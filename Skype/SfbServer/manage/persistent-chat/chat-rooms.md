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
ms.openlocfilehash: 25d13b8b44e16d476191fdae337eb72d73e77dbc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973777"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="c8da1-103">Управление комнатами чата на сервере сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c8da1-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c8da1-104">**Сводка:** Сведения об управлении Persistent Chat Server разговоров в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c8da1-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c8da1-105">Создание комнат чата и управление ими осуществляются значительно проще благодаря правильному использованию категорий.</span><span class="sxs-lookup"><span data-stu-id="c8da1-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="c8da1-106">Категория определяет пользователей, которые могут создавать или присоединиться к комнат чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="c8da1-107">Прежде чем пытаться управление комнат чата, обязательно прочитайте [сохраняемого чата категорий, комнат чата и роли пользователей в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) и [Управление категориями в Persistent Chat Server в Скайп для Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="c8da1-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8da1-108">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c8da1-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c8da1-109">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="c8da1-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="c8da1-110">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="c8da1-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="c8da1-111">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c8da1-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="c8da1-112">Можно настроить и управлять комнат чата, с помощью интерфейса командной строки Windows PowerShell или с помощью Скайп для клиента Business, если вы являетесь участником комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="c8da1-113">В этом разделе описываются способы управления комнатами с помощью интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="c8da1-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="c8da1-114">Если вы хотите управлять комнат чата с помощью Скайп для клиента Business, обратитесь к справке клиента.</span><span class="sxs-lookup"><span data-stu-id="c8da1-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="c8da1-115">Каналы, в может иметь одно из двух типов: обычный и аудитории.</span><span class="sxs-lookup"><span data-stu-id="c8da1-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="c8da1-116">В обычной комнате передавать и отправлять сообщения разрешается всем членам.</span><span class="sxs-lookup"><span data-stu-id="c8da1-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="c8da1-117">В комнату-аудиторию могут отправлять сообщения только выступающие, а остальные пользователи могут их читать.</span><span class="sxs-lookup"><span data-stu-id="c8da1-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="c8da1-118">Возможность доступа и управления комнатами чата зависит от пользовательских ролей следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c8da1-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="c8da1-119">Чтобы отправлять и читать сообщения, пользователи должны быть членами комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="c8da1-120">Выступающим разрешено передавать сообщения в комнаты-аудитории.</span><span class="sxs-lookup"><span data-stu-id="c8da1-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="c8da1-121">Администраторы могут удалять старое содержимое (например, содержимое, размещенное до определенной даты) из любой комнаты чата, чтобы база данных сильно не увеличивалась в размерах.</span><span class="sxs-lookup"><span data-stu-id="c8da1-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="c8da1-122">Кроме того, они могут удалить или заменить сообщения, которые кажутся несоответствующими данной комнате чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="c8da1-123">Сами пользователи, включая авторов сообщений, не могут удалять содержимое комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="c8da1-124">Диспетчеры комнат чата могут вносить изменения в любые свойства комнат (включая отключение комнат).</span><span class="sxs-lookup"><span data-stu-id="c8da1-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="c8da1-125">Но диспетчер комнаты чата не может удалить комнату или изменить ее категорию.</span><span class="sxs-lookup"><span data-stu-id="c8da1-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="c8da1-126">Только администраторы могут удалить комнату чата после ее создания.</span><span class="sxs-lookup"><span data-stu-id="c8da1-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="c8da1-127">Настраивать комнаты чата и управлять ими можно с помощью следующих командлетов Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c8da1-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="c8da1-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="c8da1-128">**Cmdlet**</span></span>|<span data-ttu-id="c8da1-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c8da1-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c8da1-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c8da1-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c8da1-131">Создание новой комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="c8da1-132">SET-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c8da1-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c8da1-133">Настройка параметров существующей комнаты; назначение пользователей и групп пользователей комнате</span><span class="sxs-lookup"><span data-stu-id="c8da1-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="c8da1-134">Командлет Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c8da1-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c8da1-135">Получение сведений о комнат</span><span class="sxs-lookup"><span data-stu-id="c8da1-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="c8da1-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="c8da1-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c8da1-137">Очистка комнаты или очистка сообщений в комнате</span><span class="sxs-lookup"><span data-stu-id="c8da1-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="c8da1-138">Remove Cspersistentchatroomnm</span><span class="sxs-lookup"><span data-stu-id="c8da1-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="c8da1-139">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="c8da1-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="c8da1-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="c8da1-141">Удаление сообщений из комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="c8da1-142">Командлет **New-CsPersistentChatRoom** используется для создания комнат чата, а командлет **Set-CsPersistentChatRoom** — для настройки существующей комнаты чата, включая добавление к ней пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8da1-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="c8da1-143">Можно настроить следующие параметры комнаты чата:</span><span class="sxs-lookup"><span data-stu-id="c8da1-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="c8da1-144">Disabled.</span><span class="sxs-lookup"><span data-stu-id="c8da1-144">Disabled.</span></span> <span data-ttu-id="c8da1-145">Позволяет включать или отключать комнату чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="c8da1-146">Приглашения.</span><span class="sxs-lookup"><span data-stu-id="c8da1-146">Invitations.</span></span> <span data-ttu-id="c8da1-147">Позволяет включить или отключить приглашения комнаты чата, используемые для уведомления пользователей, если они были добавлены в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="c8da1-148">Значение по умолчанию для приглашения в наследовать, которая вызвала чат принять приглашение параметры, настроенные на категории, к которой он принадлежит.</span><span class="sxs-lookup"><span data-stu-id="c8da1-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="c8da1-149">Настройка приглашения на параметр значение false на уровне комнаты чата позволяет переопределять параметр category.</span><span class="sxs-lookup"><span data-stu-id="c8da1-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="c8da1-150">Privacy.</span><span class="sxs-lookup"><span data-stu-id="c8da1-150">Privacy.</span></span> <span data-ttu-id="c8da1-151">Позволяет указать, будет ли комната чата открытой, закрытой или секретной.</span><span class="sxs-lookup"><span data-stu-id="c8da1-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="c8da1-152">Открытые комнаты могут отыскивать и использовать любые пользователи.</span><span class="sxs-lookup"><span data-stu-id="c8da1-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="c8da1-153">Закрытые комнаты могут отыскивать любые пользователи, но доступны они только их членам.</span><span class="sxs-lookup"><span data-stu-id="c8da1-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="c8da1-154">Секретные комнаты могут отыскивать и использовать только члены комнат.</span><span class="sxs-lookup"><span data-stu-id="c8da1-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="c8da1-155">По умолчанию все новые комнаты исходно настроены как закрытые.</span><span class="sxs-lookup"><span data-stu-id="c8da1-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="c8da1-156">Type.</span><span class="sxs-lookup"><span data-stu-id="c8da1-156">Type.</span></span> <span data-ttu-id="c8da1-157">Позволяет указать, является ли чата обычных комнаты, который принимает сообщений, отправленных любой элемент или помещении аудитория, который принимает сообщений, отправленных только выступающим.</span><span class="sxs-lookup"><span data-stu-id="c8da1-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="c8da1-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="c8da1-158">Addin.</span></span> <span data-ttu-id="c8da1-159">Позволяет связать ранее настроенную надстройку с комнатой чата, что позволяет членам комнаты, участвующим в беседе, просматривать содержимое по URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="c8da1-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="c8da1-160">Помимо приведенных выше параметров командлета **Set-CsPersistentChatRoom** позволяет назначить пользователей чат следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c8da1-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="c8da1-161">Members.</span><span class="sxs-lookup"><span data-stu-id="c8da1-161">Members.</span></span> <span data-ttu-id="c8da1-162">Задает членство для комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-162">Configures membership for the chat room.</span></span> <span data-ttu-id="c8da1-163">Вы можете добавить или удалить одного или нескольких членов с помощью одного командлета, указав SIP-адрес пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8da1-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="c8da1-164">Чтобы разрешить добавление группы пользователей, можно также указать организационные подразделения или группы рассылки Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8da1-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="c8da1-165">Managers.</span><span class="sxs-lookup"><span data-stu-id="c8da1-165">Managers.</span></span> <span data-ttu-id="c8da1-166">Позволяет назначать диспетчеров в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="c8da1-167">Диспетчеры обладают полномочиями определять членство комнаты чата наряду с установкой других параметров.</span><span class="sxs-lookup"><span data-stu-id="c8da1-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="c8da1-p115">Presenters. Позволяет назначать выступающих комнате-аудитории чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-p115">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="c8da1-170">Подробные сведения о синтаксисе, включая все параметры, [Скайп для консоли 2015 Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="c8da1-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="c8da1-171">Создание новой комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-171">Create a new room</span></span>

<span data-ttu-id="c8da1-172">Создать новую комнату можно с помощью командлета **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="c8da1-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="c8da1-173">Например, следующая команда создаст новую комнату чата с именем ITChatRoom в пуле atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c8da1-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="c8da1-174">В данном примере комната чата добавлена в категорию IT:</span><span class="sxs-lookup"><span data-stu-id="c8da1-174">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="c8da1-175">**Примечание:** PersistentChatPoolFqdn не требуется, если выполняется одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="c8da1-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="c8da1-176">Существует только один пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="c8da1-177">для категории указано полное доменное имя пула;</span><span class="sxs-lookup"><span data-stu-id="c8da1-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="c8da1-178">для добавления комнаты указывается полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="c8da1-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="c8da1-179">Настройка существующей комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-179">Configure an existing room</span></span>

<span data-ttu-id="c8da1-180">Существующие комнаты можно настроить с помощью командлета **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="c8da1-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="c8da1-181">Например следующая команда назначает user1 как участник и докладчик и Пользователь2 Руководитель из testCat комнаты аудитория:</span><span class="sxs-lookup"><span data-stu-id="c8da1-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="c8da1-182">В следующем примере выполняется добавление в комнату чата NorthAmerica всех пользователей подразделения NorthAmericaUsers OU в Active Directory:</span><span class="sxs-lookup"><span data-stu-id="c8da1-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="c8da1-183">В следующем примере все участники группы рассылки Finance добавляются в ту же комнату чата:</span><span class="sxs-lookup"><span data-stu-id="c8da1-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="c8da1-184">Отключение или включение комнаты чата</span><span class="sxs-lookup"><span data-stu-id="c8da1-184">Disable or enable a room</span></span>

<span data-ttu-id="c8da1-185">Если раздел сохраняемого чата больше не является релевантным, можно сделать чат недоступен для пользователей, отключив его.</span><span class="sxs-lookup"><span data-stu-id="c8da1-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="c8da1-186">Если комната чата отключена, все подключенные на данный момент участники отключаются от нее.</span><span class="sxs-lookup"><span data-stu-id="c8da1-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="c8da1-187">Пользователи не могут снова подключиться к комнате чата или найти ее через поиск после ее отключения.</span><span class="sxs-lookup"><span data-stu-id="c8da1-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="c8da1-188">Если журнал чата повторяется, содержимое сохраняется при отключении комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="c8da1-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="c8da1-189">Но содержимое не будет отображаться в поиске, пока комната чата остается в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="c8da1-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="c8da1-190">Если включить ее позднее, пользователи смогут находить сообщения, опубликованные до того, как комната чата была отключена.</span><span class="sxs-lookup"><span data-stu-id="c8da1-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="c8da1-191">Сведения о настройке журнала чата [Управление категориями в Persistent Chat Server в Скайп для Business Server 2015](categories.md)см.</span><span class="sxs-lookup"><span data-stu-id="c8da1-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="c8da1-192">Если комната чата отключена, список ее членов и другие параметры сохраняются.</span><span class="sxs-lookup"><span data-stu-id="c8da1-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="c8da1-193">При повторном включении вам, как администратору, не потребуется создавать их вручную повторно.</span><span class="sxs-lookup"><span data-stu-id="c8da1-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="c8da1-194">Комнаты можно отключить с помощью командлета **Set-CsPersistentChatRoom** , значение True для параметра отключено:</span><span class="sxs-lookup"><span data-stu-id="c8da1-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="c8da1-195">Чтобы разрешить использование комнаты чата, задайте параметру Disabled значение False:</span><span class="sxs-lookup"><span data-stu-id="c8da1-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="c8da1-196">Получение сведений о комнат</span><span class="sxs-lookup"><span data-stu-id="c8da1-196">Get information about rooms</span></span>

<span data-ttu-id="c8da1-197">Получить сведения о комнатах, настроенных для использования в организации, можно с помощью командлета **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="c8da1-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="c8da1-198">Следующая команда возвращает сведения обо всех настроенных в организации комнатах чата:</span><span class="sxs-lookup"><span data-stu-id="c8da1-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="c8da1-199">Удаление всего содержимого из комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-199">Remove all content from a room</span></span>

<span data-ttu-id="c8da1-p121">Удалить содержимое из комнаты можно с помощью командлета **Clear-CsPersistentChatRoom**. Например, следующая команда удалит из комнаты сохраняемого чата все содержимое, добавленное в нее до 1 марта 2015 г. включительно:</span><span class="sxs-lookup"><span data-stu-id="c8da1-p121">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="c8da1-202">Удаление сообщения из комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-202">Remove a message from a room</span></span>

<span data-ttu-id="c8da1-p122">Можно удалить одно или несколько сообщений из комнаты сохраняемого чата и при необходимости заменить какое-либо сообщение на стандартное или предоставленное администратором сообщение с помощью командлета **Remove-CsPersistentChatMessage**. Например, следующая команда удалит из комнаты чата ITChatRoom все сообщения, переданные пользователем kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="c8da1-p122">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="c8da1-205">В следующем примере вместо удаленных сообщений отображается примечание о том, что сообщение уже не доступно:</span><span class="sxs-lookup"><span data-stu-id="c8da1-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="c8da1-206">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="c8da1-206">Remove a room</span></span>

<span data-ttu-id="c8da1-207">Удалить комнату можно с помощью командлета **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="c8da1-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="c8da1-208">Например, следующая команда удалит комнату чата RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="c8da1-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="c8da1-209">Перемещение комнаты из одной категории в другую</span><span class="sxs-lookup"><span data-stu-id="c8da1-209">Move a room from one category to another</span></span>

<span data-ttu-id="c8da1-p123">Если диспетчер комнаты чата имеет привилегии **автора** в другой категории, то он может переместить комнату из одной категории в другую. Комната не удаляется и воссоздается. Это изменение связи с базой данных.</span><span class="sxs-lookup"><span data-stu-id="c8da1-p123">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="c8da1-p124">Изменение категории комнаты должно происходить редко и с осторожностью. Категория определяет разрешенное членство в комнате чата, поэтому при перемещении комнаты чата в другую категорию все системные списки управления доступом (SACL), которые более не поддерживаются новой категорией, очищаются. Например, если пользователь был членом комнаты и больше не относится к разрешенным участникам в новой категории, членство комнаты будет изменено, а пользователь будет удален из комнаты.</span><span class="sxs-lookup"><span data-stu-id="c8da1-p124">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

