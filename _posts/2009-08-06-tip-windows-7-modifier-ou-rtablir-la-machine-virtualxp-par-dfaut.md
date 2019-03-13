---
layout: post
title: Tip – Windows 7 – modifier ou rétablir la machine VirtualXP par défaut
date: 2009-08-06 09:31
author: sammykrosoft
comments: true
categories: [Uncategorized]
---
<p>Pour réassocier le menu Virtual Windows XP à la bonne machine virtuelle Windows XP (bouton Démarrer –&gt; Windows Virtual PC –&gt; Virtual Windows XP) :</p>  <p>&#160;</p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_6.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_6.png"><img style="border-bottom: 0px; border-left: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_2.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_2.png" width="244" height="136" /></a>&#160;<em>Note : ce menu est associé à l’appel de la commande “%SystemRoot%\system32\rundll32.exe %SystemRoot%\system32\VMCPropertyHandler.dll,LaunchDefaultVM”. la propriété LaunchDefaultVM ne fait pas appel à une valeur de la base de registres comme j’ai moi-même pu le croire, mais à une valeur du fichier options.xml auquel nous allons accéder ci-dessous …</em></p>  <p>Allez dans le répertoire %localAppData%\Microsoft\Windows Virtual PC\</p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_8.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_8.png"><img style="border-bottom: 0px; border-left: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_3.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_3.png" width="519" height="197" /></a> </p>  <p>&#160;</p>  <p>Ouvrir le fichier “<strong>Options.xml</strong>” puis rechercher et modifier si besoin:</p>  <p>1- le tag “<strong>&lt;defaults&gt;</strong>” pour les informations de configuration</p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_4.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_4.png"><img style="border-bottom: 0px; border-left: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_1.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_1.png" width="634" height="96" /></a> </p>  <p>2- le tag “<strong>&lt;default_vm&gt;</strong>”, et donnez-lui le nom de la machine virtuelle Windows XP à mettre par défaut :</p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_2.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_2.png"><img style="border-bottom: 0px; border-left: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb.png" width="561" height="46" /></a> </p>  <p><em>Note : ce nom de machine virtuelle correspond simplement au nom de votre machine VirtualXP (<u>sans le vmcx</u>) que vous trouvez dans le répertoire de votre profil %useprofile%\Virtual Machines :</em></p>  <p><a href="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_10.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_10.png"><img style="border-bottom: 0px; border-left: 0px; display: block; float: none; margin-left: auto; border-top: 0px; margin-right: auto; border-right: 0px" title="image" border="0" alt="image" src="https://msdnshared.blob.core.windows.net/media/TNBlogsFS/BlogFileStorage/blogs_technet/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_4.png" original-url="http://blogs.technet.com/blogfiles/samdrey/WindowsLiveWriter/TipWindows7modifierourtablirlamachineVir_DA3C/image_thumb_4.png" width="627" height="121" /></a></p>