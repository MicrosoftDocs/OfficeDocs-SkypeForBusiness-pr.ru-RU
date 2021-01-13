---
title: Создание администратора сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: Сводка. В этом разделе вы узнаете, как создать роль администратора сервера сохраняемого чата для начальной настройки и управления службами сохраняемого чата в Skype для бизнеса Server 2015.
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802099"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="c559e-103">Создание администратора сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c559e-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c559e-104">**Сводка:** В этом разделе вы узнаете, как создать роль администратора сервера сохраняемого чата для начальной настройки и управления службами сохраняемого чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c559e-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c559e-105">В Skype для бизнеса Server пользователи, которые выполняют определенные задачи, должны быть назначены участниками одной или более определенных групп.</span><span class="sxs-lookup"><span data-stu-id="c559e-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="c559e-106">Role-Based управления доступом (RBAC) используется для предоставления привилегий путем назначения пользователям предварительно заданных административных ролей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c559e-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="c559e-107">Эти роли соответствуют универсальным группам безопасности в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c559e-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="c559e-108">Членам группы безопасности администратора сохраняемого чата CsPersistentChatAdministrator предоставляется доступ клетам сервера сохраняемого чата, которые можно выполнять с помощью оболочки управления Skype для бизнеса Server или панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c559e-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="c559e-109">Перед настройкой и администрированием сервера сохраняемой беседы убедитесь, что имеются соответствующие права и разрешения пользователей, а также что все пользователи, которые будут выступать в качестве администраторов сохраняемой беседы, будут добавлены в группу безопасности администратора сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="c559e-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="c559e-110">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c559e-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c559e-111">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="c559e-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="c559e-112">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c559e-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c559e-113">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c559e-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="c559e-114">Создание администратора сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="c559e-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="c559e-115">Чтобы добавить пользователя в группу безопасности администратора сохраняемой беседы, CsPersistentChatAdministrator, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c559e-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="c559e-116">Используя учетную запись с разрешением на изменение членства в группе Active Directory, войдите на компьютер, на котором установлены пользователи и компьютеры Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c559e-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="c559e-117">Нажмите кнопку Пуск, выберите Все программы, Администрирование и затем Пользователи и компьютеры Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c559e-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="c559e-118">В окне «Пользователи и компьютеры Active Directory» разверните имя своего домена и щелкните контейнер Users.</span><span class="sxs-lookup"><span data-stu-id="c559e-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="c559e-119">Щелкните правой кнопкой мыши группу безопасности CsPersistentChatAdministrator и выберите "Свойства".</span><span class="sxs-lookup"><span data-stu-id="c559e-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="c559e-120">В диалоговом окне Свойства на вкладке Члены нажмите кнопку Добавить.</span><span class="sxs-lookup"><span data-stu-id="c559e-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="c559e-121">В диалоговом окне "Выбор пользователей, компьютеров, контактов или групп" введите имя пользователя или отображаемого имени пользователя, добавляемого в группу, в поле "Введите имена объектов для выбора" и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="c559e-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="c559e-122">В диалоговом окне Свойства нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="c559e-122">In the Properties dialog box, click OK.</span></span>
    

