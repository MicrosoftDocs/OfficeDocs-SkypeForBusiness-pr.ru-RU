---
title: 'Lync Server 2013: командлеты веб-сервера и служб'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web server and services cmdlets
ms:assetid: 07ce7fd4-4068-4957-9cb9-fd121b43858c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415631(v=OCS.15)
ms:contentKeyID: 48183326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f9a5fccbf3cf420f5fefa35b0efa30e55fe517f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-server-and-services-cmdlets-in-lync-server-2013"></a><span data-ttu-id="db873-102">Командлеты веб-сервера и служб в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db873-102">Web server and services cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db873-103">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="db873-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="db873-104">Многие компоненты Microsoft Lync Server 2013 основаны на Интернете: эти компоненты используют веб-службы или веб-страницы для выполнения своих задач.</span><span class="sxs-lookup"><span data-stu-id="db873-104">Many Microsoft Lync Server 2013 components are web-based: these components either use Web Services or webpages to carry out their tasks.</span></span> <span data-ttu-id="db873-105">Командлеты веб-сервера и веб-служб позволяют выполнять такие действия, как Настройка параметров веб-сервера и управление простыми URL-адресами.</span><span class="sxs-lookup"><span data-stu-id="db873-105">The Web Server and Web services cmdlets enable you to do such things as configure Web Server settings and to manage simple URLs.</span></span> <span data-ttu-id="db873-106">Простые URL-адреса упрощают для пользователей присоединение к собраниям и конференциям, а также упрощают для администраторов вход в панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db873-106">Simple URLs make it easier for users to join meetings and conferences, and make it easier for Administrators to log on to the Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="web-server-and-web-services-cmdlets"></a><span data-ttu-id="db873-107">Командлеты веб-сервера и веб-служб</span><span class="sxs-lookup"><span data-stu-id="db873-107">Web Server and Web Services Cmdlets</span></span>

<span data-ttu-id="db873-108">Ниже приведен список командлетов, которые относятся непосредственно к управлению веб-серверами и веб-службами.</span><span class="sxs-lookup"><span data-stu-id="db873-108">The following is a list of cmdlets that relate directly to managing Web Servers and Web Services:</span></span>

<span data-ttu-id="db873-109">**Веб-серверы и службы**</span><span class="sxs-lookup"><span data-stu-id="db873-109">**Web Servers and Services**</span></span>

  - <span></span>  
    <span data-ttu-id="db873-110">[New — Кссимплеурл](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-110">[New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-111">[Get — CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-111">[Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-112">[New — CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-112">[New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-113">[Remove — CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-113">[Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-114">[Set — CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-114">[Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-115">[New — CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-115">[New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-116">[New — Ксвеборигин](https://technet.microsoft.com/library/JJ950236(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-116">[New-CsWebOrigin](https://technet.microsoft.com/library/JJ950236(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-117">[Set — Ксвебсервер](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-117">[Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-118">[Get — CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-118">[Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-119">[New — CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-119">[New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-120">[Remove — CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-120">[Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-121">[Set — CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-121">[Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-122">[New — Ксвебтрустедкацертификате](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-122">[New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-123">[New — CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-123">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-124">[Get — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-124">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-125">[New — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-125">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-126">[Remove — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-126">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-127">[Set — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-127">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="db873-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-128">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="db873-129">[Set — Кскерберосаккаунтпассворд](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-129">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="db873-130">[Test-Ксвебапп](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-130">[Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))</span></span>

  - <span data-ttu-id="db873-131">[Test-Ксвебаппанонимаус](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="db873-131">[Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db873-132">См. также</span><span class="sxs-lookup"><span data-stu-id="db873-132">See Also</span></span>


[<span data-ttu-id="db873-133">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="db873-133">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

