---
title: 'Lync Server 2013: Проверка параметров конфигурации магистрали SIP'
description: 'Lync Server 2013: Проверка параметров конфигурации магистрали SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44fe2ef5123bec31fafaff2d811a501e5cca4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558275"
---
# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="89ce0-103">Проверка параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89ce0-103">Test SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89ce0-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="89ce0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="89ce0-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="89ce0-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="89ce0-107">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="89ce0-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="89ce0-108">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="89ce0-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="89ce0-109">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="89ce0-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="89ce0-110">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="89ce0-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="89ce0-111">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="89ce0-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="89ce0-112">Кроме того, администраторы могут использовать командлет Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать номер, набранный пользователем, на номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="89ce0-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="89ce0-113">Параметры конфигурации магистрали можно тестировать только с помощью Windows PowerShell и командлета [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="89ce0-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="89ce0-114">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89ce0-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89ce0-115">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="89ce0-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="89ce0-116">Тестирование параметров конфигурации магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="89ce0-116">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="89ce0-117">Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="89ce0-117">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

