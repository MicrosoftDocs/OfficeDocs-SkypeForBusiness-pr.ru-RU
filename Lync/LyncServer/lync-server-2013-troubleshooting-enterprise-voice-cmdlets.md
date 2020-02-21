---
title: 'Lync Server 2013: Устранение неполадок с командлетами корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Enterprise Voice cmdlets
ms:assetid: 28ec32d2-6d1e-40e6-b2a8-065803288e8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415638(v=OCS.15)
ms:contentKeyID: 48183697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc8bceaed6b94c4555b20f67be9e783765040ba8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="90b69-102">Устранение неполадок командлетов корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90b69-102">Troubleshooting Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90b69-103">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="90b69-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="90b69-104">Настройка корпоративной голосовой связи в рамках реализации Microsoft Lync Server 2013 включает в себя создание маршрутов, политик и правил, которые должны работать вместе, чтобы обеспечить выполнение входящих и исходящих вызовов должным образом.</span><span class="sxs-lookup"><span data-stu-id="90b69-104">Setting up Enterprise Voice as part of your Microsoft Lync Server 2013 implementation involves creating routes, policies and rules that must all work together to ensure incoming and outgoing calls are completed as expected.</span></span> <span data-ttu-id="90b69-105">Командная консоль Lync Server включает командлеты, которые можно использовать для тестирования подключений и путей, а также для устранения неполадок, которые могут возникнуть во время реализации.</span><span class="sxs-lookup"><span data-stu-id="90b69-105">Lync Server Management Shell includes cmdlets that can be used to test connections and paths and to troubleshoot issues that may arise during implementation.</span></span>

<div>

## <a name="troubleshooting-enterprise-voice-cmdlets"></a><span data-ttu-id="90b69-106">Командлеты для устранения неполадок корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="90b69-106">Troubleshooting Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="90b69-107">Для тестирования и устранения неполадок подключений корпоративной голосовой связи можно использовать следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="90b69-107">The following cmdlets can be used to test and troubleshoot Enterprise Voice connections.</span></span>

<span data-ttu-id="90b69-108">**Командлеты для устранения неполадок корпоративной голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="90b69-108">**Troubleshooting Enterprise Voice Cmdlets**</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-109">[Get — Ксвоицеконфигуратион](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-109">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-110">[Remove — Ксвоицеконфигуратион](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-110">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-111">[Set — Ксвоицеконфигуратион](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-111">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90b69-112">[Get — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-112">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-113">[New — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-113">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-114">[Remove — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-114">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-115">[Set — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-115">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="90b69-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-116">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90b69-117">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-117">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90b69-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-118">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90b69-119">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-119">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90b69-120">[Test-Ксвоицерауте](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-120">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="90b69-121">[Test-Ксвоицеусер](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="90b69-121">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90b69-122">См. также</span><span class="sxs-lookup"><span data-stu-id="90b69-122">See Also</span></span>


[<span data-ttu-id="90b69-123">Командлеты корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90b69-123">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="90b69-124">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="90b69-124">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

