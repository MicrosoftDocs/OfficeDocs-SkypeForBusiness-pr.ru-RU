---
title: Управление комнатами чата на сервере сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: Сводка. Узнайте, как управлять комнатами чата сервера сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815109"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d15a1-103">Управление комнатами чата на сервере сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d15a1-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d15a1-104">**Сводка:** Узнайте, как управлять комнатами чата сервера сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d15a1-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d15a1-105">Создание комнат чата и управление им намного проще при правильном использовании категорий.</span><span class="sxs-lookup"><span data-stu-id="d15a1-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d15a1-106">Категория определяет, кто может создавать комнаты чата или присоединяться к ним.</span><span class="sxs-lookup"><span data-stu-id="d15a1-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="d15a1-107">Прежде чем пытаться управлять комнатами чата, обязательно прочитайте категории сохраняемой беседы, комнаты чата и роли пользователей в Skype для бизнеса [Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) и управление категориями на сервере сохраняемой беседы в Skype для бизнеса [Server 2015.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="d15a1-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d15a1-108">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d15a1-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d15a1-109">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="d15a1-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="d15a1-110">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d15a1-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="d15a1-111">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d15a1-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="d15a1-112">Вы можете настроить комнаты чата и управлять ими с помощью Windows PowerShell командной строки или клиента Skype для бизнеса, если вы входите в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="d15a1-113">В этом разделе описывается, как управлять комнатами чата с Windows PowerShell интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="d15a1-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="d15a1-114">Если вы хотите управлять комнатами чата с помощью клиента Skype для бизнеса, см. справку по клиенту.</span><span class="sxs-lookup"><span data-stu-id="d15a1-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="d15a1-115">Комнаты чата могут иметь один из двух типов: обычный и аудитории.</span><span class="sxs-lookup"><span data-stu-id="d15a1-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="d15a1-116">Обычная комната чата позволяет всем участникам размещать и читать сообщения.</span><span class="sxs-lookup"><span data-stu-id="d15a1-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="d15a1-117">Аудитория — это тип комнаты чата, в которой только presenters могут размещать публикации, но все могут читать.</span><span class="sxs-lookup"><span data-stu-id="d15a1-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="d15a1-118">Доступ к комнатам чата и управление ими зависит от ролей пользователей следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d15a1-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="d15a1-119">Пользователи должны быть членами комнаты чата, чтобы иметь возможность размещать и читать сообщения.</span><span class="sxs-lookup"><span data-stu-id="d15a1-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="d15a1-120">Presenters are allowed to post to Auditorium rooms.</span><span class="sxs-lookup"><span data-stu-id="d15a1-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="d15a1-121">Администраторы могут удалить старое содержимое (например, содержимое, размещенное до определенной даты) из любой комнаты чата, чтобы не дать базе данных сильно увеличиться в размерах.</span><span class="sxs-lookup"><span data-stu-id="d15a1-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="d15a1-122">Администраторы также могут удалять или заменять сообщения, которые считаются недопустимыми для определенной комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="d15a1-123">Сами пользователи, включая авторов сообщений, не могут удалять содержимое комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="d15a1-124">Менеджеры комнат чата могут вносить изменения во все свойства комнат чата, включая отключение комнат.</span><span class="sxs-lookup"><span data-stu-id="d15a1-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="d15a1-125">Однако менеджеры не могут удалить комнату или изменить категорию комнаты.</span><span class="sxs-lookup"><span data-stu-id="d15a1-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="d15a1-126">Только администраторы могут удалить комнату чата после ее создания.</span><span class="sxs-lookup"><span data-stu-id="d15a1-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="d15a1-127">Настроить комнаты чата и управлять ими можно с помощью следующих Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d15a1-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="d15a1-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="d15a1-128">**Cmdlet**</span></span>|<span data-ttu-id="d15a1-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d15a1-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d15a1-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d15a1-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d15a1-131">Создание комнаты чата</span><span class="sxs-lookup"><span data-stu-id="d15a1-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="d15a1-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d15a1-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d15a1-133">Настройка параметров существующей комнаты; назначение пользователей и групп пользователей комнате</span><span class="sxs-lookup"><span data-stu-id="d15a1-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="d15a1-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d15a1-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d15a1-135">Извлечение сведений о комнатах</span><span class="sxs-lookup"><span data-stu-id="d15a1-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="d15a1-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d15a1-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d15a1-137">Очистка комнаты или сообщений из комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="d15a1-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d15a1-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d15a1-139">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="d15a1-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d15a1-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="d15a1-141">Удаление сообщений из комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="d15a1-142">С помощью **new-CsPersistentChatRoom** можно создавать комнаты чата, а **set-CsPersistentChatRoom** — для настройки существующей комнаты чата, включая добавление пользователей в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="d15a1-143">Для комнат чата можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d15a1-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="d15a1-144">Отключено.</span><span class="sxs-lookup"><span data-stu-id="d15a1-144">Disabled.</span></span> <span data-ttu-id="d15a1-145">Позволяет отключить или включить комнату чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="d15a1-146">Приглашения.</span><span class="sxs-lookup"><span data-stu-id="d15a1-146">Invitations.</span></span> <span data-ttu-id="d15a1-147">Позволяет включить или отключить приглашения в комнаты чата, которые используются для уведомления пользователей о добавлении их в качестве участников комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="d15a1-148">Параметр по умолчанию для приглашений в наследуется, что привело к тому, что комната чата приняла параметр приглашения, настроенный для категории, к которой она принадлежит.</span><span class="sxs-lookup"><span data-stu-id="d15a1-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="d15a1-149">Настройка для параметра приглашений false на уровне комнаты чата позволяет переопределять параметр категории.</span><span class="sxs-lookup"><span data-stu-id="d15a1-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="d15a1-150">Конфиденциальность.</span><span class="sxs-lookup"><span data-stu-id="d15a1-150">Privacy.</span></span> <span data-ttu-id="d15a1-151">Позволяет указать, является ли комната чата открытой, закрытой или секретной.</span><span class="sxs-lookup"><span data-stu-id="d15a1-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="d15a1-152">Открытые комнаты могут искать и получать доступ любой.</span><span class="sxs-lookup"><span data-stu-id="d15a1-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="d15a1-153">Закрытые комнаты могут искать все, но доступ к ним могут получить только участники.</span><span class="sxs-lookup"><span data-stu-id="d15a1-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="d15a1-154">Поиск в секретных комнатах и доступ к ним могут получить только члены комнаты.</span><span class="sxs-lookup"><span data-stu-id="d15a1-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="d15a1-155">По умолчанию каждая новая комната изначально настроена как закрытая.</span><span class="sxs-lookup"><span data-stu-id="d15a1-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="d15a1-156">Тип.</span><span class="sxs-lookup"><span data-stu-id="d15a1-156">Type.</span></span> <span data-ttu-id="d15a1-157">Позволяет указать, является ли комната чата обычной комнатой, которая принимает сообщения, которые опубликовал какой-либо член, или комнатой аудитории, которая принимает сообщения, которые были опубликованы только для presenter.</span><span class="sxs-lookup"><span data-stu-id="d15a1-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="d15a1-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="d15a1-158">Addin.</span></span> <span data-ttu-id="d15a1-159">Позволяет связать ранее настроенную надстройку с комнатой чата, что позволяет участникам просматривать содержимое URL-адреса во время участия.</span><span class="sxs-lookup"><span data-stu-id="d15a1-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="d15a1-160">В дополнение к перечисленным выше параметрам, с помощью cmdlet **Set-CsPersistentChatRoom** можно назначать пользователей комнате чата следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d15a1-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="d15a1-161">Участники.</span><span class="sxs-lookup"><span data-stu-id="d15a1-161">Members.</span></span> <span data-ttu-id="d15a1-162">Настраивает членство для комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-162">Configures membership for the chat room.</span></span> <span data-ttu-id="d15a1-163">С помощью одного или нескольких членов можно добавить или удалить отдельные члены, указав SIP-адрес пользователей.</span><span class="sxs-lookup"><span data-stu-id="d15a1-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="d15a1-164">Чтобы разрешить массовое добавление пользователей, можно также у указывает подразделения или группы рассылки Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d15a1-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="d15a1-165">Менеджеры.</span><span class="sxs-lookup"><span data-stu-id="d15a1-165">Managers.</span></span> <span data-ttu-id="d15a1-166">Позволяет назначать менеджеров комнате чата.</span><span class="sxs-lookup"><span data-stu-id="d15a1-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="d15a1-167">Менеджеры имеют разрешения на определение членства в комнате чата вместе с другими настройками.</span><span class="sxs-lookup"><span data-stu-id="d15a1-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="d15a1-168">Presenters.</span><span class="sxs-lookup"><span data-stu-id="d15a1-168">Presenters.</span></span> <span data-ttu-id="d15a1-169">Позволяет назначать presenters комнате чата аудитории.</span><span class="sxs-lookup"><span data-stu-id="d15a1-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="d15a1-170">Подробные сведения о синтаксисе, включая все параметры, см. в руководстве [по skype для бизнеса Server 2015 Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="d15a1-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="d15a1-171">Создание комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-171">Create a new room</span></span>

<span data-ttu-id="d15a1-172">Вы можете создать новую комнату с помощью **cmdlet New-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="d15a1-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d15a1-173">Например, следующая команда создает новую комнату чата с именем ITChatRoom в пуле atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d15a1-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="d15a1-174">В этом примере комната чата добавляется в ИТ-категорию:</span><span class="sxs-lookup"><span data-stu-id="d15a1-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="d15a1-175">**Примечание.** PersistentChatPoolFqdn не требуется, если имеется одно из следующих ва.</span><span class="sxs-lookup"><span data-stu-id="d15a1-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="d15a1-176">Существует только один пул серверов сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="d15a1-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="d15a1-177">для категории указано полное доменное имя пула;</span><span class="sxs-lookup"><span data-stu-id="d15a1-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="d15a1-178">для добавления комнаты указывается полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="d15a1-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="d15a1-179">Настройка существующей комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-179">Configure an existing room</span></span>

<span data-ttu-id="d15a1-180">Существующую комнату можно настроить с помощью **cmdlet Set-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="d15a1-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d15a1-181">Например, следующая команда назначает user1 в качестве участника и presenter, а пользователя user2 — в качестве руководителя комнаты аудитории testCat:</span><span class="sxs-lookup"><span data-stu-id="d15a1-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="d15a1-182">В следующем примере в комнату чата NorthAmerica добавляются все пользователи из OU NorthAmericaUsers в active Directory:</span><span class="sxs-lookup"><span data-stu-id="d15a1-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="d15a1-183">В следующем примере все члены группы рассылки Finance добавляются в ту же комнату чата:</span><span class="sxs-lookup"><span data-stu-id="d15a1-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="d15a1-184">Отключение или включит комнату</span><span class="sxs-lookup"><span data-stu-id="d15a1-184">Disable or enable a room</span></span>

<span data-ttu-id="d15a1-185">Если тема комнаты сохраняемого чата больше не актуальна, вы можете сделать комнату чата недоступной для пользователей, отключив ее.</span><span class="sxs-lookup"><span data-stu-id="d15a1-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="d15a1-186">Когда чат отключен, все подключенные на данный момент участники отключаются от него.</span><span class="sxs-lookup"><span data-stu-id="d15a1-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="d15a1-187">Пользователи не могут снова подключиться к чату или найти его через поиск после его отключения.</span><span class="sxs-lookup"><span data-stu-id="d15a1-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="d15a1-188">Если история комнаты чата сохраняется, содержимое сохраняется, когда комната чата отключена.</span><span class="sxs-lookup"><span data-stu-id="d15a1-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="d15a1-189">Тем не менее, содержимое не будет отображаться в поиске, пока чат остается в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="d15a1-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="d15a1-190">Если включить чат позднее, пользователи смогут находить сообщения, опубликованные до того, как чат был отключен.</span><span class="sxs-lookup"><span data-stu-id="d15a1-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="d15a1-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="d15a1-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="d15a1-192">Если чат отключен, список его участников и другие параметры сохраняются.</span><span class="sxs-lookup"><span data-stu-id="d15a1-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="d15a1-193">Как администратор вы можете включить отключенную комнату, и вам не нужно вручную повторно создавать параметры.</span><span class="sxs-lookup"><span data-stu-id="d15a1-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="d15a1-194">Вы можете отключить комнату с помощью cmdlet **Set-CsPersistentChatRoom** и установить для параметра Disabled true:</span><span class="sxs-lookup"><span data-stu-id="d15a1-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="d15a1-195">Чтобы включить комнату чата, установите для параметра Disabled параметр False:</span><span class="sxs-lookup"><span data-stu-id="d15a1-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="d15a1-196">Получить сведения о комнатах</span><span class="sxs-lookup"><span data-stu-id="d15a1-196">Get information about rooms</span></span>

<span data-ttu-id="d15a1-197">Для получения сведений о комнатах, настроенных для использования в организации, можно использовать cmdlet **Get-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="d15a1-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="d15a1-198">Следующая команда возвращает сведения обо всех комнатах чата, настроенных для использования в организации:</span><span class="sxs-lookup"><span data-stu-id="d15a1-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="d15a1-199">Удаление всего содержимого из комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-199">Remove all content from a room</span></span>

<span data-ttu-id="d15a1-200">Удалить содержимое из комнаты можно с помощью **cmdlet Clear-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="d15a1-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d15a1-201">Например, следующая команда удаляет все содержимое из комнаты сохраняемой беседы ITChatRoom, которая была добавлена в комнату 1 марта 2015 г. или до 1 марта 2015 г.:</span><span class="sxs-lookup"><span data-stu-id="d15a1-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="d15a1-202">Удаление сообщения из комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-202">Remove a message from a room</span></span>

<span data-ttu-id="d15a1-203">Можно удалить одно или несколько сообщений в базе данных сохраняемого чата и при необходимости заменить сообщение на сообщение по умолчанию или сообщение, предоставленное администратором, с помощью cmdlet **Remove-CsPersistentChatMessage.**</span><span class="sxs-lookup"><span data-stu-id="d15a1-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="d15a1-204">Например, следующая команда удаляет все сообщения из чата ITChatRoom, которые были опубликованы пользователем kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="d15a1-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="d15a1-205">В следующем примере все удаленые сообщения заменяются примечанием о том, что сообщение больше не доступно:</span><span class="sxs-lookup"><span data-stu-id="d15a1-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="d15a1-206">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="d15a1-206">Remove a room</span></span>

<span data-ttu-id="d15a1-207">Удалить комнату можно с помощью **cmdlet Remove-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="d15a1-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="d15a1-208">Например, следующая команда удаляет комнату чата RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="d15a1-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="d15a1-209">Перемещение комнаты из одной категории в другую</span><span class="sxs-lookup"><span data-stu-id="d15a1-209">Move a room from one category to another</span></span>

<span data-ttu-id="d15a1-210">Если менеджер комнаты  чата имеет права создателя в другой категории, он может переместить комнату из одной категории в другую.</span><span class="sxs-lookup"><span data-stu-id="d15a1-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="d15a1-211">Комната не удаляется и воссоздается.</span><span class="sxs-lookup"><span data-stu-id="d15a1-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="d15a1-212">Это изменение связи с базой данных.</span><span class="sxs-lookup"><span data-stu-id="d15a1-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="d15a1-213">Изменение категории комнаты чата следует делать редко и с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="d15a1-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="d15a1-214">Категория определяет разрешенное членство в комнате чата, поэтому при перемещении комнаты чата в другую категорию все системные списки управления доступом (SACL), которые более не поддерживаются новой категорией, очищаются.</span><span class="sxs-lookup"><span data-stu-id="d15a1-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="d15a1-215">Например, если пользователь был членом комнаты и больше не является разрешенным членом в новой категории, членство в комнате будет изменено, а пользователь будет удален из комнаты.</span><span class="sxs-lookup"><span data-stu-id="d15a1-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

