---
title: Создание администраторов панели управления Skype для бизнеса Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: Предоставление доступа к Скайп для Business Server 2015, выполните следующие действия.
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="d9cba-103">Создание администраторов панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d9cba-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="d9cba-104">Предоставление доступа к Скайп для Business Server 2015, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d9cba-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="d9cba-105">Войдите как участник группы администраторов домена или группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d9cba-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d9cba-106">Откройте раздел **Active Directory — пользователи и компьютеры**, разверните домен, щелкните на контейнере **Пользователи** правой кнопкой мыши и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d9cba-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="d9cba-107">В окне **Свойства CSAdministrator** перейдите на вкладку **Участники**.</span><span class="sxs-lookup"><span data-stu-id="d9cba-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="d9cba-p101">На вкладке "Участники" нажмите кнопку **Добавить**. В окне **выбора пользователей, контактов, компьютеров, учетных записей служб или групп** найдите поле **Введите имена объектов для выбора**. Введите имена пользователей или групп для добавления к группе CSAdministrators. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9cba-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="d9cba-p102">На вкладке "Участники" проверьте наличие выбранных пользователей или групп. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d9cba-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="d9cba-114">Скайп для панели управления Business Server — это средство управления доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="d9cba-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="d9cba-115">Членство в группе CsAdministrator дает пользователь, работающий с Скайп для панели управления сервера Business полный доступ для всех доступных функций конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d9cba-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="d9cba-116">Предусмотрены также другие роли, предназначенные для выполнения определенных функций.</span><span class="sxs-lookup"><span data-stu-id="d9cba-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="d9cba-117">Пользователям не нужно включить поддержку Скайп для Business Server, чтобы сделать членами группы управления.</span><span class="sxs-lookup"><span data-stu-id="d9cba-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="d9cba-118">Другие роли, относятся:</span><span class="sxs-lookup"><span data-stu-id="d9cba-118">Other roles include:</span></span>
  
- <span data-ttu-id="d9cba-119">**CsArchiving:** Члены этой группы могут выполнять все функции архивации, таких как Настройка и управление ими роли сервера архивирование.</span><span class="sxs-lookup"><span data-stu-id="d9cba-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="d9cba-p104">**CsHelpDesk.** Участники этой группы могут просматривать конфигурацию и развертывание, в том числе свойства и политики пользователей. Они могут также выполнять некоторые задачи по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="d9cba-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="d9cba-p105">**CsLocationAdministrator.** Участники имеют самый низкий уровень пользовательских прав, связанных с управлением службой Enhanced 9-1-1 (E9-1-1). Они могут создавать в развертывании расположения и сетевые идентификаторы E9-1-1 и связывать их.</span><span class="sxs-lookup"><span data-stu-id="d9cba-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="d9cba-124">**CsResponseGroupAdministrator.** Участники могут настраивать службу "Группа ответа" и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="d9cba-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="d9cba-125">**CsServerAdministrator:** Члены можно управлять, наблюдения и устранения всех серверов с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d9cba-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="d9cba-126">**CsUserAdministrator.** Участники могут управлять пользователями, включать и отключать их, назначать им существующие политики.</span><span class="sxs-lookup"><span data-stu-id="d9cba-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="d9cba-127">**CsViewOnlyAdministrator:** Участники могут просматривать развертывания и настройки сведения о сервере.</span><span class="sxs-lookup"><span data-stu-id="d9cba-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="d9cba-128">Членство в этом позволяет членам позволяют отслеживать состояние серверы Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d9cba-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="d9cba-129">**CsVoiceAdministrator:** Участников можно создать, настроить и управлять параметрами связанные с голосовой связи в Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="d9cba-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="d9cba-130">Для обеспечения согласованности системы безопасности и целостности данных управления доступом на основе ролей, добавление пользователей в группы, определяющие роли, выполняемые пользователями в системе управления Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="d9cba-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

