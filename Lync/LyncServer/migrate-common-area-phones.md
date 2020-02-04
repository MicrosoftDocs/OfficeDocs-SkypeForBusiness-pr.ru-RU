---
title: Миграция телефонов общего пользования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="5e7ef-102">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="5e7ef-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e7ef-103">_**Тема последнего изменения:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5e7ef-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5e7ef-104">Обычные телефоны — это IP-телефоны, которые чаще всего находятся в общей рабочей области или в общей области, например в зале ожидания, кухни или фабрики.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="5e7ef-105">Для обеспечения функций UC для Lync Server не нужно подключаться к компьютеру с помощью обычных телефонов.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="5e7ef-106">После миграции развертывания Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты контактов, связанные с устаревшим стандартным телефоном.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="5e7ef-107">С помощью командной консоли Lync Server вы сначала получите все объекты контактов, связанные с Lync Server 2010 Common Area Phone, а затем переместите эти объекты в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="5e7ef-108">**Миграция телефонов общего пользования**</span><span class="sxs-lookup"><span data-stu-id="5e7ef-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="5e7ef-109">На сервере переднего плана Lync Server 2013 откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="5e7ef-110">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5e7ef-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="5e7ef-111">Чтобы убедиться в том, что все объекты контакта были перемещены в пул Lync Server 2013, в командной консоли Lync Server Management Shell введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5e7ef-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="5e7ef-112">Убедитесь, что все объекты контакта теперь связаны с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7ef-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

