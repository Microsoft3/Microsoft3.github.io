---
layout: post
title: Bookmark - SMTP NDR CODEs (Technet)
date: 2013-12-09 10:55
author: sammykrosoft
comments: true
categories: [Uncategorized]
---
<p><p></p><p>4.3.1</p><p>Out-of-memory or out-of-disk space condition on the Exchange server. Potentially also means out-of-file handles on IIS.</p><p>4.3.2</p><p>Message deleted from a queue by the administrator via the Queue Viewer interface in Exchange System Manager.</p><p>4.4.1</p><p>Host not responding. Check network connectivity. If problem persists, an NDR will be issued.</p><p>4.4.2</p><p>Connection dropped. Possible temporary network problems.</p><p>4.4.6</p><p>Maximum hop count for a message has been exceeded. Check the message address, DNS address, and SMTP virtual servers to make sure that nothing is causing the message to loop.</p><p>4.4.7</p><p>Message expired. Message wait time in queue exceeds limit, potentially due to remote server being unavailable.</p><p>5.0.0</p><p>Generic message for no route is available to deliver a message or failure. If it is an outbound SMTP message, make sure that an address space is available and have proper routing groups listed.</p><p>5.1.0</p><p>Message categorizer failures. Check the destination addresses and resend the message. Forcing rebuild of Recipient Update Service (RUS) may resolve the issue.</p><p>5.1.1</p><p>Recipient could not be resolved. Check the destination addresses and resend the message. Potentially e-mail account no longer exists on the destination server.</p><p>5.1.3</p><p>Bad address.</p><p>5.1.4</p><p>Duplicate SMTP address. Use LDIFDE or script to locate duplicate and update as appropriate.</p><p>5.2.1</p><p>Local mail system rejected message, &ldquo;over size&rdquo; message. Check the recipient&rsquo;s limits.</p><p>5.2.3</p><p>Message too large. Potentially the recipient mailbox is disabled due to exceeding mailbox limit.</p><p>5.3.3</p><p>The remote server has run out of disk space to queue messages, possible SMTP protocol error.</p><p>5.3.5</p><p>Message loopback detected.</p><p>5.4.0</p><p>Authoritative host not found. Check message and DNS to ensure proper entry. Potential error in smarthost entry or SMTP name lookup failure.</p><p>5.4.4</p><p>No route found to next hop. Make sure connectors are configured correctly and address spaces exist for the message type</p><p>5.4.6</p><p>Categorizer problems with recipient. Recipient may have alternate recipient specified looping back to self.</p><p>5.4.8</p><p>Looping condition detected. Server trying to forward the message to itself. Check smarthost configuration, FQDN name, DNS host and MX records, and recipient policies.</p><p>5.5.0</p><p>Generic SMTP protocol error.</p><p>5.5.2</p><p>SMTP protocol error for receiving out of sequence SMTP protocol command verbs. Possible to low disk space/memory of remote server.</p><p>5.5.3</p><p>Too many recipients in the message. Reduce number of recipients in message and resend.</p><p>5.7.1</p><p>Access denied. Sender may not have permission to send message to the recipient. Possible unauthorized SMTP relay attempt from SMTP client.</p><p></p><p></p><p>Source: </p><a title="https://www.microsoft.com/technet/prodtechnol/exchange/guides/ExMgmtGuide/fb7830cf-23c6-48a6-8759-526b7854ae39.mspx?mfr=true" href="https://www.microsoft.com/technet/prodtechnol/exchange/guides/ExMgmtGuide/fb7830cf-23c6-48a6-8759-526b7854ae39.mspx?mfr=true">https://www.microsoft.com/technet/prodtechnol/exchange/guides/ExMgmtGuide/fb7830cf-23c6-48a6-8759-526b7854ae39.mspx?mfr=true</a></p>
