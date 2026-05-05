---
title: "Featuring Ben Deitch, Engineering Fellow"
url: "https://blog.openlibrary.org/2026/03/03/featuring-ben-deitch-engineering-fellow/"
date: "Tue, 03 Mar 2026 00:10:27 +0000"
author: "elizabethmays"
feed_url: "https://blog.openlibrary.org/feed/"
---
<p>By Elizabeth Mays &amp; Mek</p>


<div class="wp-block-image is-style-rounded">
<figure class="alignleft size-full"><img alt="" class="wp-image-2631" height="200" src="https://blog.openlibrary.org/files/2026/03/image.png" width="200" /></figure></div>


<p>Open Library is powered by a global community of volunteers, a small team of staff, and several extraordinary, handpicked volunteer fellows who are picked to work alongside staff to tackle ambitious, high impact projects. This week, we’re featuring the work of Engineering Fellow Ben Deitch, who has made a dramatic impact on the Open Library initiative since 2024.&nbsp;</p>



<p>Ben’s numerous engineering contributions have strengthened Open Library’s experience for hundreds of thousands of patrons. With the mentorship of senior staff engineer Drini Cami, Ben wrote code that enables patrons to:</p>



<ul class="wp-block-list">
<li>Find exact book editions from their Reading Logs</li>



<li>Search which books were read within any given year</li>



<li>Discover interesting books based on a sophisticated <a href="https://www.reddit.com/r/AskProgramming/comments/6pc2bd/what_is_reddit_trending_algorithm/">reddit-style</a> trending algorithm</li>



<li>Mark books as “Want to Read” from author pages</li>
</ul>



<p>Prior to Ben’s work, reading logs would show works instead of editions. Ben added the ability to <a href="https://github.com/internetarchive/openlibrary/pull/8821">view editions on a reading log</a>. This enables users to track the precise editions of books they have read. The log will also show the right cover for each edition.&nbsp;</p>



<p>Ben also implemented a basic “<a href="https://github.com/internetarchive/openlibrary/pull/8873">fuzzy search</a>” for the Solr Search engine, making the overall search system much more tolerant of spelling errors and bringing it closer to modern standards for search engines so that patrons don’t hit dead ends.&nbsp;</p>



<p>In another project, Ben coded in a new,<a href="https://github.com/internetarchive/openlibrary/pull/8725"> image-based preview for user created book lists</a>, which appears on users’ My Books pages. This feature also enables patrons to see the first few books in a list at a glance.&nbsp;</p>



<p>Ben can also be credited for enabling the <a href="https://github.com/internetarchive/openlibrary/pull/8639">“already read” books to be viewed by the year in which they were read</a>.&nbsp;</p>



<p>Historically, search results and book pages have featured a “Want to Read” button that patrons can click to keep track of books of interest. Ben extended book results so patrons can also click “Want to Read” from the author’s page.</p>



<p>In the past, when carousels were rendered for the homepage, facets were included – like language – that were accidentally being dropped when additional results were loaded. Ben fixed this <a href="https://github.com/internetarchive/openlibrary/pull/8586">issue</a> so books results were relevant even when loading multiple pages.</p>



<p>Finally, Ben fixed an librarian issue to <a href="https://github.com/internetarchive/openlibrary/pull/8735">alter the display message after the merging author entries</a> so merging two author records no longer show as successful when there was actually an error</p>



<p>Ben’s work can be found across the Open Library – from the search page, to the home page, the author’s page, and the my books page. We are grateful to Ben and couldn’t be more proud of his contributions to our Open Library.</p>



<p>You can send Ben kudos <a href="https://www.linkedin.com/in/benjamin-b-deitch/">here</a> on LinkedIn!</p>
