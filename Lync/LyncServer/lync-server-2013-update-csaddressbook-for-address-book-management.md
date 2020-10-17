---
title: 'Lync Server 2013: Update-CsAddressBook для управления адресной книгой'
description: 'Lync Server 2013: Update-CsAddressBook для управления адресной книгой.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4adc7f94e2f31f64f6517b8cdf9bbcb0649f6c8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546245"
---
# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3700f-103">Update-CsAddressBook для управления адресной книгой в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3700f-103">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3700f-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3700f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3700f-p101">Кто может запускать данный командлет: по умолчанию членам следующих групп разрешено локально запускать командлет Update-CsAddressBook — RTCUniversalUserAdmins, RTCUniversalServerAdmins. Чтобы возвратить список всех ролей управления доступом на основе ролей, которым был назначен данный командлет (включая любые настраиваемые роли управления доступом на основе ролей, созданные лично вами), выполните следующую команду из командной строки Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3700f-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="3700f-p102">Командлет Update-CsAddressBook заменяет собой команду **abserver.exe –syncNow** из Office Communications Server. Задача этого командлета — запустить синхронизацию немедленно, не ожидая запланированного времени. Первый пример команды обновляет все адресные книги в организации. Второй пример обновляет только адресную книгу, сопоставленную с заданным сервером.</span><span class="sxs-lookup"><span data-stu-id="3700f-p102">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server. The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time. The first example command updates all Address Books in the organization. The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3700f-111">В Lync Server 2013 служба репликации пользователей Lync Server выберет изменения из Active Directory и обновляет базу данных пользователей Lync Server в соответствии с заданным интервалом.</span><span class="sxs-lookup"><span data-stu-id="3700f-111">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="3700f-112">Служба Replicator пользователей Lync Server также будет быстро распространять изменения базы данных RTCab, не требуя от администратора выполнять командлет Update – CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="3700f-112">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="3700f-113">Администраторы должны будут запустить Update -CSAddressBook только в случае, когда включена загрузка файла адресной книги.</span><span class="sxs-lookup"><span data-stu-id="3700f-113">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="3700f-114">Например:</span><span class="sxs-lookup"><span data-stu-id="3700f-114">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="3700f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3700f-115">See Also</span></span>


[<span data-ttu-id="3700f-116">Update — CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="3700f-116">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

