---
title: "Improving Search by 10%"
url: "https://blog.openlibrary.org/2026/04/16/improving-search-by-10-percent/"
date: "Thu, 16 Apr 2026 04:18:15 +0000"
author: "mek"
feed_url: "https://blog.openlibrary.org/feed/"
---
<p>Today&#8217;s challenge is to find &#8220;<a href="https://openlibrary.org/works/OL42542598W/The_Secret_of_Secrets?edition=key%3A/books/OL61173979M">The Secret of Secrets</a>&#8220;, by&nbsp;<a href="https://openlibrary.org/authors/OL39307A/Dan_Brown">Dan Brown</a> using Open Library <a href="https://openlibrary.org/search">search</a>. It&#8217;s not impossible, but it is <strong>not </strong>easy&#8230; And it&#8217;s not just because the <strong>Я</strong> is backwards on the cover.</p>


<div class="wp-block-image">
<figure class="alignleft size-full"><img alt="" class="wp-image-2668" height="388" src="https://blog.openlibrary.org/files/2026/04/image-6.png" width="257" /></figure></div>


<p>If you search for &#8220;<a href="https://openlibrary.org/search?q=the+secret+of+secrets&amp;mode=everything">the secret of secrets</a>&#8220;, you <strong>won&#8217;t</strong> find the right match on the first <strong>two pages </strong>of results.</p>



<p>If you search for &#8220;<a href="https://openlibrary.org/search?q=the+secret+of+secrets+dan+brown&amp;mode=everything">the secret of secrets dan brown</a>&#8220;, the result is still 7th in the list.</p>



<p>In this example, our current search algorithm is biasing too heavily on returning book results that have lots of editions to vouch for them, as well as other boosting factors (like star ratings) that don&#8217;t always produce desired result.</p>



<p>What search algorithm would perform better? And how do know whether one approach is better than the other?</p>



<p>These are key questions <a href="https://openlibrary.org/about/team#:~:text=Core%20Developer-,Drini%20Cami,-Core%20Developer">Drini Cami</a> &#8212; core maintainer of Open Library search &#8212; has been investigating this month.</p>



<h2 class="wp-block-heading">Is Search Improving?</h2>



<p>In order to know whether we&#8217;re making changes that improve the quality of our search results, we can&#8217;t just change the algorithm, type in a search, and see if the result is better in that one case. We need to apply some consistent framework across a collection of challenging queries and measure how the system &#8212; on a whole &#8212; performed before versus after.</p>



<p>In Open Library&#8217;s case, Drini maintains a <a href="https://docs.google.com/spreadsheets/d/1BN5I7-OkTPaoTr2Es6jQ4O9ICWFmH0q9CP6kEgolCgg/edit?gid=1006480604#gid=1006480604">Search Evaluation Spreadsheet</a> that measures 100 common searches—everything from &#8220;Harry Potter&#8221; and &#8220;Little Prince&#8221; to &#8220;The Secret Garden&#8221; and &#8220;Narnia&#8221;. These searches come from our server logs (i.e. popular searches from patrons). It also contains challenging cases that we&#8217;ve seen underperform in the past. </p>



<p>For each search query we&#8217;ve collected, we define what we expect the &#8220;correct&#8221; search result to be and then check how often the correct result appears in the top 3 search results (across the search algorithms we&#8217;re considering).</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2663" height="786" src="https://blog.openlibrary.org/files/2026/04/Screenshot-2026-04-15-at-9.04.59 PM.png" width="2226" /></figure>



<h2 class="wp-block-heading">Multiplicative Instead of Additive</h2>



