---
title: 'Lync Server 2013: командлеты Windows PowerShell для управления адресной книгой'
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
ms.openlocfilehash: 69af5cc5bc9279b1be748cb9a38477ea6d0f3aa6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="5e368-102">Командлеты Windows PowerShell для служб адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e368-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5e368-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5e368-104">Lync Server предоставляет несколько командлетов интерфейса командной строки Windows PowerShell для управления и настройки службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="5e368-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="5e368-105">Некоторые из этих командлетов представляют собой замены для команд ABServer. exe, используемых в предыдущих версиях Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="5e368-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="5e368-106">В следующих разделах описываются командлеты, используемые для задания, создания и извлечения сведений о службе адресной книги, ее настройках, а также сведений о веб-службах, которые используются службой адресной книги при извлечении клиентами ее файлов и параметров.</span><span class="sxs-lookup"><span data-stu-id="5e368-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="5e368-107">Все эти командлеты выдаются с помощью командной консоли Lync Server, которую можно найти в средствах Lync Server на сервере или рабочей станции, на которых установлены средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="5e368-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5e368-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="5e368-108">In This Section</span></span>

  - [<span data-ttu-id="5e368-109">New – CsAddressBookConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-110">Set – CsAddressBookConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-111">Get – CsAddressBookConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-112">Remove – CsAddressBookConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-113">Test-CsAddressBookService для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="5e368-114">Test-CsAddressBookWebQuery для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="5e368-115">Update — CsAddressBook для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="5e368-116">New – CsClientPolicy для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="5e368-117">Set – CsClientPolicy для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="5e368-118">Get – CsService для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="5e368-119">New – CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-120">Get – CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-121">Set – CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="5e368-122">Remove – CsWebServiceConfiguration для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e368-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="5e368-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5e368-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e368-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5e368-124">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

