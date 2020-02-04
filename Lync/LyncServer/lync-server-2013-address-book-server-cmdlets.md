---
title: 'Lync Server 2013: командлеты адресной книги сервера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5117b7a17d607ec995df371fd0cd80fd7c05aeab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="cb9ba-102">Командлеты сервера адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9ba-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb9ba-103">_**Тема последнего изменения:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="cb9ba-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="cb9ba-104">Серверы адресной книги являются посредниками между доменными службами Active Directory и Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cb9ba-105">Сервер адресной книги обеспечивает синхронизацию сведений о пользователях, хранящихся в Lync Server 2013, с информацией о пользователе, хранящейся в службе каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="cb9ba-106">Это можно сделать, периодически синхронизируя файлы адресной книги с данными, хранящимися в базе данных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="cb9ba-107">В свою очередь, Lync Server включает несколько командлетов для управления серверами адресной книги.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="cb9ba-108">Командлеты сервера адресной книги</span><span class="sxs-lookup"><span data-stu-id="cb9ba-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="cb9ba-109">Вы не можете настроить параметры сервера адресной книги на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="cb9ba-110">Windows PowerShell — это основной инструмент для управления этими параметрами.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="cb9ba-111">Ниже приведен список командлетов, непосредственно связанных с администрированием сервера адресной книги.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="cb9ba-112">**адресной книги**</span><span class="sxs-lookup"><span data-stu-id="cb9ba-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="cb9ba-113">[Get-Ксаддрессбукконфигуратион](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cb9ba-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cb9ba-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cb9ba-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cb9ba-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-117">[Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cb9ba-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cb9ba-119">[Test-Ксаддрессбуксервице](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-119">[Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cb9ba-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cb9ba-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb9ba-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cb9ba-121">See Also</span></span>


[<span data-ttu-id="cb9ba-122">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb9ba-122">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

