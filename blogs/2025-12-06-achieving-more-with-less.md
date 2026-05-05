---
title: "Achieving More with Less"
url: "https://blog.openlibrary.org/2025/12/06/achieving-more-with-less/"
date: "Sat, 06 Dec 2025 18:27:21 +0000"
author: "mek"
feed_url: "https://blog.openlibrary.org/feed/"
---
<p><strong>Setbacks:</strong> 2025 has been a challenging year for the Open Library community and the library world. We began the year by upgrading our systems in response to cybersecurity incidents and <a href="https://blog.openlibrary.org/2025/09/12/open-library-search-balancing">fortifying our web services</a> to withstand relentless DDOS (distributed <a href="https://en.wikipedia.org/wiki/Denial-of-service_attack">denial of service</a>) attacks from bots. We developed revised plans to achieve <a href="https://docs.google.com/document/d/1FdhNnT83uBMC6gjXl4w_VeYEyqXfnM6iwGgvYg9Wl0A/edit?tab=t.0#heading=h.61ofb5mxo698"><strong>More with Less</strong></a> to meet the needs of patrons who lost access to <a href="https://blog.archive.org/2024/06/14/patrons-speak-out-the-impact-of-losing-access-to-more-than-500000-books/">500,000 books</a> due to late-2024 takedowns. The year continued to bring setbacks, including a <a href="https://torrentfreak.com/images/251001-BAPO-D-NL-006-ENG.pdf">Brussels Court order</a>, which resulted in additional removals, and contesting thousands of spammy automated takedown requests from an AI company. Just last month, we responded to a power outage affecting one of our data centers and then a cut that was identified in one of our internet service provider&#8217;s fiberoptic cables, resulting in reduced access. </p>



<p>Given all these setbacks, why weren&#8217;t we seeing a decline in sign-ups?</p>



<p><strong>Less is More:</strong> Putting patrons&#8217; experience first. As the year progressed and we reviewed our quarterly numbers, one metric that circumstantially held high was sign-ups. The Open Library is historically a significant source of registrations for the Internet Archive, contributing to approximately 30% of all registrations. Some websites may have found it reassuring that, despite all the challenges presented in 2024 and 2025, adoption seemed to keep its pace. At the Open Library, we measure success in <strong>value</strong> delivered to readers &#8212; not registrations &#8212; and this trend seemed to indicated something may have become out of balance:</p>



<pre class="wp-block-verse"><strong><em>What reason(s) might explain why registrations remain steady when significant sources of value are no longer accessible?</em></strong></pre>



<p>We <strong>hypothesized</strong> some class of patrons are signing up with an expectation and then not getting the value they are expecting.</p>



<p><strong>Testing the hypothesis: </strong>The first step of our investigation was to take inventory of the possible reasons one might register an account. Each of the following actions <strong>require accounts</strong>:</p>



<ul class="wp-block-list">
<li>Borrowing a book</li>



<li>Using the Reading Log</li>



<li>Adding books to Lists</li>



<li>Community review tags</li>



<li>Following other readers</li>



<li>Reading Goals</li>
</ul>



<p><strong>Supporting Evidence: </strong>We started by reviewing the Reading Log because it&#8217;s the platform&#8217;s <a href="https://openlibrary.org/stats">largest source of engagement</a>, with 5M unique patrons logging 11.5M books. We discovered that millions of patrons had only logged a <strong>single</strong> book. There&#8217;s nothing inherently bad about this statistic, in fact many websites may be happy about this engagement. However, unlike many book catalog websites, the Open Library is unique in that it links to millions of books that may be accessed through trusted book providers. It is thus reasonable that many patrons come to the Open Library website with the intent of accessing a specific title. This data amplified occasional reports from patrons who expressed disappointed when clicking &#8220;Want to Read&#8221; did not result in access to the book.</p>



<p><strong>Refined hypothesis:</strong> Based on these learnings, we felt confident the &#8220;<strong>Want to Read</strong>&#8221; button may be confusing new patrons who thought clicking the button would get them <strong>access</strong> to the book. Under this lens, each of these registrations represents adoption for the wrong reason: i.e. a patron is compelled by the offering to register, but they bounce because what they get is a broken promise.</p>



<p><strong>Trying a solution:</strong> Data gave us confidence the &#8220;Want to Read&#8221; button may be confusing new visitors to the site, but it also revealed that hundreds of thousands of patrons are actively using the Reading Log to keep track of books and we didn&#8217;t want to confuse the experience for them. We decided to change the website so that <strong>non-logged-in</strong> patrons, would see the &#8220;Want to Read&#8221; button as &#8220;Add to List&#8221; instead, whereas <strong>logged-in </strong>returning visitors would continue to see the &#8220;Want to Read&#8221; button they were used to.</p>



<div class="wp-block-group is-nowrap is-layout-flex wp-container-core-group-is-layout-ad2f72ca wp-block-group-is-layout-flex">
<figure class="wp-block-image size-full is-resized"><img alt="The original button presented to patrons, which shows a potentially misleading: &quot;Want to Read&quot;" class="wp-image-2591" height="196" src="https://blog.openlibrary.org/files/2025/12/Screenshot-2025-12-06-at-10.28.23 AM.png" style="width: 183px; height: auto;" width="418" /><figcaption class="wp-element-caption"><strong>Before:</strong> <em>The original button presented to patrons, which shows a potentially misleading: &#8220;Want to Read&#8221;</em></figcaption></figure>



<figure class="wp-block-image size-full is-resized"><img alt="The button presented to logged out patrons after the change, reading &quot;Add to List&quot; instead of &quot;Want to Read&quot;" class="wp-image-2585" height="204" src="https://blog.openlibrary.org/files/2025/12/image-1.png" style="width: 183px; height: auto;" width="359" /><figcaption class="wp-element-caption"><em><strong>After:</strong> The button presented to logged out patrons after the change, reading &#8220;Add to List&#8221; instead of &#8220;Want to Read&#8221;</em></figcaption></figure>
</div>



<p class="has-text-align-left"><strong>Results: </strong>When our team launched this week&#8217;s deploy, we noticed a few performance hiccups: our latest deploy increased memory demands and our servers began using too much memory, causing <a href="https://en.wikipedia.org/wiki/Swap_(computer_programming)">swapping</a>. After some fire-fighting, we were able to make adjustments to our workers that normalized performance, though we remained alert.</p>



<figure class="wp-block-image size-large"><img alt="A chart from Open Library's grafana system indicating that the website was facing a large number of 503's (i.e. it failed to respond to patron requests) " class="wp-image-2586" height="131" src="https://blog.openlibrary.org/files/2025/12/Screenshot-2025-12-05-at-11.44.19 AM-500x131.png" width="500" /></figure>



<p>Later that night, we noticed a significant drop in registrations and started frantically testing the website:</p>



<figure class="wp-block-image size-large"><img alt="A chart from Open Library's grafana system indicating that registrations-per-minute had fallen in the latest deploy." class="wp-image-2584" height="267" src="https://blog.openlibrary.org/files/2025/12/image-500x267.png" width="500" /></figure>



<p>We were <strong>thrilled</strong> to realize that our services are working correctly and the chart accurately reflected &#8212; what we hope to be &#8212; a decrease in bad experiences for our patrons. </p>



<p><strong>Conclusion: </strong>Sometimes, less is more. We anticipate this will be the first small change in a long <a href="https://jamesclear.com/marginal-gains">series of marginal improvements</a> we hope to bring us closer into alignment with the core needs of our patrons. As we move towards 2026, we will continue to respond to the new<strong> normal </strong>shaped by recent events with the mantra: <strong>back to basics</strong>.</p>
