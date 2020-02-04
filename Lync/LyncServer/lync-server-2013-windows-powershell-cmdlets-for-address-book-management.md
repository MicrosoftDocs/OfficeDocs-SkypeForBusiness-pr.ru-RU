---
title: 'Lync Server 2013: командлеты Windows PowerShell для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ec10f3e3d3d58a790ddc60fd1af1d1b09765685
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="b6e05-102">Командлеты Windows PowerShell для служб адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6e05-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b6e05-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b6e05-104">Lync Server предоставляет несколько командлетов интерфейса командной строки Windows PowerShell для управления и настройки службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="b6e05-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="b6e05-105">Некоторые из этих командлетов являются заменой для команд Абсервер. exe, используемых в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="b6e05-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="b6e05-106">В следующих разделах приведены командлеты, которые используются для задания, создания и получения сведений о службе адресной книги, ее конфигурации и сведения о веб-службах, которые используются службой адресной книги для получения доступа к службе адресной книги. файлы и параметры.</span><span class="sxs-lookup"><span data-stu-id="b6e05-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="b6e05-107">Все эти командлеты выдаются в командной консоли Lync Server Management Shell, которую можно найти на сервере или на рабочей станции, где установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="b6e05-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b6e05-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="b6e05-108">In This Section</span></span>

  - [<span data-ttu-id="b6e05-109">New-Ксаддрессбукконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-110">Set-Ксаддрессбукконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-111">Get-Ксаддрессбукконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-112">Remove-Ксаддрессбукконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-113">Test-Ксаддрессбуксервице для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-114">Test-Ксаддрессбуквебкуери для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-115">Update-Ксаддрессбук для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-116">New-CsClientPolicy для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-117">Set-CsClientPolicy для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-118">Get-Кссервице для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-119">New-Ксвебсервицеконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-120">Get-Ксвебсервицеконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-121">Set-Ксвебсервицеконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="b6e05-122">Remove-Ксвебсервицеконфигуратион для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6e05-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="b6e05-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b6e05-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b6e05-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b6e05-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

