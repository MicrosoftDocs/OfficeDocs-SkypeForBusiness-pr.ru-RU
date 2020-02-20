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
ms.openlocfilehash: fe9a7462edb8df2741a8c783cff17e62bfe848eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="cef89-102">Командлеты сервера адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cef89-102">Address Book Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cef89-103">_**Последнее изменение темы:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="cef89-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="cef89-104">Серверы адресной книги являются посредниками между доменными службами Active Directory и Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cef89-104">Address Book servers are intermediaries between Active Directory Domain Services and Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cef89-105">Сервер адресной книги обеспечивает синхронизацию сведений о пользователях, хранящихся в Lync Server 2013, с информацией о пользователях, хранящейся в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cef89-105">The Address Book server ensures that the user information stored in Lync Server 2013 is in synch with the user information stored in Active Directory.</span></span> <span data-ttu-id="cef89-106">Для этого файлы адресной книги периодически синхронизируются с данными, хранящимися в пользовательской базе данных.</span><span class="sxs-lookup"><span data-stu-id="cef89-106">This is done by periodically synching Address Book files with information stored in the User database.</span></span> <span data-ttu-id="cef89-107">В свою очередь, Lync Server включает ряд командлетов для управления серверами адресной книги.</span><span class="sxs-lookup"><span data-stu-id="cef89-107">In turn, Lync Server includes a number of cmdlets for managing Address Book servers.</span></span>

<div>

## <a name="address-book-server-cmdlets"></a><span data-ttu-id="cef89-108">Address Book Server Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cef89-108">Address Book Server Cmdlets</span></span>

<span data-ttu-id="cef89-109">Параметры сервера адресной книги невозможно настроить в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cef89-109">You cannot configure the Address Book Server settings in Lync Server Control Panel.</span></span> <span data-ttu-id="cef89-110">Windows PowerShell — это основное средство для управления этими параметрами.</span><span class="sxs-lookup"><span data-stu-id="cef89-110">Windows PowerShell is the primary tool for managing these settings.</span></span> <span data-ttu-id="cef89-111">Ниже приведен список командлетов, которые непосредственно связаны с управлением серверами адресной книги.</span><span class="sxs-lookup"><span data-stu-id="cef89-111">The following is a list of cmdlets that relate directly to managing the Address Book Server:</span></span>

<span data-ttu-id="cef89-112">**Сервер адресной книги**</span><span class="sxs-lookup"><span data-stu-id="cef89-112">**Address Book Server**</span></span>

  - <span></span>  
    <span data-ttu-id="cef89-113">[Get — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-113">[Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cef89-114">[New — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-114">[New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cef89-115">[Remove — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-115">[Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cef89-116">[Set — CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-116">[Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cef89-117">[Update — CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-117">[Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cef89-118">[Debug — CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-118">[Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cef89-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-119">[Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cef89-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cef89-120">[Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cef89-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cef89-121">See Also</span></span>


[<span data-ttu-id="cef89-122">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="cef89-122">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

