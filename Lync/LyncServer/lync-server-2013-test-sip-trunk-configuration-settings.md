---
title: 'Lync Server 2013: Проверка параметров конфигурации магистрали SIP'
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
ms.openlocfilehash: ba8abe19ed739783dc702686d630fb854ab9150a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a38d8-102">Проверка параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a38d8-102">Test SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a38d8-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a38d8-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a38d8-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="a38d8-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="a38d8-106">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="a38d8-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="a38d8-107">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="a38d8-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="a38d8-108">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="a38d8-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a38d8-109">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="a38d8-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a38d8-110">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="a38d8-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="a38d8-111">Администраторы также могут использовать командлет Test-CsTrunkConfiguration, чтобы проверить, может ли магистраль преобразовать номер, набранный пользователем, на номер, который может обрабатываться шлюзом.</span><span class="sxs-lookup"><span data-stu-id="a38d8-111">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="a38d8-112">Параметры конфигурации магистрали можно тестировать только с помощью Windows PowerShell и командлета [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a38d8-112">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet.</span></span> <span data-ttu-id="a38d8-113">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a38d8-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a38d8-114">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="a38d8-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="a38d8-115">Тестирование параметров конфигурации магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="a38d8-115">To test SIP trunk configuration settings</span></span>

  - <span data-ttu-id="a38d8-116">Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.</span><span class="sxs-lookup"><span data-stu-id="a38d8-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

