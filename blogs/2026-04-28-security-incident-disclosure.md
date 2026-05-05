---
title: "Security Incident Disclosure"
url: "https://blog.openlibrary.org/2026/04/28/security-incident-disclosure-2024-04-28/"
date: "Tue, 28 Apr 2026 22:42:18 +0000"
author: "mek"
feed_url: "https://blog.openlibrary.org/feed/"
---
<p>Early, around 7:30am Pacific, on Tuesday, April 28th, high database load was detected on OpenLibrary.org. Investigation revealed a set of at least 38,703 residential IP addresses performing a coordinated <code><a href="https://en.wikipedia.org/wiki/SQL_injection">sqlinjection</a></code> attack on a vulnerable <a href="http://openlibrary.org">openlibrary.org</a> endpoint, resulting in exfiltration of emails and encrypted passwords of 175,080 <strong>legacy</strong> accounts, registered before March, 2011. This table has not been used for authentication since 2016, however we advise affected accounts to change their passwords on any relevant platforms.</p>



<p>The attack was identified and mitigated within a four hour window. Impact was limited due to the obscurity of the attack which could only process a single account query per malicious request. This is an old, no-longer-in-use table that was formerly used for Open Library sign-in <strong>prior </strong>to switching to use<a href="http://archive.org"> Archive.org</a> login credentials in 2016.</p>



<p><strong>Details </strong></p>



<p>Prior to 2016, Open Library maintained its own login system distinct from <a href="http://archive.org">Archive.org</a>, which used a legacy <code>account</code> database table. In 2016, both for improved security and patron convenience, the Open Library website switched to a unified model where authentication is performed using <a href="http://archive.org">archive.org</a> credentials and <strong>not </strong>legacy Open Library credentials. Since this date <strong>no</strong> new Open Library patron account passwords have been stored within Open Library’s legacy <code>account</code> database. </p>



<p>Today&#8217;s incident only affects a subset of legacy accounts whose credentials are no longer in active use. Furthermore, no plaintext passwords were compromised – all passwords in this table were both <a href="https://en.wikipedia.org/wiki/Salt_(cryptography)">salted</a> and encrypted.</p>



<p><strong>Remediation &amp; Impact</strong></p>



<p>Upon discovery, the identified exploited path was blocked at the nginx level and a <a href="https://github.com/internetarchive/openlibrary/pull/12460">security fix</a> was then patch deployed to our servers. All accounts in the no-longer-in-use legacy `account` table have had their encrypted password fields cleared. We are releasing a tool to check whether your email was affected by the breach.</p>



<p><strong>Check If Your Account is Affected</strong></p>



<p>If your email is <a href="https://openlibrary.org/account/security/2026-04-28T18">on this list</a>, out of an abundance of concern, we recommend changing your password for any service that matches the password used when registering your OpenLibrary account.</p>



<p><strong>Open Library’s Security Policy</strong></p>



<p>The Open Library team routinely monitors security alerts, performs sqlinjection audits, and responds seriously to security reports we receive. We believe strongly in a full transparency policy when incidents occur, both so our patrons have the best information to make decisions, are able to understand our responses, and so our developer community can help report and address issues.</p>



<p><strong>Followup</strong></p>



<p>Followup details and actions will be updated via our <a href="https://github.com/internetarchive/openlibrary/issues/12459">post-mortem</a>. Please feel warmly invited to direct questions and concerns to <a href="mailto:info@archive.org">info@archive.org</a> and report security vulnerabilities to <a href="mailto:security@archive.org">security@archive.org</a> and <a href="mailto:mek@archive.org">mek@archive.org</a>.</p>



<p><strong>Apologies &amp; Gratitude</strong></p>



<p>Thank you for your patience and understanding and our sincere apologies for the poor behavior of these malicious actors and the impact this has on our community. As AI tooling makes it easier for malicious actors to attack websites like ours, our team will continue to proactively take steps to put our patrons’ privacy and security first.</p>



<p>The Open Library Team</p>



<p>Mek, Drini, Jim, Lisa</p>
