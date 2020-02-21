---
title: Перенос аналоговых устройств
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc1c3420c22f4cc58bd0e617fd9ba98e16102c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="6c4c0-102">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="6c4c0-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c4c0-103">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="6c4c0-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6c4c0-104">Lync Server обеспечивает поддержку аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="6c4c0-105">В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="6c4c0-106">Можно настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="6c4c0-107">После перехода с Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты Contact, связанные с аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="6c4c0-108">Используйте командную консоль Lync Server, чтобы сначала получить все объекты Contacts, связанные с аналоговыми устройствами Lync Server 2010, а затем переместить эти объекты в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="6c4c0-109">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="6c4c0-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="6c4c0-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6c4c0-111">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="6c4c0-112">Убедитесь, что все объекты Contacts были перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="6c4c0-113">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="6c4c0-114">Убедитесь, что все объекты Contact теперь связаны с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c4c0-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

