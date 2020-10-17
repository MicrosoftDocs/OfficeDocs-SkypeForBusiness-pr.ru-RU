---
title: 'Lync Server 2013: Test-CsAddressBookWebQuery для управления адресной книгой'
description: 'Lync Server 2013: Test-CsAddressBookWebQuery для управления адресной книгой.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7448733ed1477d36b887648154d66c96f9e6d0b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547445"
---
# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="11fc3-103">Test-CsAddressBookWebQuery для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11fc3-103">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11fc3-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="11fc3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="11fc3-p101">По умолчанию право на запуск командлета Test-CsAddressBookWebQuery имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей управления доступом на основе ролей (RBAC), которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните в командной строке Windows PowerShell следующую команду.</span><span class="sxs-lookup"><span data-stu-id="11fc3-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="11fc3-p102">Как и для синтетической транзакции test-CsAddressBookService, Test-CsAddressBookWebQuery выполняет запрос для веб-запроса адресной книги, чтобы убедиться, что он работает должным образом. Командлет подключается компоненту проверки подлинности веб-билета и указывает учетные данные, заданные в параметре -UserCredential. Если проверка подлинности пройдена, этот командлет затем отображает информацию -TargetSipAddress. Командлет должен сообщать об успехе, если ему удалось извлечь информацию о контакте.</span><span class="sxs-lookup"><span data-stu-id="11fc3-p102">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly. The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential. If authenticated, the cmdlet then present the –TargetSipAddress information. The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="11fc3-111">Например:</span><span class="sxs-lookup"><span data-stu-id="11fc3-111">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="11fc3-112">См. также</span><span class="sxs-lookup"><span data-stu-id="11fc3-112">See Also</span></span>


[<span data-ttu-id="11fc3-113">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="11fc3-113">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

