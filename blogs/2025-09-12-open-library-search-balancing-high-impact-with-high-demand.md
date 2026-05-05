---
title: "Open Library Search: Balancing High-Impact with High-Demand"
url: "https://blog.openlibrary.org/2025/09/12/open-library-search-balancing-high-impact-with-high-demand/"
date: "Fri, 12 Sep 2025 22:51:17 +0000"
author: "mek"
feed_url: "https://blog.openlibrary.org/feed/"
---
<p>The Open Library is a card catalog of every book published spanning more than 50 million edition records. Fetching all of these records all at once is computationally expensive, so we use <a href="https://solr.apache.org/">Apache Solr</a> to power our search engine. This system is primarily maintained by Drini Cami and has enjoyed support from myself, Scott Barnes, Ben Deitch, and Jim Champ.</p>



<p>Our search engine is responsible for rapidly generating results when patrons use the autocomplete search box, when apps make book data requests using our programatic <a href="http://google.com/search?q=blog.openlibrary.org+search.json&amp;oq=blog.openlibrary.org+search.json&amp;gs_lcrp=EgZjaHJvbWUyBggAEEUYOTIHCAEQIRigATIHCAIQIRigATIHCAMQIRigATIHCAQQIRigATIHCAUQIRigAdIBCDg5MDVqMGo3qAIAsAIA&amp;sourceid=chrome&amp;ie=UTF-8">Search API</a>, to load data for rending book carousels, and much more.</p>



<p>A key challenge of maintaining such a search engine is keeping its schema manageable so it is both compact and efficient yet also versatile enough to serve the diverse needs of millions of registered patrons. Small decisions, like whether a certain field should be made sortable can &#8212; at scale &#8212; make or break the system&#8217;s ability to keep up with requests.</p>



<p>This year, the Open Library team was committed to releasing several ambitious search improvements, during a time when the search engine was already struggling to meet the existing load:</p>



<ul class="wp-block-list">
<li><strong>Edition-powered Carousels</strong> that go beyond the general work to show you the most relevant, specific, available edition, in your desired language.</li>



<li><a href="https://blog.openlibrary.org/2025/08/06/whats-trending-on-open-library/"><strong>Trending</strong></a> algorithms that showcase what books are having sudden upticks, as opposed to what is consistently popular over stretches of time.</li>



<li><strong><a href="https://blog.openlibrary.org/2025/07/23/connecting-k-12-students-with-books-by-reading-level/">10K Reading Levels</a></strong> to make the K-12 <a href="https://openlibrary.org/collections/k-12">Student Library</a> more relevant and useful.</li>
</ul>



