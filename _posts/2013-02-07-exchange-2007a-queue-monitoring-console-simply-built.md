---
layout: post
title: Exchange 2007–A Queue Monitoring Console simply built
date: 2013-02-07 12:53
author: sammykrosoft
comments: true
categories: [Uncategorized]
---
<p>&#160;</p>  <p>Using my DTW (Document-Tool-Walkthru) Excel based tool that you can download through : <a title="http://www.opsvault.com/how-to-build-a-simple-and-efficient-windows-monitoring-solution-dtw/" href="http://www.opsvault.com/how-to-build-a-simple-and-efficient-windows-monitoring-solution-dtw/">http://www.opsvault.com/how-to-build-a-simple-and-efficient-windows-monitoring-solution-dtw/</a></p>  <p>&#160;</p>  <p>Here is a nice HTA console quickly built with the above Excel tool that I called “DTW” tool :</p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/73/61/metablogapi/0361.image_2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-73-61-metablogapi/0361.image_5F00_2.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/73/61/metablogapi/3173.image_thumb.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/communityserver-blogs-components-weblogfiles/00-00-00-73-61-metablogapi/3173.image_5F00_thumb.png" width="463" height="251" /></a></p>  <p>&#160;</p>  <p>And here is the code generated with the help of my <a href="http://www.opsvault.com/how-to-build-a-simple-and-efficient-windows-monitoring-solution-dtw/">DTW</a>. Copy and paste the below code into a notepad that you save as “LocalQueueMonitor.hta”. </p>  <p>The below generated HTA file will only run on a local Exchange 2007 server, but the <a href="http://www.opsvault.com/how-to-build-a-simple-and-efficient-windows-monitoring-solution-dtw/">DTW</a> enables you to easily build a console that will run against remote server(s). Plus, you can play with the “Console initialization parameters” as you want to customize the look and feel and behaviour of your console !</p>  <p>Here is the code, generated by the <a href="http://www.opsvault.com/how-to-build-a-simple-and-efficient-windows-monitoring-solution-dtw/">DTW tool</a>, and that will to generate an HTA file that will monitor the local Exchange 2007 server queues:</p>  <p><font face="Courier New">&lt;HTML&gt;      <br />&lt;BODY BGCOLOR=#C0C0C0&gt;       <br />&lt;OBJECT       <br />CLASSID=&quot;clsid:C4D2D8E0-D1DD-11CE-940F-008029004347&quot;       <br />ID=&quot;Monitor&quot;       <br />HEIGHT=80%       <br />WIDTH=100%&gt;       <br />&lt;/OBJECT&gt;</font></p> <font face="Courier New">   <p>     <br />&lt;SCRIPT LANGUAGE=&quot;VBScript&quot;&gt;</p>    <p>     <br />Sub Window_OnLoad       <br />On Error Resume Next</p>    <p>     <br />' Console initialization       <br />Monitor.DisplayType = &quot;1&quot;       <br />Monitor.ReportValueType = &quot;0&quot;       <br />Monitor.MaximumScale = &quot;100&quot;       <br />Monitor.MinimumScale = &quot;0&quot;       <br />Monitor.ShowLegend = &quot;1&quot;       <br />Monitor.ShowToolbar = &quot;1&quot;       <br />Monitor.ShowScaleLabels = &quot;1&quot;       <br />Monitor.ShowHorizontalGrid = &quot;1&quot;       <br />Monitor.ShowVerticalGrid = &quot;1&quot;       <br />Monitor.ShowValueBar = &quot;1&quot;       <br />Monitor.ManualUpdate = &quot;0&quot;       <br />Monitor.Highlight = &quot;1&quot;       <br />Monitor.ReadOnly = &quot;1&quot;       <br />Monitor.MonitorDuplicateInstances = &quot;1&quot;       <br />Monitor.UpdateInterval = &quot;1&quot;       <br />Monitor.DisplayFilter = &quot;1&quot;       <br />Monitor.BackColorCtl = &quot;-2147483633&quot;       <br />Monitor.ForeColor = &quot;-1&quot;       <br />Monitor.BackColor = &quot;-1&quot;       <br />Monitor.GridColor = &quot;8421504&quot;       <br />Monitor.TimeBarColor = &quot;255&quot;       <br />Monitor.BorderStyle = &quot;2&quot;       <br />Monitor.TimeAxisLabels = &quot;1&quot;       <br />Monitor.Tooltip = &quot;1&quot;       <br />Monitor.NextCounterColor = &quot;4&quot;       <br />Monitor.NextCounterWidth = &quot;0&quot;       <br />Monitor.NextCounterLineStyle = &quot;0&quot;       <br />Monitor.MaximumSamples = &quot;200&quot;       <br />Monitor.GraphTitle = &quot;CPU and Submission queues&quot;       <br />Monitor.YAxisLabel = &quot;Y label&quot;       <br />Monitor.DigitGrouping = &quot;1&quot;       <br />Monitor.WrapTimeLine = &quot;1&quot;       <br />Monitor.DataSourceType = &quot;1&quot;       <br />'Monitor.SqlDsnName =       <br />'Monitor.SqlLogSetName =       <br />Monitor.LogFileCount = &quot;0&quot;       <br />Monitor.AmbientFont = &quot;1&quot;       <br />'Monitor.LegendColumnWidths =       <br />Monitor.LegendSortDirection = &quot;-2&quot;       <br />Monitor.LegendSortColumn = &quot;0&quot;       <br />Monitor.CounterCount = &quot;4&quot;       <br />Monitor.MaximumSamples = &quot;100&quot;</p>    <p>     <br />' Counters list added to the console       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Aggregate Delivery Queue Length (All Queues)&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Messages Completed Delivery Per Second&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Poison Queue Length&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Retry Mailbox Delivery Queue Length&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Retry Non-Smtp Delivery Queue Length&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Retry Remote Delivery Queue Length&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Submission Queue Length&quot;)       <br />Monitor.Counters.Add(&quot;\MSExchangeTransport Queues(_total)\Unreachable Queue Length&quot;)       <br />Monitor.Counters.Add(&quot;\Memory\Available Mbytes&quot;)       <br />Monitor.Counters.Add(&quot;\Processor(_Total)\% Processor Time&quot;)</p>    <p>     <br />' Counter drawing customization       <br />Monitor.Counters.Item(19).Color = &quot;100&quot;       <br />Monitor.Counters.Item(19).Width = &quot;4&quot;       <br />Monitor.Counters.Item(19).LineStyle = &quot;2&quot;       <br />Monitor.Counters.Item(19).ScaleFactor = &quot;0.001&quot;       <br />Monitor.Counters.Item(19).Show = &quot;1&quot;       <br />Monitor.Counters.Item(19).Selected = &quot;0&quot;       <br />Monitor.Counters.Item(19).StatisticStatus = &quot;0&quot;       <br /></p>    <p>End Sub</p>    <p>     <br />&lt;/SCRIPT&gt;       <br />&lt;/BODY&gt;       <br />&lt;/HTML&gt;</p> </font>