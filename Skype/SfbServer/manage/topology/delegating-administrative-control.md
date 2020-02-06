---
title: Делегирование административного управления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817275"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="1d601-102">Делегирование административного управления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1d601-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="1d601-103">В Skype для бизнеса Server задачи администрирования делегируются пользователям с помощью функции управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="1d601-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="1d601-104">При установке Skype для бизнеса Server создается ряд ролей RBAC.</span><span class="sxs-lookup"><span data-stu-id="1d601-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="1d601-105">These roles correspond to universal security groups in Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="1d601-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="1d601-106">Например, роль RBAC Кшелпдеск соответствует группе Кшелпдеск, которая находится в контейнере Users доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d601-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="1d601-107">Кроме того, каждая роль RBAC связана с набором командлетов Windows PowerShell в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1d601-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1d601-108">Эти командлеты представляют задачи, которые могут быть выполнены пользователями, которым назначена данная роль RBAC.</span><span class="sxs-lookup"><span data-stu-id="1d601-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="1d601-109">Например, роли Кшелпдеск назначены командлеты Lock-Ксклиентпин и Унлоккксклиентпин.</span><span class="sxs-lookup"><span data-stu-id="1d601-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="1d601-110">Это означает, что пользователи, которым назначена роль Кшелпдеск, могут блокировать и разблокирование PIN-кодов пользователей.</span><span class="sxs-lookup"><span data-stu-id="1d601-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="1d601-111">Однако роль Кшелпдеск не назначила командлет New-Ксвоицеполици.</span><span class="sxs-lookup"><span data-stu-id="1d601-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="1d601-112">Это означает, что пользователи, которым назначена роль Кшелпдеск, не могут создавать новые политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1d601-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="1d601-113">Просмотр сведений о ролях RBAC</span><span class="sxs-lookup"><span data-stu-id="1d601-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="1d601-114">Вы можете получить основные сведения о ролях RBAC, выполнив следующую команду в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="1d601-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="1d601-115">Имейте в виду, что идентификатор роли RBAC (например, Ксвоицеадминистратор) имеет прямое сопоставление с группой безопасности, обнаруженной в контейнере Users доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d601-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="1d601-116">Чтобы просмотреть список командлетов, назначенных для роли, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1d601-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="1d601-117">Назначение роли RBAC пользователю</span><span class="sxs-lookup"><span data-stu-id="1d601-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="1d601-118">Чтобы назначить пользователю роль RBAC, необходимо добавить этого пользователя в соответствующую группу безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d601-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="1d601-119">Например, чтобы назначить пользователю роль Кслокатионадминистратор, необходимо добавить этого пользователя в группу Кслокатионадминистратор.</span><span class="sxs-lookup"><span data-stu-id="1d601-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="1d601-120">Это можно сделать, выполнив описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1d601-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="1d601-121">Используя учетную запись, которая имеет разрешение на изменение членства группы Active Directory, войдите в систему на компьютере, на котором установлен компонент "пользователи и компьютеры Active Directory".</span><span class="sxs-lookup"><span data-stu-id="1d601-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="1d601-122">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Администрирование**, а затем — **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1d601-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="1d601-123">В окне "пользователи и компьютеры Active Directory" разверните имя своего домена и щелкните контейнер " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="1d601-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="1d601-124">Щелкните правой кнопкой мыши группу безопасности **кслокатионадминистратор**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="1d601-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="1d601-125">В диалоговом окне **Свойства** на вкладке **члены** нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="1d601-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="1d601-126">В диалоговом окне **Выбор пользователей, компьютеров, контактов или групп** введите имя пользователя или отображаемое имя пользователя, которого нужно добавить в группу (например, Кен мер) в поле **Введите имена объектов, которые нужно выделить** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d601-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="1d601-127">В диалоговом окне " **Свойства** " нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1d601-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="1d601-128">Чтобы убедиться в том, что роль RBAC назначена, используйте командлет Get-Ксадминролеассигнмент, передав командлету значение SamAccountName (имя для входа в службу каталогов Active Directory) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="1d601-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="1d601-129">Например, выполните эту команду в командной консоли управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="1d601-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
