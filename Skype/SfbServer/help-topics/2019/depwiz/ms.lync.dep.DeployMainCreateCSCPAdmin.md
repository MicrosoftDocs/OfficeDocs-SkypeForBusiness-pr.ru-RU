---
title: Создание администраторов панели управления Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы предоставить доступ к Skype для бизнеса Server, сделайте следующее:'
ms.openlocfilehash: cb1449aa4fcca534e01b4d8a47a7ac9c39cd64c7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824969"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="f8262-103">Создание администраторов панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f8262-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="f8262-104">Чтобы предоставить доступ к Skype для бизнеса Server, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f8262-104">To grant access to the Skype for Business Server, do the following:</span></span>
  
1. <span data-ttu-id="f8262-105">Войдите как участник группы администраторов домена или группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f8262-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="f8262-106">Откройте окно **Active Directory — пользователи и компьютеры**, разверните свой домен, щелкните правой кнопкой мыши контейнер **Пользователи** и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f8262-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="f8262-107">В окне **Свойства CSAdministrator** перейдите на вкладку **Участники**.</span><span class="sxs-lookup"><span data-stu-id="f8262-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="f8262-p101">На вкладке "Участники" нажмите кнопку **Добавить**. В окне **Выбрать пользователей, контакты, компьютеры, учетные записи служб или группы** найдите элемент **Введите имена объектов для выбора**. Введите имена пользователей или групп для добавления в группу CSAdministrators. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8262-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="f8262-p102">На вкладке "Участники" проверьте наличие выбранных пользователей или групп. Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f8262-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="f8262-114">Панель управления Skype для бизнеса Server — это средство управления доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="f8262-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="f8262-115">Членство в группе CsAdministrator предоставляет пользователю, использующему панель управления Skype для бизнеса Server, полный контроль над всеми доступными функциями конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8262-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="f8262-116">Имеются также другие роли, предназначенные для выполнения определенных функций.</span><span class="sxs-lookup"><span data-stu-id="f8262-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="f8262-117">Пользователям не нужно включить Skype для бизнеса Server, чтобы они были членами групп управления.</span><span class="sxs-lookup"><span data-stu-id="f8262-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="f8262-118">К другим ролям относятся:</span><span class="sxs-lookup"><span data-stu-id="f8262-118">Other roles include:</span></span>
  
- <span data-ttu-id="f8262-119">**CsArchiving:** Члены этой группы могут выполнять все функции архива, такие как настройка и управление ролью сервера архива.</span><span class="sxs-lookup"><span data-stu-id="f8262-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="f8262-p104">**CsHelpDesk.** Участники этой группы могут просматривать конфигурацию и развертывание, в том числе свойства и политики пользователей. Они также могут выполнять определенные задачи поиска и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="f8262-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="f8262-p105">**CsLocationAdministrator.** Участники имеют самый низкий уровень пользовательских прав, связанных с управлением службой Enhanced 9-1-1 (E9-1-1). Они могут создавать в развертывании расположения и сетевые идентификаторы E9-1-1 и связывать их.</span><span class="sxs-lookup"><span data-stu-id="f8262-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="f8262-124">**CsResponseGroupAdministrator.** Участники могут настраивать службу "Группа ответа" и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="f8262-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="f8262-125">**CsServerAdministrator:** Участники могут управлять всеми серверами Skype для бизнеса Server, отслеживать и устранять неполадки, а также устранять их неполадки.</span><span class="sxs-lookup"><span data-stu-id="f8262-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="f8262-126">**CsUserAdministrator.** Участники могут управлять пользователями, включать и отключать их, а также назначать пользователям существующие политики.</span><span class="sxs-lookup"><span data-stu-id="f8262-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="f8262-127">**CsViewOnlyAdministrator:** Участники могут просматривать развертывание и конфигурацию сведений о сервере.</span><span class="sxs-lookup"><span data-stu-id="f8262-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="f8262-128">Это членство позволяет участнику отслеживать состояние серверов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f8262-128">This membership enables a member to monitor the health of the servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="f8262-129">**CsVoiceAdministrator:** Участники могут создавать, настраивать параметры голосовой связи и управлять ими в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f8262-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="f8262-130">Чтобы обеспечить безопасность и целостность управления доступом на основе ролей, добавьте пользователей в группы, которые определяют, какую роль выполняет пользователь при управлении развертыванием Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f8262-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