<p>For the technical crowd, <a href="https://github.com/internetarchive/openlibrary/pull/12357">this change (PR #12357)</a> adjusts Work Search’s Solr eDisMax tuning to use <strong>multiplicative</strong> boosting (via&nbsp;<code>boost</code>) instead of <strong>additive</strong> boosting (via&nbsp;<code>bf</code>) to reduce over-weighting of popularity signals relative to textual relevance:</p>



<ul class="wp-block-list">
<li>Replaces&nbsp;<code>bf</code>-based additive boosts with an eDismax&nbsp;<code>boost</code>&nbsp;function expression.</li>



<li>Expands/adjusts&nbsp;<code>qf</code>&nbsp;and phrase-boost parameters (<code>pf</code>,&nbsp;<code>pf2</code>) to change match weighting and proximity scoring.</li>
</ul>



<p>Overall, the change has improved the relevance of our test results by roughly 10%:</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2662" height="742" src="https://blog.openlibrary.org/files/2026/04/577477282-46d64b59-b034-4d61-97da-88fd2004f7ae.png" width="1602" /></figure>



<h2 class="wp-block-heading">Early Anecdotes:</h2>



<p>In our <a href="https://codepen.io/cdrini/full/wvJqzaK">testing playground</a>&#8230;</p>



<figure class="wp-block-image size-full"><img alt="" class="wp-image-2666" height="1152" src="https://blog.openlibrary.org/files/2026/04/578981005-aa5c5dfd-f112-4779-9b1c-2301ed9fae25-scaled.png" width="2560" /></figure>



<ul class="wp-block-list">
<li>&#8220;The secret of secrets&#8221; now appears as the 3rd result.</li>



<li>&#8220;My Life&#8221;, by Bill Clinton went from 101th to 19th</li>



<li>&#8220;laws field guide&#8221; went from 14th to 1st</li>
</ul>



<p>Expect these improvements to be live on the main site early next week. Happy reading!</p>



<h2 class="wp-block-heading">Future Opportunities: Exact Match versus Browser</h2>



<p>Since releasing this blog post, we received a great question internally by Sawood Alam, from the Wayback Machine team who asks:</p>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p>Have you measured how would this change affects the <strong>discovery </strong>use-case where a patron is not after one specific document in mind, but wants to find out what options are out there (as opposed to the lookup use-case where they already know what they are looking for)?</p>
</blockquote>



<p>And this is indeed something the Open Library team has been considering. Sawood is pointing out that there are [at <strong>least</strong>] <strong>two</strong> modes of searching:</p>



<ol class="wp-block-list">
<li>by <strong>Exact</strong> match</li>



<li><strong>Browsing</strong></li>
</ol>



<p>One may browse in a variety of different ways, but for simplicity I&#8217;d like to refer to this as &#8220;searching by proxy&#8221;. That is to say, instead of searching for an exact book by title, a patron may endeavor to discover a suitable book by any number or combination of proximal qualities like author, topic, format, genre. An example is a search for <code>nonfiction</code> books about <code>UFO</code>s that are advertised as <code>textbooks</code> and published before <code>1950</code>.</p>



<p>For <strong>browsing</strong> queries of this flavor, it&#8217;s difficult to know (in advance) what book(s) should appear in the top-three position in search results as the answer will often be subjective to the searcher.</p>



<p>As a result, an additional approach will need to be instrumented and added to our existing process that (a) accurately identifies <strong>when </strong>a search term is for a proximal <code>quality</code> rather than an <code>exact</code> (e.g. title) match and, (b) introduces secondary evaluation metric, such as:</p>



<ul class="wp-block-list">
<li><strong>Success Rate:</strong> How often <em>any</em> result is clicked &#8212; perhaps called Query Success Rate (QSR)</li>



<li><strong>Relevance:</strong> <em>When</em> a result is clicked&#8230; how often is this click for a record in a<strong> top 3</strong> position &#8212; something like Mean Reciprocal Rank (MRR)</li>
</ul>



<p>Further research is required to understand how these metrics may be combined in a recipe that results in the best experience for patrons. For instance, [when] is it more important to improve relevance versus the general distribution of clicks? Maybe &#8220;better&#8221; means increasing the ratio of searches-to-clicks by 20% rather than increasing the number of clicks in the top-3 position by 25% (if search-to-clicks were to drop by 5%).</p>



<p>Suffice to say, as policy changes make it more challenging for some readers to find the exact book(s) they are looking for, it becomes increasingly meaningful to be able to suggest suitable alternatives &#8212; and be able to measure how effective we are at making relevant recommendations. Measuring <strong>browse </strong>cases is something we expect to work towards in the coming months.</p>
