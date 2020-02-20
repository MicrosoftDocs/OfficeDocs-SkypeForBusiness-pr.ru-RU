---
title: 'Lync Server 2013: делегирование административного управления Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74089690a9c37a753d9dad56fd7246f9d4cb6213
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="74963-102">Делегирование административного управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74963-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74963-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="74963-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="74963-104">В Lync Server 2013 административные задачи делегируются пользователям с помощью новой функции управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="74963-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="74963-105">При установке Lync Server создаются некоторые роли RBAC.</span><span class="sxs-lookup"><span data-stu-id="74963-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="74963-106">Эти роли соответствуют универсальным группам безопасности в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74963-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="74963-107">Например, роль RBAC CsHelpDesk соответствует группе CsHelpDesk, находящуюся в контейнере "Пользователи" в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74963-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="74963-108">Кроме того, каждая роль RBAC связана с набором командлетов Windows PowerShell для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74963-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="74963-109">Эти командлеты представляют задачи, которые могут выполнять пользователи, которым назначена данная роль RBAC.</span><span class="sxs-lookup"><span data-stu-id="74963-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="74963-110">Например, роли CsHelpDesk назначены командлеты Lock — CsClientPin и Унлоккксклиентпин.</span><span class="sxs-lookup"><span data-stu-id="74963-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="74963-111">Это означает, что пользователи, которым назначена роль CsHelpDesk, могут блокировать и разблокировать номера ПИН-кодов пользователей.</span><span class="sxs-lookup"><span data-stu-id="74963-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="74963-112">Однако роли CsHelpDesk не назначен командлет New – CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="74963-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="74963-113">Это означает, что пользователи, которым назначена роль CsHelpDesk, не могут создавать новые политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="74963-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="74963-114">Просмотр сведений о ролях RBAC</span><span class="sxs-lookup"><span data-stu-id="74963-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="74963-115">Вы можете получить основные сведения о ролях RBAC, выполнив следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="74963-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="74963-116">Имейте в виду, что идентификатор роли RBAC (например, CsVoiceAdministrator) имеет прямое сопоставление для группы безопасности, обнаруженной в контейнере "Пользователи" в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74963-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="74963-117">Чтобы просмотреть список командлетов, которые были назначены роли, используйте команду, аналогичную приведенной ниже:</span><span class="sxs-lookup"><span data-stu-id="74963-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="74963-118">Назначение роли RBAC пользователю</span><span class="sxs-lookup"><span data-stu-id="74963-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="74963-119">Чтобы назначить роль RBAC пользователю, необходимо добавить этого пользователя в соответствующую группу безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74963-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="74963-120">Например, чтобы назначить роль CsLocationAdministrator пользователю, его нужно добавить в группу CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74963-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="74963-121">Это можно сделать посредством следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="74963-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="74963-122">**Назначение пользователя в группу безопасности**</span><span class="sxs-lookup"><span data-stu-id="74963-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="74963-123">Используя учетную запись с разрешением на изменение членства группы Active Directory, выполните вход на компьютер, где был установлен компонент «Пользователи и компьютеры Active Directory».</span><span class="sxs-lookup"><span data-stu-id="74963-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="74963-124">Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="74963-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="74963-125">В окне «Пользователи и компьютеры Active Directory» разверните имя своего домена и щелкните контейнер **Users**.</span><span class="sxs-lookup"><span data-stu-id="74963-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="74963-126">Щелкните группу безопасности **CsLocationAdministrator** правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="74963-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="74963-127">В диалоговом окне **Свойства** на вкладке **Члены** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="74963-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="74963-128">В диалоговом окне **Выбор: Пользователи, Компьютеры, Контакты или Группы** введите имя пользователя или отображаемое имя для пользователя, добавляемого в группу, (например, **Ken Myer**) в поле **Введите имена выбираемых объектов** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74963-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="74963-129">В диалоговом окне **Свойства** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="74963-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="74963-130">Чтобы убедиться, что роль управления доступом на основе ролей была назначена, используйте командлет [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment), передавая в него SamAccountName (имя для входа Active Directory) пользователя.</span><span class="sxs-lookup"><span data-stu-id="74963-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="74963-131">Например, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="74963-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

