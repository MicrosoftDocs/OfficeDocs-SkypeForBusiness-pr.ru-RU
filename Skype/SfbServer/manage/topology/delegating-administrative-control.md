---
title: Делегирование административного управления Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832799"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="dc934-102">Делегирование административного управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc934-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="dc934-103">В Skype для бизнеса Server административные задачи делегируются пользователям с помощью функции управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="dc934-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="dc934-104">При установке Skype для бизнеса Server создается ряд ролей RBAC.</span><span class="sxs-lookup"><span data-stu-id="dc934-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="dc934-105">Эти роли соответствуют универсальным группам безопасности в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc934-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="dc934-106">Например, роль RBAC CsHelpDesk соответствует группе CsHelpDesk, найденной в контейнере Users в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc934-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="dc934-107">Кроме того, каждая роль RBAC связана с набором Windows PowerShell Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc934-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="dc934-108">Эти cmdlets представляют задачи, которые могут выполнять пользователи, которым назначена данной роли RBAC.</span><span class="sxs-lookup"><span data-stu-id="dc934-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="dc934-109">Например, роли CsHelpDesk назначены Lock-CsClientPin и UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="dc934-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="dc934-110">Это означает, что пользователи, которым назначена роль CsHelpDesk, могут заблокировать и разблокировать ПИН-коды пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc934-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="dc934-111">Однако роль CsHelpDesk не была назначена New-CsVoicePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="dc934-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="dc934-112">Это означает, что пользователи, которым назначена роль CsHelpDesk, не могут создавать новые политики голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="dc934-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="dc934-113">Просмотр сведений о ролях RBAC</span><span class="sxs-lookup"><span data-stu-id="dc934-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="dc934-114">Вы можете получить основные сведения о ролях RBAC, выверив следующую команду в командной оболочке Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="dc934-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="dc934-115">Помните, что удостоверение роли RBAC (например, CsVoiceAdministrator) имеет прямое сопоставление с группой безопасности, найденной в контейнере Users в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc934-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="dc934-116">Чтобы просмотреть список командлетов, которые были назначены роли, используйте команду, аналогичную приведенной ниже:</span><span class="sxs-lookup"><span data-stu-id="dc934-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="dc934-117">Назначение роли RBAC пользователю</span><span class="sxs-lookup"><span data-stu-id="dc934-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="dc934-118">Чтобы назначить пользователю роль RBAC, необходимо добавить этого пользователя в соответствующую группу безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc934-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="dc934-119">Например, чтобы назначить роль CsLocationAdministrator пользователю, его нужно добавить в группу CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dc934-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="dc934-120">Это можно сделать посредством следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="dc934-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="dc934-121">Используя учетную запись с разрешением на изменение членства группы Active Directory, выполните вход на компьютер, где был установлен компонент «Пользователи и компьютеры Active Directory».</span><span class="sxs-lookup"><span data-stu-id="dc934-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="dc934-122">Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dc934-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="dc934-123">В окне «Пользователи и компьютеры Active Directory» разверните имя своего домена и щелкните контейнер **Users**.</span><span class="sxs-lookup"><span data-stu-id="dc934-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="dc934-124">Щелкните группу безопасности **CsLocationAdministrator** правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc934-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="dc934-125">В диалоговом окне **Свойства** на вкладке **Члены** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dc934-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="dc934-126">В диалоговом окне "Выбор **пользователей, компьютеров,** контактов или групп" введите имя пользователя или отображаемого имени  пользователя, добавляемого в группу (например, Ken Myer), в поле "Введите имена выбираемого объекта" и нажмите кнопку "ОК". </span><span class="sxs-lookup"><span data-stu-id="dc934-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="dc934-127">В диалоговом окне **Свойства** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc934-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="dc934-128">Чтобы убедиться, что роль управления доступом на основе ролей была назначена, используйте командлет Get-CsAdminRoleAssignment, передавая в него SamAccountName (имя для входа Active Directory) пользователя.</span><span class="sxs-lookup"><span data-stu-id="dc934-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="dc934-129">Например, запустите эту команду в командной оболочке Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="dc934-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
