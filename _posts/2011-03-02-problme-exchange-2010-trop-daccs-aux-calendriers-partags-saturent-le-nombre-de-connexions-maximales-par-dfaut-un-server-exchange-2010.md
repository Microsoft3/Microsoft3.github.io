---
layout: post
title: Problème Exchange 2010 –Trop d’accès aux calendriers partagés saturent le nombre de connexions maximales par défaut à un server Exchange 2010
date: 2011-03-02 11:08
author: sammykrosoft
comments: true
categories: [Uncategorized]
---
<p>&#160;</p>  <p>Lorsque des clients Outlook 2007 utilisent la fonction de calendriers partagés, ils ouvrent implicitement des connections clientes de type “Exchange Administrator”.</p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/73/61/metablogapi/5228.image_2.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/CommunityServer-Blogs-Components-WeblogFiles/00-00-00-73-61-metablogapi/5228.image_5F00_2.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/prod.evol.blogs.technet.com/CommunityServer.Blogs.Components.WeblogFiles/00/00/00/73/61/metablogapi/6327.image_thumb.png" original-url="http://blogs.technet.com/cfs-file.ashx/__key/CommunityServer-Blogs-Components-WeblogFiles/00-00-00-73-61-metablogapi/6327.image_5F00_thumb.png" width="559" height="180" /></a></p>  <p>&#160;</p>  <p>D’après les premiers éléments recueillis, il s’agit d’un “flag” MAPI que le client Outlook positionne pour certaines connexions, dont ces connexions d’un utilisateur à un ou des calendriers partagés.</p>  <p>Voici l’article détaillant les opérations à réaliser si vos utilisateurs rencontrent des difficultés de connexion à des calendriers ou autres répertoires partagés à cause de la limite des 10 000 connections atteintes pour les instances “Exchange Administrator” :</p>  <p>Exchange Store Limits: Exchange 2010 Sp1 Help </p>  <p><a href="http://technet.microsoft.com/en-us/library/ff477612.aspx">http://technet.microsoft.com/en-us/library/ff477612.aspx</a> </p>  <p>1. Start Registry Editor (regedit). </p>  <p>2. Navigate to the following registry subkey:    <br /><b><a href="file:///\\HKEY_LOCAL_MACHINE">\\HKEY_LOCAL_MACHINE</a> \SYSTEM\CurrentControlSet\Services\MSExchangeIS\ParametersSystem</b>. </p>  <p>3. Right-click <b>ParametersSystem</b>, point to <b>New</b>, and then click <b>DWORD (32-bit) Value.</b> </p>  <p>4. Enter the following for the Value Name    <br />Value Name: <b>Maximum Allowed Exchange Sessions Per Service      <br /></b>Value Data: <b>25,000 </b>or whatever limit you want (Default when value is not present is 10,000). Maximum value is 65536     <br /><i>Note: The value data should be entered in Decimal.</i></p>