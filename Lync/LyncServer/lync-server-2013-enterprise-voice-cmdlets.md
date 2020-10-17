---
title: 'Lync Server 2013: командлеты корпоративной голосовой связи'
description: 'Lync Server 2013: командлеты корпоративной голосовой связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447876de74a63e1def03f41bca512d57c46daf91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558435"
---
# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0ed78-103">Командлеты корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ed78-103">Enterprise Voice cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ed78-104">_**Последнее изменение темы:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="0ed78-104">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="0ed78-105">Корпоративная голосовая связь — это реализация Майкрософт протокола VoIP.</span><span class="sxs-lookup"><span data-stu-id="0ed78-105">Enterprise Voice is the Microsoft implementation of Voice over IP (VoIP).</span></span> <span data-ttu-id="0ed78-106">Командлеты, доступные для управления корпоративной голосовой связью в Microsoft Lync Server 2013, позволяют создавать и изменять абонентские группы (ранее называемые профилями местонахождения), политики голосовой связи, маршруты и правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="0ed78-106">The cmdlets available for managing Enterprise Voice in Microsoft Lync Server 2013 will allow you to create and modify dial plans (formerly known as location profiles), voice policies, routes, and normalization rules.</span></span>

<div>

## <a name="enterprise-voice-cmdlets"></a><span data-ttu-id="0ed78-107">Командлеты корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="0ed78-107">Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="0ed78-108">Большинство задач управления, применяемых к корпоративной голосовой связи, можно выполнить на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ed78-108">Most management tasks that apply to Enterprise Voice can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="0ed78-109">Эти же задачи можно выполнить с помощью командлетов из командной консоли Lync Server или из скрипта, что позволяет автоматизировать некоторые задачи.</span><span class="sxs-lookup"><span data-stu-id="0ed78-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script, allowing you to automate certain tasks.</span></span> <span data-ttu-id="0ed78-110">Далее приводится список командлетов, относящихся непосредственно к управлению корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="0ed78-110">The following is a list of cmdlets that relate directly to managing Enterprise Voice:</span></span>

<span data-ttu-id="0ed78-111">**[Устранение неполадок командлетов корпоративной голосовой связи в Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0ed78-111">**[Troubleshooting Enterprise Voice cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-112">[Get — Ксвоицеконфигуратион](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-112">[Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-113">[Remove — Ксвоицеконфигуратион](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-113">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-114">[Set — Ксвоицеконфигуратион](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-114">[Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-115">[Get — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-115">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-116">[New — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-116">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-117">[Remove — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-117">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-118">[Set — CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-118">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-119">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-119">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-120">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-120">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-121">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-121">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-122">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-122">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-123">[Test-Ксвоицерауте](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-123">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-124">[Test-Ксвоицеусер](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-124">[Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))</span></span>

<span data-ttu-id="0ed78-125">**[Командлеты правил нормализации голосовой связи в Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0ed78-125">**[Voice normalization rules cmdlets in Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-126">[Get — CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-126">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-127">[New — CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-127">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-128">[Remove — CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-128">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-129">[Set — CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-129">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-130">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-130">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-131">[New — Ксвоицережекс](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-131">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="0ed78-132">**[Командлеты политики голосовой связи в Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0ed78-132">**[Voice policy cmdlets in Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-133">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-133">[Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-134">[Granting — CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-134">[Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-135">[New — CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-135">[New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-136">[Remove — CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-136">[Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-137">[Set — CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-137">[Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-138">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-138">[Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-139">[Get — Кспстнусаже](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-139">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-140">[Set — Кспстнусаже](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-140">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-141">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-141">[Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-142">[Granting — CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-142">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-143">[New — CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-143">[New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-144">[Remove — CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-144">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-145">[Set — CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-145">[Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-146">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-146">[Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))</span></span>

<span data-ttu-id="0ed78-147">**[Командлеты маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0ed78-147">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-148">[Get — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-148">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-149">[New — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-149">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-150">[Remove — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-150">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-151">[Set — Ксраутингконфигуратион](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-151">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0ed78-152">[Get — Ксвоицерауте](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-152">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-153">[New — Ксвоицерауте](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-153">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-154">[Remove — Ксвоицерауте](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-154">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-155">[Set — Ксвоицерауте](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-155">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0ed78-156">[Test-Ксвоицерауте](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0ed78-156">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ed78-157">См. также</span><span class="sxs-lookup"><span data-stu-id="0ed78-157">See Also</span></span>


[<span data-ttu-id="0ed78-158">Дополнительные командлеты корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ed78-158">Advanced Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="0ed78-159">Командлеты голосовых приложений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ed78-159">Voice application cmdlets in Lync Server 2013</span></span>](lync-server-2013-voice-application-cmdlets.md)  


[<span data-ttu-id="0ed78-160">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ed78-160">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

