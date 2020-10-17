---
title: 'Lync Server 2013: командлеты конфигурации магистрали'
description: 'Lync Server 2013: командлеты конфигурации магистрали.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4df1c60455275a87b85cb0b0d14f91e58436c80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548895"
---
# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a><span data-ttu-id="267f7-103">Командлеты настройки магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="267f7-103">Trunking configuration cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="267f7-104">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="267f7-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="267f7-p101">С помощью командлетов конфигурации распределения каналов определяются параметры для объекта кэширующего узла распределения каналов, такого как шлюз телефонной сети общего пользования (ТСОП), УАТС или УАТС на базе протокола IP или пограничный контроллер сеансов у поставщика услуг. Эти параметры определяют, включен ли обход сервера-посредника для этой магистрали, налагаются ли на отправку пакетов протокола RTCP определенные условия и необходимо ли требовать шифрование протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="267f7-p101">Trunk configuration cmdlets are used to define settings for a trunking peer entity such as a public switched telephone network (PSTN) gateway, IP-public branch exchange (PBX), or Session Border Controller (SBC) at the service provider. These settings configure such things as whether media bypass is enabled on this trunk, whether real-time transport control protocol (RTCP) packets are sent under certain conditions, and whether to require secure real-time protocol (SRTP) encryption.</span></span>

<div>

## <a name="trunking-configuration-cmdlets"></a><span data-ttu-id="267f7-107">Командлеты конфигурации распределения каналов</span><span class="sxs-lookup"><span data-stu-id="267f7-107">Trunking Configuration Cmdlets</span></span>

<span data-ttu-id="267f7-108">Для конфигурации распределения каналов используйте следующие командлеты.</span><span class="sxs-lookup"><span data-stu-id="267f7-108">Use the following cmdlets for trunk configuration.</span></span>

<span data-ttu-id="267f7-109">**Конфигурация распределения каналов**</span><span class="sxs-lookup"><span data-stu-id="267f7-109">**Trunking Configuration**</span></span>

  - <span data-ttu-id="267f7-110">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-110">[Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="267f7-111">[Get — CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-111">[Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))</span></span>

  - <span data-ttu-id="267f7-112">[New — CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-112">[New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))</span></span>

  - <span data-ttu-id="267f7-113">[Remove — CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-113">[Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))</span></span>

  - <span data-ttu-id="267f7-114">[Set — CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-114">[Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="267f7-115">[Get — CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-115">[Get-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-116">[New — CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-116">[New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-117">[Remove — CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-117">[Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-118">[Set — CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-118">[Set-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="267f7-119">[Get — CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-119">[Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="267f7-120">[Get — CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-120">[Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-121">[New — CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-121">[New-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-122">[Remove — CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-122">[Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-123">[Set — CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-123">[Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="267f7-124">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-124">[Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="267f7-125">[New — Ксвоицережекс](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="267f7-125">[New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="267f7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="267f7-126">See Also</span></span>


[<span data-ttu-id="267f7-127">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="267f7-127">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