<p>Rather than tout a success story (we&#8217;re still in the thick of figuring out performance day-by-day), our goal is to pay it forward, document our journey, and give others reference points and ideas for how to maintain, tune, and advance a large production search system with a small team. The vibe is &#8220;keep your head above water.&#8221;</p>



<figure class="wp-block-image size-full is-resized"><img alt="An AI generated image of someone holding a book above water" class="wp-image-2554" height="670" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-1.30.11 PM.png" style="width: 342px; height: auto;" width="764" /></figure>



<h2 class="wp-block-heading">Starting in the Red</h2>



<p>Towards the third quarter of last year, the Internet Archive and the Open Library were victim to a <a href="https://blog.archive.org/2024/05/28/internet-archive-and-the-wayback-machine-under-ddos-cyber-attack/">large scale, coordinate DDOS attack</a>. The result was significant excess load to our search engine and material changes in how we secured and accessed our networks. During this time, the entire Solr re-indexing process (i.e. the technical process for rebuilding a fresh search engine from the latest data dumps) was left in an broken state.</p>



<p>In this pressurized state, our first action was to tune Solr&#8217;s heap. We had allocated 10GB of RAM to the Solr instance but also the heap was allowed to use 10GB, resulting in memory exhaustion. When Scott lowered the heap to 8GB, we encountered fewer heap errors. This was compounded by the fact that previously, we dealt with long spikes of 503s by restarting Solr, causing a <a href="https://en.wikipedia.org/wiki/Thundering_herd_problem">thundering herd problem</a> where the server would restart just to be overwhelmed by heap errors.</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2555" height="204" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-2.42.28 PM.png" width="900" /></figure>



<p>With 8GB of heap, our memory utilization gradually rose until we were using about 95% of memory and without further tuning and monitoring, we had few options other than to increase RAM available to the host. Fortunately, we were able to grow from ~16GB to ~24GB. We typically operate within 10GB and are fairly CPU bound with a load average of around 8 across 8 CPUs.</p>



<p>We then fixed our Solr re-indexing flow, enabling us to more regularly &#8220;defragment&#8221; &#8212; i.e. run <code>optimize</code> on Solr. In rare cases, we&#8217;ve been able to split traffic between our <code>prod-solr</code> and <code>staged-solr</code> to withstand large spikes in traffic though typically we&#8217;re operating from a single Solr instance.</p>



<p>Even with more memory, there&#8217;s only so many long, expensive requests Solr can queue before getting overwhelmed. Outside of looking at the raw Solr logs, our visibility into what was happening across Solr was still limited, so we put our heads together to discuss obvious cases where the website makes expensive calls wastefully. Jim Champ helped us implement book carousels that load asynchronously and only when scrolled into view. He also switched the search page to asynchronously load the search facets sidebar. This was especially helpful as previously, trying to render expensive search facets would cause the entire search results page, as opposed to only the facets side menu, to fail.</p>



<h2 class="wp-block-heading">Sentry on the Hill</h2>



<p>After several tiers of low hanging fruit was plucked, we used more specific tools and added monitoring. First, we added sentry profiling which gave us much more clarity about which queries were expensive, and how often Solr errors were occurring.</p>



<p>Sentry allows us to see a panoramic view of our search performance.</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2558" height="1040" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-3.18.18 PM.png" width="1464" /></figure>



<p>Sentry also gives us the ability to drill in and explore specific errors and their frequencies.</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2556" height="636" src="https://blog.openlibrary.org/files/2025/09/image-1.png" width="1520" /></figure>



<p>With profiling, we can even explore individual function calls to learn where the process is spending the most amount of time.</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2557" height="1000" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-3.17.31 PM.png" width="1408" /></figure>



<h2 class="wp-block-heading">Docker Monitoring &amp; Grafana </h2>



<p>To further increase our visibility, Drini developed a new type of <a href="https://github.com/internetarchive/openlibrary/pull/10522">monitoring docker container</a> that can be deployed agnostically to each of our VMs and use environment variables so that only relevant jobs would be run for that host. This approach has allowed us to centrally configure recipes so each host collects the data it needs and uploads it to our central dashboards in Grafana.</p>



<p>Recently, we added <a href="https://github.com/internetarchive/openlibrary/pull/11156">labels</a> to all of our Solr calls so we can view exactly how many requests are being made of each query type and what their performance characteristics are.</p>



<p>At a top level, we can see in blue how much total traffic we&#8217;re getting to Solr and the green colors (darker is better) lets us know how many requests are being served quickly.</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2559" height="386" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-3.28.12 PM-scaled.png" width="2560" /></figure>



<p>We can then drill in and explore each Solr query by type, identifying which endpoints are causing the greatest strain and giving us a way to then analyze nginx web traffic further in case it is the result of a DDOS.</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2560" height="1088" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-3.29.44 PM.png" width="1466" /></figure>



<p>Until recently, we were able to see how hard each of our main Open Library web application works were working at any given time. Spikes of pink or purple were when Open Library was waiting for requests to finish from Archive.org. Yellow patches &#8212; until recently &#8212; were classified as &#8220;other,&#8221; meaning we didn&#8217;t know exactly what was going on (even though Sentry profiling and flame graphs gave us strong clues that Solr was the culprit). By using <a href="https://github.com/benfred/py-spy">pyspy</a> with our new docker monitoring setup, we were able to add Solr profling into our worker graphs on Grafana and visualize the complete story clearly:</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2561" height="537" src="https://blog.openlibrary.org/files/2025/09/Screenshot-2025-09-12-at-3.35.14 PM-scaled.png" width="2560" /></figure>



<p>Once we turned on this new monitoring flow, it was clear these large sections of yellow, where workers were inundated with &#8220;unknown&#8221; work, were almost entirely (~50%) Solr.</p>



<h2 class="wp-block-heading">With Great Knowledge&#8230;</h2>



<p>Each graph helped us further direct and focus our efforts. Once we knew Open Library was being slowed down primarily by Solr, we began investigating requests and Drini noticed many Solr requests were living on for more than 10 seconds, even though the Open Library app has been given instructions to abandon any Solr query that takes more than 10 seconds. It turns out, even in these cases, Solr may continue to process the query in the background (so it can finish and cache the result for the future). This &#8220;feature&#8221; was resulting in Solr&#8217;s free connections becoming exhausted and a long haproxy queue. Drini modified our Solr queries to include a <code>timeAllowed</code> parameter to match Open Library&#8217;s contract to quit after 10 seconds and almost immediately the service showed signs of recovery:</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2562" height="456" src="https://blog.openlibrary.org/files/2025/09/image-2.png" width="686" /></figure>



<p>After we set the&nbsp;<code>timeAllowed</code>&nbsp;parameter, we began to encounter more clear examples of queries failing and investigated patterns within Sentry. We realized a prominent trends of very expensive, unuseful, one-character or stop-word-like queries like&nbsp;&#8220;<code>*"</code>&nbsp;or&nbsp;&#8220;<code>a"</code>&nbsp;or&nbsp;&#8220;<code>the"</code>. By looking at the full request and url parameters in our nginx logs, we discovered that the autocomplete search bar was likely responsible for submitting lots of unuseful requests as patrons typed out the beginning of their search.</p>



<p>To fix this, we patched our autocomplete to require at least 3 characters (and not e.g. the word &#8220;the&#8221;) and also are building in backend directives to Solr to pre-validate queries to avoid processing these cases.</p>



<h2 class="wp-block-heading">Conclusion</h2>



<p>Sometimes, you just need more RAM. Sometimes, it&#8217;s really important to understand how complex systems work and how heap space needs to be tuned. More than anything, having visibility and monitoring tools have bee critical to learning which opportunities to pursue in order to use our time effectively. <strong>Always</strong>, having talented, dedicated engineers like Drini Cami, and the support of Scott Barnes, Jim Champ, and many other contributors, is the reason Open Library is able to keep running day after day. I&#8217;m proud to work with all of you and grateful for all the search features and performance improvements we&#8217;ve been able to deliver to Open Library&#8217;s patrons in 2025.</p>
