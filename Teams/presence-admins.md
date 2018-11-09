---
title: Сведения о присутствии пользователя в группах
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rakayala
description: Сведения о "Администраторы" иметь представление о присутствии в группах.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1934a602d89240c89ffb4f7410192d19a7dd2e61
ms.sourcegitcommit: 139b3d3b7fcc1dd7fba7fd14ff34e4ffdfcc7eeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2018
ms.locfileid: "26038881"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="0d795-103">Сведения о присутствии пользователя в группах</span><span class="sxs-lookup"><span data-stu-id="0d795-103">User Presence in Teams</span></span>

<span data-ttu-id="0d795-104">Сведения о присутствии является частью профиля пользователя в группах Майкрософт (и, в Office 365) — и указывает пользователя текущего уровня доступности и состояния другим пользователям в организации.</span><span class="sxs-lookup"><span data-stu-id="0d795-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="0d795-105">По умолчанию каждому в вашей организации, с помощью команды изучить ли другим пользователям, доступные через Интернет.</span><span class="sxs-lookup"><span data-stu-id="0d795-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="0d795-106">Состояния присутствия в группах</span><span class="sxs-lookup"><span data-stu-id="0d795-106">Presence states in Teams</span></span>

<span data-ttu-id="0d795-107">Состояние присутствия пользователя, доступные в группах являются:</span><span class="sxs-lookup"><span data-stu-id="0d795-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="0d795-108">Настроенные пользователем</span><span class="sxs-lookup"><span data-stu-id="0d795-108">User configured</span></span>|<span data-ttu-id="0d795-109">Настроить приложение</span><span class="sxs-lookup"><span data-stu-id="0d795-109">App configured</span></span>|
|:--- |:---|
| ![Доступные сведения о присутствии](media/Presence_Available.png) <span data-ttu-id="0d795-111">Доступно</span><span class="sxs-lookup"><span data-stu-id="0d795-111">Available</span></span>|![Доступные сведения о присутствии](media/Presence_Available.png) <span data-ttu-id="0d795-113">Доступно</span><span class="sxs-lookup"><span data-stu-id="0d795-113">Available</span></span>|
|| ![доступные об отсутствии на работе](media/Presence_Available_OOF.png) <span data-ttu-id="0d795-115">Доступные нет на месте</span><span class="sxs-lookup"><span data-stu-id="0d795-115">Available, Out of Office</span></span> |
|  ![«Занят»](media/Presence_Busy.png) <span data-ttu-id="0d795-117">«Занят»</span><span class="sxs-lookup"><span data-stu-id="0d795-117">Busy</span></span> |  ![«Занят»](media/Presence_Busy.png) <span data-ttu-id="0d795-119">«Занят»</span><span class="sxs-lookup"><span data-stu-id="0d795-119">Busy</span></span>  |
|| ![«Занят»](media/Presence_Busy.png) <span data-ttu-id="0d795-121">В ходе звонка</span><span class="sxs-lookup"><span data-stu-id="0d795-121">In a call</span></span>|
|| ![«Занят»](media/Presence_Busy.png) <span data-ttu-id="0d795-123">В ходе собрания</span><span class="sxs-lookup"><span data-stu-id="0d795-123">In a meeting</span></span> |
|| ![«занят» об отсутствии на работе](media/Presence_Busy_OOF.png) <span data-ttu-id="0d795-125">В ходе звонка, нет на месте</span><span class="sxs-lookup"><span data-stu-id="0d795-125">In a call, out of office</span></span>|
|  ![«Не беспокоить»](media/Presence_DND.png) <span data-ttu-id="0d795-127">«Не беспокоить»</span><span class="sxs-lookup"><span data-stu-id="0d795-127">Do not disturb</span></span> ||
|| ![«Не беспокоить»](media/Presence_DND.png) <span data-ttu-id="0d795-129">Представления</span><span class="sxs-lookup"><span data-stu-id="0d795-129">Presenting</span></span>|
| ![Нет на месте](media/Presence_Away.png) <span data-ttu-id="0d795-131">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="0d795-131">Away</span></span>| ![Нет на месте](media/Presence_Away.png) <span data-ttu-id="0d795-133">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="0d795-133">Away</span></span>|
|| <span data-ttu-id="0d795-134">![Нет на месте](media/Presence_Away.png) от последнего показано *время*</span><span class="sxs-lookup"><span data-stu-id="0d795-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Нет на месте](media/Presence_Away.png) <span data-ttu-id="0d795-136">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="0d795-136">Be right back</span></span>| |
|| ![Нет на месте](media/Presence_Away.png)  <span data-ttu-id="0d795-138">Не на работе</span><span class="sxs-lookup"><span data-stu-id="0d795-138">Off Work</span></span>|
|| ![Автономный режим](media/Presence_Offline.png) <span data-ttu-id="0d795-140">Автономный режим</span><span class="sxs-lookup"><span data-stu-id="0d795-140">Offline</span></span> |
|| ![Неизвестный](media/Presence_Unknown.png) <span data-ttu-id="0d795-142">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="0d795-142">Status unknown</span></span>|
||![заблокировано](media/Presence_Blocked.png) <span data-ttu-id="0d795-144">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="0d795-144">Blocked</span></span> |
|| ![Нет на месте](media/Presence_OOF.png) <span data-ttu-id="0d795-146">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="0d795-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="0d795-147">Пользователи могут вручную устанавливать свое состояние присутствия на некоторые параметры и их состояний получает отражены другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="0d795-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="0d795-148">Сведения о присутствии дополнительных пользователей также автоматически обновляются на основе действие пользователя (например, «доступен» или «нет на месте), состояния календаря Outlook (например, собрания) или группам состояния приложения (в ходе звонка Presenting), чтобы состояния, которые расположены в списке.</span><span class="sxs-lookup"><span data-stu-id="0d795-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="0d795-149">Существует время ожидания простоя 15 минут, после чего текущее состояние присутствия пользователей восстановит нет на месте.</span><span class="sxs-lookup"><span data-stu-id="0d795-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="0d795-150">Пользователи могут указать, кто может перестать работать, (обратитесь к нему переопределения не беспокоить параметр).</span><span class="sxs-lookup"><span data-stu-id="0d795-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="0d795-151">Эти параметры, доступные в приложении.</span><span class="sxs-lookup"><span data-stu-id="0d795-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="0d795-152">Группы, не является Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0d795-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="0d795-153">Следующие параметры администрирования в Скайп для бизнеса, отличаются в группах:</span><span class="sxs-lookup"><span data-stu-id="0d795-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="0d795-154">Совместное использование сведений о присутствии всегда включена в группах для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="0d795-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="0d795-155">Настройки конфиденциальности (Выбор, кто может просматривать сведения о присутствии) недоступен в группах.</span><span class="sxs-lookup"><span data-stu-id="0d795-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="0d795-156">Сведения о присутствии, общий доступ для всех пользователей (включая федеративных служб) всегда включена для пользователей в группах.</span><span class="sxs-lookup"><span data-stu-id="0d795-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="0d795-157">Список контактов (если они были в SfB) будет отображаться в разделе **чата > контакты** или в разделе **вызовы > контакты**.</span><span class="sxs-lookup"><span data-stu-id="0d795-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="0d795-158">Возможности клиента не беспокоить и уровень всегда включена для пользователей в группах.</span><span class="sxs-lookup"><span data-stu-id="0d795-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="0d795-159">Календарь (в том числе об отсутствии на работе и другие сведения из календаря) интеграция всегда включена для пользователей в группах, интеграции с Outlook.</span><span class="sxs-lookup"><span data-stu-id="0d795-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="0d795-160">*Последнее обнаружение* или *Нет на месте с момента* (если в среде с двумя с Скайп для бизнеса) индикатор всегда включена для пользователей в группах.</span><span class="sxs-lookup"><span data-stu-id="0d795-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>
- <span data-ttu-id="0d795-161">Установка состояния присутствия настраиваемых не включен для пользователей в группах.</span><span class="sxs-lookup"><span data-stu-id="0d795-161">Setting a custom presence status is not enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0d795-162">Возможность команды администратора настроить эти параметры в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0d795-162">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="0d795-163">Совместная работа с Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0d795-163">Coexistence with Skype for Business</span></span>

<span data-ttu-id="0d795-164">Для получения дополнительных сведений на действия группы присутствия при Сосуществование с Скайп для бизнеса в разделе [Совместная работа с Скайп для бизнеса](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="0d795-164">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 