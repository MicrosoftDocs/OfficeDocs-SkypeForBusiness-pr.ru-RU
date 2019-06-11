---
title: Перенос аналоговых устройств
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="baf84-102">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="baf84-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baf84-103">_**Тема последнего изменения:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="baf84-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="baf84-104">Lync Server обеспечивает поддержку аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="baf84-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="baf84-105">В частности, поддерживаются аналоговые устройства аналогового и аналогового факсимильного аппарата.</span><span class="sxs-lookup"><span data-stu-id="baf84-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="baf84-106">Вы можете настроить полные шлюзы для поддержки использования аналоговых устройств в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="baf84-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="baf84-107">После перехода с Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты контактов, связанные с аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="baf84-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="baf84-108">Используйте командную консоль Lync Server Management Shell, чтобы сначала получить все объекты контактов, связанные с аналоговыми устройствами Lync Server 2010, а затем переместить эти объекты в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf84-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="baf84-109">Миграция аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="baf84-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="baf84-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="baf84-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="baf84-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="baf84-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="baf84-112">Убедитесь, что все объекты контакта были перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf84-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="baf84-113">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="baf84-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="baf84-114">Убедитесь, что все объекты контакта теперь связаны с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="baf84-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

