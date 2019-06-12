---
title: 'Lync Server 2013: Test-Ксаддрессбуквебкуери для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test-CsAddressBookWebQuery for Address Book management
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429716(v=OCS.15)
ms:contentKeyID: 48184865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c477c9c899847b1dec28fe70a9b749761dc43689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-csaddressbookwebquery-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="b1b46-102">Test-Ксаддрессбуквебкуери для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1b46-102">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1b46-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b1b46-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b1b46-104">Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет Test-Ксаддрессбуквебкуери: Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="b1b46-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Test-CsAddressBookWebQuery cmdlet: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="b1b46-105">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b1b46-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

<span data-ttu-id="b1b46-106">Аналогично виртуальной транзакции test-Ксаддрессбуксервице, Test-Ксаддрессбуквебкуери выполняет запрос в веб-запросе адресной книги, чтобы убедиться, что он работает правильно.</span><span class="sxs-lookup"><span data-stu-id="b1b46-106">Similar to the Test-CsAddressBookService synthetic transaction, Test-CsAddressBookWebQuery performs a query against the Address Book Web Query to ensure that it is operating properly.</span></span> <span data-ttu-id="b1b46-107">Командлет подключится к проверке подлинности веб-билета и отобразит учетные данные, указанные в – Усеркредентиал.</span><span class="sxs-lookup"><span data-stu-id="b1b46-107">The cmdlet will connect to the Web Ticket authentication and present the credentials specified in –UserCredential.</span></span> <span data-ttu-id="b1b46-108">Если прошедший проверку подлинности, командлет выдает сведения о – Таржетсипаддресс.</span><span class="sxs-lookup"><span data-stu-id="b1b46-108">If authenticated, the cmdlet then present the –TargetSipAddress information.</span></span> <span data-ttu-id="b1b46-109">Командлет должен сообщить об успешном завершении, если он смог получить информацию о контакте.</span><span class="sxs-lookup"><span data-stu-id="b1b46-109">The cmdlet should report success if it was able to retrieve the information about the contact.</span></span>

<span data-ttu-id="b1b46-110">Например:</span><span class="sxs-lookup"><span data-stu-id="b1b46-110">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

<div>

## <a name="see-also"></a><span data-ttu-id="b1b46-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b46-111">See Also</span></span>


[<span data-ttu-id="b1b46-112">Test-CsAddressBookWebQuery</span><span class="sxs-lookup"><span data-stu-id="b1b46-112">Test-CsAddressBookWebQuery</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

