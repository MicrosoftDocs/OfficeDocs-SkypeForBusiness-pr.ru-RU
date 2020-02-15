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
ms.openlocfilehash: c7abaa29d2383f80a6f822eaa5d524197996500b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="87bee-102">Миграция телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="87bee-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87bee-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="87bee-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="87bee-104">Телефоны общего пользования — это IP-телефоны, находящиеся обычно в общих рабочих помещениях или местах общего пользования, таких как вестибюли, кухни или заводские цеха.</span><span class="sxs-lookup"><span data-stu-id="87bee-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="87bee-105">Для предоставления функций UC для Lync Server не требуется подключение к компьютеру телефонов.</span><span class="sxs-lookup"><span data-stu-id="87bee-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="87bee-106">После переноса развертывания Lync Server 2010 на Lync Server 2013 необходимо также перенести объекты Contact, связанные с устаревшим стандартным телефоном.</span><span class="sxs-lookup"><span data-stu-id="87bee-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="87bee-107">С помощью командной консоли Lync Server вы сначала получите все объекты Contacts, связанные с телефонами Lync Server 2010 с общими областями, а затем переместите эти объекты в пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87bee-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="87bee-108">**Миграция телефонов общего пользования**</span><span class="sxs-lookup"><span data-stu-id="87bee-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="87bee-109">На сервере переднего плана Lync Server 2013 откройте консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="87bee-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="87bee-110">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="87bee-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="87bee-111">Чтобы убедиться, что все объекты Contact были перемещены в пул Lync Server 2013, в командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="87bee-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="87bee-112">Убедитесь, что все объекты Contact теперь связаны с пулом Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87bee-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

