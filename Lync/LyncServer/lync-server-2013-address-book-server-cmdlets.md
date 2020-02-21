---
title: 'Lync Server 2013: Командлеты сервера адресной книги'
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
ms.openlocfilehash: e35106634d9ad9dbc8c4a044aad42d50081cd1e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="bb3f0-102">Командлеты сервера адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb3f0-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb3f0-103">_**Последнее изменение темы:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="bb3f0-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="bb3f0-104">Серверы адресной книги являются посредниками между доменными службами Active Directory и Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="bb3f0-105">Сервер адресной книги обеспечивает синхронизацию сведений о пользователях, хранящихся в Lync Server 2013, с информацией о пользователях, хранящейся в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="bb3f0-106">Для этого файлы адресной книги периодически синхронизируются с данными, хранящимися в пользовательской базе данных.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="bb3f0-107">В свою очередь, Lync Server включает ряд командлетов для управления серверами адресной книги.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="bb3f0-108">Address Book Server Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bb3f0-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="bb3f0-109">Параметры сервера адресной книги невозможно настроить в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="bb3f0-110">Windows PowerShell — это основное средство для управления этими параметрами.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="bb3f0-111">Ниже приведен список командлетов, которые непосредственно связаны с управлением серверами адресной книги.</span><span class="sxs-lookup"><span data-stu-id="bb3f0-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="bb3f0-112">**Сервер адресной книги**</span><span class="sxs-lookup"><span data-stu-id="bb3f0-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="bb3f0-113">[Get — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bb3f0-114">[New — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bb3f0-115">[Remove — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="bb3f0-116">[Set — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bb3f0-117">[Update — CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bb3f0-118">[Debug — CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bb3f0-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="bb3f0-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bb3f0-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb3f0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="bb3f0-121">See Also</span></span>


[<span data-ttu-id="bb3f0-122">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb3f0-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

