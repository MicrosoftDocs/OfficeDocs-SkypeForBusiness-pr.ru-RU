---
title: Управление комнатами чата на сервере сохраняемого чата в Skype для бизнеса Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Сводка: Узнайте, как управлять Persistent Chat Server разговоров в Скайп для Business Server 2015.'
ms.openlocfilehash: fd927e3a54f1f3a8df429677f481ea224534b984
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="df00b-103">Управление комнатами чата на сервере сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="df00b-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="df00b-104">**Сводка:** Сведения об управлении Persistent Chat Server разговоров в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="df00b-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="df00b-105">Создание комнат чата и управление ими осуществляются значительно проще благодаря правильному использованию категорий.</span><span class="sxs-lookup"><span data-stu-id="df00b-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="df00b-106">Категория определяет пользователей, которые могут создавать или присоединиться к комнат чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="df00b-107">Прежде чем пытаться управление комнат чата, обязательно прочитайте [сохраняемого чата категорий, комнат чата и роли пользователей в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) и [Управление категориями в Persistent Chat Server в Скайп для Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="df00b-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="df00b-108">Можно настроить и управлять комнат чата, с помощью интерфейса командной строки Windows PowerShell или с помощью Скайп для клиента Business, если вы являетесь участником комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="df00b-109">В этом разделе описываются способы управления комнатами с помощью интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="df00b-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="df00b-110">Если вы хотите управлять комнат чата с помощью Скайп для клиента Business, обратитесь к справке клиента.</span><span class="sxs-lookup"><span data-stu-id="df00b-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="df00b-111">Каналы, в может иметь одно из двух типов: обычный и аудитории.</span><span class="sxs-lookup"><span data-stu-id="df00b-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="df00b-112">В обычной комнате передавать и отправлять сообщения разрешается всем членам.</span><span class="sxs-lookup"><span data-stu-id="df00b-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="df00b-113">В комнату-аудиторию могут отправлять сообщения только выступающие, а остальные пользователи могут их читать.</span><span class="sxs-lookup"><span data-stu-id="df00b-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="df00b-114">Возможность доступа и управления комнатами чата зависит от пользовательских ролей следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df00b-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="df00b-115">Чтобы отправлять и читать сообщения, пользователи должны быть членами комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="df00b-116">Выступающим разрешено передавать сообщения в комнаты-аудитории.</span><span class="sxs-lookup"><span data-stu-id="df00b-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="df00b-117">Администраторы могут удалять старое содержимое (например, содержимое, размещенное до определенной даты) из любой комнаты чата, чтобы база данных сильно не увеличивалась в размерах.</span><span class="sxs-lookup"><span data-stu-id="df00b-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="df00b-118">Кроме того, они могут удалить или заменить сообщения, которые кажутся несоответствующими данной комнате чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="df00b-119">Сами пользователи, включая авторов сообщений, не могут удалять содержимое комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="df00b-120">Диспетчеры комнат чата могут вносить изменения в любые свойства комнат (включая отключение комнат).</span><span class="sxs-lookup"><span data-stu-id="df00b-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="df00b-121">Но диспетчер комнаты чата не может удалить комнату или изменить ее категорию.</span><span class="sxs-lookup"><span data-stu-id="df00b-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="df00b-122">Только администраторы могут удалить комнату чата после ее создания.</span><span class="sxs-lookup"><span data-stu-id="df00b-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="df00b-123">Настраивать комнаты чата и управлять ими можно с помощью следующих командлетов Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="df00b-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="df00b-124">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="df00b-124">**Cmdlet**</span></span>|<span data-ttu-id="df00b-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="df00b-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df00b-126">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="df00b-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="df00b-127">Создание новой комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="df00b-128">SET-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="df00b-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="df00b-129">Настройка параметров существующей комнаты; назначение пользователей и групп пользователей комнате</span><span class="sxs-lookup"><span data-stu-id="df00b-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="df00b-130">Командлет Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="df00b-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="df00b-131">Получение сведений о комнат</span><span class="sxs-lookup"><span data-stu-id="df00b-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="df00b-132">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="df00b-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="df00b-133">Очистка комнаты или очистка сообщений в комнате</span><span class="sxs-lookup"><span data-stu-id="df00b-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="df00b-134">Remove Cspersistentchatroomnm</span><span class="sxs-lookup"><span data-stu-id="df00b-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="df00b-135">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="df00b-136">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="df00b-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="df00b-137">Удаление сообщений из комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="df00b-138">Командлет **New-CsPersistentChatRoom** используется для создания комнат чата, а командлет **Set-CsPersistentChatRoom** — для настройки существующей комнаты чата, включая добавление к ней пользователей.</span><span class="sxs-lookup"><span data-stu-id="df00b-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="df00b-139">Можно настроить следующие параметры комнаты чата:</span><span class="sxs-lookup"><span data-stu-id="df00b-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="df00b-140">Disabled.</span><span class="sxs-lookup"><span data-stu-id="df00b-140">Disabled.</span></span> <span data-ttu-id="df00b-141">Позволяет включать или отключать комнату чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="df00b-142">Приглашения.</span><span class="sxs-lookup"><span data-stu-id="df00b-142">Invitations.</span></span> <span data-ttu-id="df00b-143">Позволяет включить или отключить приглашения комнаты чата, используемые для уведомления пользователей, если они были добавлены в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="df00b-144">Значение по умолчанию для приглашения в наследовать, которая вызвала чат принять приглашение параметры, настроенные на категории, к которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="df00b-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="df00b-145">Настройка приглашения на параметр значение false на уровне комнаты чата позволяет переопределять параметр category.</span><span class="sxs-lookup"><span data-stu-id="df00b-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="df00b-146">Privacy.</span><span class="sxs-lookup"><span data-stu-id="df00b-146">Privacy.</span></span> <span data-ttu-id="df00b-147">Позволяет указать, будет ли комната чата открытой, закрытой или секретной.</span><span class="sxs-lookup"><span data-stu-id="df00b-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="df00b-148">Открытые комнаты могут отыскивать и использовать любые пользователи.</span><span class="sxs-lookup"><span data-stu-id="df00b-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="df00b-149">Закрытые комнаты могут отыскивать любые пользователи, но доступны они только их членам.</span><span class="sxs-lookup"><span data-stu-id="df00b-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="df00b-150">Секретные комнаты могут отыскивать и использовать только члены комнат.</span><span class="sxs-lookup"><span data-stu-id="df00b-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="df00b-151">По умолчанию все новые комнаты исходно настроены как закрытые.</span><span class="sxs-lookup"><span data-stu-id="df00b-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="df00b-152">Type.</span><span class="sxs-lookup"><span data-stu-id="df00b-152">Type.</span></span> <span data-ttu-id="df00b-153">Позволяет указать, является ли чата обычных комнаты, который принимает сообщений, отправленных любой элемент или помещении аудитория, который принимает сообщений, отправленных только выступающим.</span><span class="sxs-lookup"><span data-stu-id="df00b-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="df00b-154">Addin.</span><span class="sxs-lookup"><span data-stu-id="df00b-154">Addin.</span></span> <span data-ttu-id="df00b-155">Позволяет связать ранее настроенную надстройку с комнатой чата, что позволяет членам комнаты, участвующим в беседе, просматривать содержимое по URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="df00b-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="df00b-156">Помимо приведенных выше параметров командлета **Set-CsPersistentChatRoom** позволяет назначить пользователей чат следующим образом:</span><span class="sxs-lookup"><span data-stu-id="df00b-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="df00b-157">Members.</span><span class="sxs-lookup"><span data-stu-id="df00b-157">Members.</span></span> <span data-ttu-id="df00b-158">Задает членство для комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-158">Configures membership for the chat room.</span></span> <span data-ttu-id="df00b-159">Вы можете добавить или удалить одного или нескольких членов с помощью одного командлета, указав SIP-адрес пользователей.</span><span class="sxs-lookup"><span data-stu-id="df00b-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="df00b-160">Чтобы разрешить добавление группы пользователей, можно также указать организационные подразделения или группы рассылки Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df00b-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="df00b-161">Managers.</span><span class="sxs-lookup"><span data-stu-id="df00b-161">Managers.</span></span> <span data-ttu-id="df00b-162">Позволяет назначать диспетчеров в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="df00b-163">Диспетчеры обладают полномочиями определять членство комнаты чата наряду с установкой других параметров.</span><span class="sxs-lookup"><span data-stu-id="df00b-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="df00b-p114">Presenters. Позволяет назначать выступающих комнате-аудитории чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="df00b-166">Подробные сведения о синтаксисе, включая все параметры, [Скайп для консоли 2015 Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="df00b-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="df00b-167">Создание новой комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-167">Create a new room</span></span>

<span data-ttu-id="df00b-168">Создать новую комнату можно с помощью командлета **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="df00b-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="df00b-169">Например следующая команда создает новый чата с именем ITChatRoom на пул atl-cs-001.contoso.com. В этом примере добавляется комнаты чата категории ИТ:</span><span class="sxs-lookup"><span data-stu-id="df00b-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com. In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="df00b-170">**Примечание:** PersistentChatPoolFqdn не требуется, если выполняется одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="df00b-170">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="df00b-171">Существует только один пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-171">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="df00b-172">для категории указано полное доменное имя пула;</span><span class="sxs-lookup"><span data-stu-id="df00b-172">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="df00b-173">для добавления комнаты указывается полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="df00b-173">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="df00b-174">Настройка существующей комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-174">Configure an existing room</span></span>

<span data-ttu-id="df00b-175">Существующие комнаты можно настроить с помощью командлета **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="df00b-175">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="df00b-176">Например следующая команда назначает user1 как участник и докладчик и Пользователь2 Руководитель из testCat комнаты аудитория:</span><span class="sxs-lookup"><span data-stu-id="df00b-176">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="df00b-177">В следующем примере выполняется добавление в комнату чата NorthAmerica всех пользователей подразделения NorthAmericaUsers OU в Active Directory:</span><span class="sxs-lookup"><span data-stu-id="df00b-177">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="df00b-178">В следующем примере все участники группы рассылки Finance добавляются в ту же комнату чата:</span><span class="sxs-lookup"><span data-stu-id="df00b-178">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="df00b-179">Отключение или включение комнаты чата</span><span class="sxs-lookup"><span data-stu-id="df00b-179">Disable or enable a room</span></span>

<span data-ttu-id="df00b-180">Если раздел сохраняемого чата больше не является релевантным, можно сделать чат недоступен для пользователей, отключив его.</span><span class="sxs-lookup"><span data-stu-id="df00b-180">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="df00b-181">Если комната чата отключена, все подключенные на данный момент участники отключаются от нее.</span><span class="sxs-lookup"><span data-stu-id="df00b-181">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="df00b-182">Пользователи не могут снова подключиться к комнате чата или найти ее через поиск после ее отключения.</span><span class="sxs-lookup"><span data-stu-id="df00b-182">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="df00b-183">Если журнал чата повторяется, содержимое сохраняется при отключении комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="df00b-183">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="df00b-184">Но содержимое не будет отображаться в поиске, пока комната чата остается в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="df00b-184">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="df00b-185">Если включить ее позднее, пользователи смогут находить сообщения, опубликованные до того, как комната чата была отключена.</span><span class="sxs-lookup"><span data-stu-id="df00b-185">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="df00b-186">Сведения о настройке журнала чата [Управление категориями в Persistent Chat Server в Скайп для Business Server 2015](categories.md)см.</span><span class="sxs-lookup"><span data-stu-id="df00b-186">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="df00b-187">Если комната чата отключена, список ее членов и другие параметры сохраняются.</span><span class="sxs-lookup"><span data-stu-id="df00b-187">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="df00b-188">При повторном включении вам, как администратору, не потребуется создавать их вручную повторно.</span><span class="sxs-lookup"><span data-stu-id="df00b-188">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="df00b-189">Комнаты можно отключить с помощью командлета **Set-CsPersistentChatRoom** , значение True для параметра отключено:</span><span class="sxs-lookup"><span data-stu-id="df00b-189">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="df00b-190">Чтобы разрешить использование комнаты чата, задайте параметру Disabled значение False:</span><span class="sxs-lookup"><span data-stu-id="df00b-190">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False

```

## <a name="get-information-about-rooms"></a><span data-ttu-id="df00b-191">Получение сведений о комнат</span><span class="sxs-lookup"><span data-stu-id="df00b-191">Get information about rooms</span></span>

<span data-ttu-id="df00b-192">Получить сведения о комнатах, настроенных для использования в организации, можно с помощью командлета **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="df00b-192">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="df00b-193">Следующая команда возвращает сведения обо всех настроенных в организации комнатах чата:</span><span class="sxs-lookup"><span data-stu-id="df00b-193">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="df00b-194">Удаление всего содержимого из комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-194">Remove all content from a room</span></span>

<span data-ttu-id="df00b-p120">Удалить содержимое из комнаты можно с помощью командлета **Clear-CsPersistentChatRoom**. Например, следующая команда удалит из комнаты сохраняемого чата все содержимое, добавленное в нее до 1 марта 2015 г. включительно:</span><span class="sxs-lookup"><span data-stu-id="df00b-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="df00b-197">Удаление сообщения из комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-197">Remove a message from a room</span></span>

<span data-ttu-id="df00b-p121">Можно удалить одно или несколько сообщений из комнаты сохраняемого чата и при необходимости заменить какое-либо сообщение на стандартное или предоставленное администратором сообщение с помощью командлета **Remove-CsPersistentChatMessage**. Например, следующая команда удалит из комнаты чата ITChatRoom все сообщения, переданные пользователем kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="df00b-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="df00b-200">В следующем примере вместо удаленных сообщений отображается примечание о том, что сообщение уже не доступно:</span><span class="sxs-lookup"><span data-stu-id="df00b-200">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="df00b-201">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="df00b-201">Remove a room</span></span>

<span data-ttu-id="df00b-202">Удалить комнату можно с помощью командлета **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="df00b-202">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="df00b-203">Например, следующая команда удалит комнату чата RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="df00b-203">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="df00b-204">Перемещение комнаты из одной категории в другую</span><span class="sxs-lookup"><span data-stu-id="df00b-204">Move a room from one category to another</span></span>

<span data-ttu-id="df00b-p122">Если диспетчер комнаты чата имеет привилегии **автора** в другой категории, то он может переместить комнату из одной категории в другую. Комната не удаляется и воссоздается. Это изменение связи с базой данных.</span><span class="sxs-lookup"><span data-stu-id="df00b-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="df00b-p123">Изменение категории комнаты должно происходить редко и с осторожностью. Категория определяет разрешенное членство в комнате чата, поэтому при перемещении комнаты чата в другую категорию все системные списки управления доступом (SACL), которые более не поддерживаются новой категорией, очищаются. Например, если пользователь был членом комнаты и больше не относится к разрешенным участникам в новой категории, членство комнаты будет изменено, а пользователь будет удален из комнаты.</span><span class="sxs-lookup"><span data-stu-id="df00b-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

