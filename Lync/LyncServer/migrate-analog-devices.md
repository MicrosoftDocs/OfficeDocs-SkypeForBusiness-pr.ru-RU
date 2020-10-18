---
title: Перенос аналоговых устройств
description: Перенос аналоговых устройств.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579405"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="14257-103">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="14257-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14257-104">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="14257-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="14257-105">Lync Server обеспечивает поддержку аналоговых устройств.</span><span class="sxs-lookup"><span data-stu-id="14257-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="14257-106">В частности, к поддерживаемым аналоговым устройствам относятся аналоговые телефоны и факсимильные аппараты.</span><span class="sxs-lookup"><span data-stu-id="14257-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="14257-107">Можно настроить квалифицированные шлюзы для поддержки использования аналоговых устройств в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14257-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="14257-108">После перехода с Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты Contact, связанные с аналоговыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="14257-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="14257-109">Используйте командную консоль Lync Server, чтобы сначала получить все объекты Contacts, связанные с аналоговыми устройствами Lync Server 2010, а затем переместить эти объекты в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14257-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="14257-110">Перенос аналоговых устройств</span><span class="sxs-lookup"><span data-stu-id="14257-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="14257-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="14257-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="14257-112">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="14257-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="14257-113">Убедитесь, что все объекты Contacts были перемещены в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14257-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="14257-114">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="14257-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="14257-115">Убедитесь, что все объекты Contact теперь связаны с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14257-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

