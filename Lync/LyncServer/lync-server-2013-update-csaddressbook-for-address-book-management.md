---
title: 'Lync Server 2013: Update-Ксаддрессбук для управления адресными книгами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e10f9d52d9e4090601330cad44d5da03e69540
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="6007c-102">Update-Ксаддрессбук для управления адресными книгами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6007c-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6007c-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6007c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6007c-104">Кто может запустить этот командлет: по умолчанию членам следующих групп разрешено выполнять командлет Update-Ксаддрессбук локально: Рткуниверсалусерадминс, Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="6007c-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="6007c-105">Чтобы возвратить список всех ролей управления доступом на основе ролей (RBAC), которые назначены этому командлету (включая любые пользовательские роли RBAC, созданные пользователем), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6007c-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="6007c-106">Командлет Update-Ксаддрессбук заменяет команду **абсервер. exe – синкнов** в Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="6007c-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="6007c-107">Цель командлета состоит в том, чтобы начать синхронизацию немедленно, вместо того чтобы ждать запланированного времени.</span><span class="sxs-lookup"><span data-stu-id="6007c-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="6007c-108">Первый пример команды обновляет все адресные книги в Организации.</span><span class="sxs-lookup"><span data-stu-id="6007c-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="6007c-109">Вторая обновляет только адресную книгу, связанную с определенным сервером.</span><span class="sxs-lookup"><span data-stu-id="6007c-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6007c-110">В Lync Server 2013 служба репликатора пользователей Lync Server выберет изменения из Active Directory и обновит базу данных пользователей Lync Server на основе заданного интервала.</span><span class="sxs-lookup"><span data-stu-id="6007c-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="6007c-111">Служба репликации пользователей Lync Server также будет автоматически распространять изменения базы данных Рткаб, не требуя администратора запускать Update-Ксаддрессбук.</span><span class="sxs-lookup"><span data-stu-id="6007c-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="6007c-112">Администраторам потребуется выполнить Update-Ксаддрессбук только в том случае, если разрешена загрузка файла адресной книги.</span><span class="sxs-lookup"><span data-stu-id="6007c-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="6007c-113">Например:</span><span class="sxs-lookup"><span data-stu-id="6007c-113">For example:</span></span>

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="6007c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6007c-114">See Also</span></span>


[<span data-ttu-id="6007c-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="6007c-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

