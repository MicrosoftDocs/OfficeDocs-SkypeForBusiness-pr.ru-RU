---
title: Присутствие пользователей в Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Администраторы информации должны понимать состояние присутствия в Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fd6ac289df238d9f410266b1eca43a3a18f493e
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548527"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="3e6ee-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="3e6ee-103">User Presence in Teams</span></span>

<span data-ttu-id="3e6ee-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в рамках Office 365), а также сведения о его доступности и состоянии другим пользователям в Организации.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="3e6ee-105">По умолчанию любой пользователь в вашей организации, использующий Teams, может видеться практически в реальном времени, независимо от того, доступны ли другие пользователи в сети.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-105">By default, anyone in your organization using Teams can see - in nearly real time - whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="3e6ee-106">Состояние присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="3e6ee-106">Presence states in Teams</span></span>

<span data-ttu-id="3e6ee-107">Состояние присутствия пользователя доступно в teams:</span><span class="sxs-lookup"><span data-stu-id="3e6ee-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="3e6ee-108">Настраиваемый пользователем</span><span class="sxs-lookup"><span data-stu-id="3e6ee-108">User configured</span></span>|<span data-ttu-id="3e6ee-109">Настроенное приложение</span><span class="sxs-lookup"><span data-stu-id="3e6ee-109">App configured</span></span>|
|:--- |:---|
| ![Сплошная зеленая отметка чек, указывающая на наличие свободного места](media/Presence_Available.png) <span data-ttu-id="3e6ee-111">Доступно</span><span class="sxs-lookup"><span data-stu-id="3e6ee-111">Available</span></span>|![Сплошная зеленая отметка чек, указывающая на наличие свободного места](media/Presence_Available.png) <span data-ttu-id="3e6ee-113">Доступно</span><span class="sxs-lookup"><span data-stu-id="3e6ee-113">Available</span></span>|
|| ![Открыть зеленый отметку чек, указывающую на доступное отсутствие на работе](media/Presence_Available_OOF.png) <span data-ttu-id="3e6ee-115">Доступно, нет на месте</span><span class="sxs-lookup"><span data-stu-id="3e6ee-115">Available, Out of Office</span></span> |
|  ![Сплошной красный круг, обозначающий "занято"](media/Presence_Busy.png) <span data-ttu-id="3e6ee-117">Сильно</span><span class="sxs-lookup"><span data-stu-id="3e6ee-117">Busy</span></span> |  ![Сильно](media/Presence_Busy.png) <span data-ttu-id="3e6ee-119">Сильно</span><span class="sxs-lookup"><span data-stu-id="3e6ee-119">Busy</span></span>  |
|| ![Сплошной красный круг, указывающий на то, что звонок занят](media/Presence_Busy.png) <span data-ttu-id="3e6ee-121">В звонке</span><span class="sxs-lookup"><span data-stu-id="3e6ee-121">In a call</span></span>|
|| ![Сплошной красный круг, указывающий на то, что собрание занято](media/Presence_Busy.png) <span data-ttu-id="3e6ee-123">На собрании</span><span class="sxs-lookup"><span data-stu-id="3e6ee-123">In a meeting</span></span> |
|| ![Открытие красного круга, указывающего на занятие](media/Presence_Busy_OOF.png) <span data-ttu-id="3e6ee-125">В звонке, нет на месте</span><span class="sxs-lookup"><span data-stu-id="3e6ee-125">In a call, out of office</span></span>|
|  ![Красный кружок с белой линией, указывающая "не беспокоить"](media/Presence_DND.png) <span data-ttu-id="3e6ee-127">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="3e6ee-127">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией, обозначающая представление](media/Presence_DND.png) <span data-ttu-id="3e6ee-129">Указав</span><span class="sxs-lookup"><span data-stu-id="3e6ee-129">Presenting</span></span>|
| ![Желтый значок часов, обозначающий состояние "нет на месте"](media/Presence_Away.png) <span data-ttu-id="3e6ee-131">Уйти</span><span class="sxs-lookup"><span data-stu-id="3e6ee-131">Away</span></span>| ![уйти](media/Presence_Away.png) <span data-ttu-id="3e6ee-133">Уйти</span><span class="sxs-lookup"><span data-stu-id="3e6ee-133">Away</span></span>|
|| <span data-ttu-id="3e6ee-134">![Значок желтого синхронизирующего импульса](media/Presence_Away.png) , указывающий на отсутствие последнего замеченного *времени*</span><span class="sxs-lookup"><span data-stu-id="3e6ee-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов, указывающий на нет, должен быть сзади](media/Presence_Away.png) <span data-ttu-id="3e6ee-136">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="3e6ee-136">Be right back</span></span>| |
|| ![Желтый значок часов, обозначающий состояние "нет на месте"](media/Presence_Away.png)  <span data-ttu-id="3e6ee-138">Не на работе</span><span class="sxs-lookup"><span data-stu-id="3e6ee-138">Off Work</span></span>|
|| ![Серый круг с крестиком, обозначающий "не в сети"](media/Presence_Offline.png) <span data-ttu-id="3e6ee-140">Доступ</span><span class="sxs-lookup"><span data-stu-id="3e6ee-140">Offline</span></span> |
|| ![Открыть серый круг, обозначающий состояние Unknown](media/Presence_Unknown.png) <span data-ttu-id="3e6ee-142">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="3e6ee-142">Status unknown</span></span>|
||![Открытие красного круга с диагональной линией, означающей "заблокировано"](media/Presence_Blocked.png) <span data-ttu-id="3e6ee-144">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="3e6ee-144">Blocked</span></span> |
|| ![Сиреневый круг со стрелкой, указывающей на наличие отсутствия на рабочем месте](media/Presence_OOF.png) <span data-ttu-id="3e6ee-146">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="3e6ee-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="3e6ee-147">Пользователи могут вручную установить для своего текущего состояния присутствия некоторые параметры, и их состояние будет отражено для всех других пользователей.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="3e6ee-148">Дополнительные сведения о присутствии пользователя также автоматически обновляются в зависимости от действий пользователя (например, "доступно" или "нет на месте"), состояний календаря Outlook (например, на собрании) и состояний приложения Teams (в вызове, презентации) до состояний с отступом в списке.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="3e6ee-149">Время ожидания бездействия в течение 15 минут, после которого текущее состояние присутствия пользователя будет сброшено на нет на месте.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="3e6ee-150">Пользователи могут определять, кому разрешено переключаться (общаться с параметром "не беспокоить").</span><span class="sxs-lookup"><span data-stu-id="3e6ee-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="3e6ee-151">Эти параметры доступны в приложении.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="3e6ee-152">Teams не является Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3e6ee-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="3e6ee-153">Следующие параметры администратора в Skype для бизнеса отличаются в teams:</span><span class="sxs-lookup"><span data-stu-id="3e6ee-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="3e6ee-154">Общий доступ к присутствию всегда включен в Teams для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="3e6ee-155">Конфиденциальность (принятие решения о том, кто может видеть состояние присутствия) недоступен в Teams.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="3e6ee-156">Предоставление общего предоставления сведений о присутствии для всех пользователей (в том числе федеративных служб) всегда разрешено пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="3e6ee-157">Список контактов (если они в SfB) видны в разделе **чат _Гт_ Contacts (контакты** ) или в разделе **звонки _гт_ контакты**.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="3e6ee-158">Клиент не переносятся, а функции, появляющиеся неактивными, всегда включаются для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="3e6ee-159">В приложении "Календарь" (включая _Амп_ другую информацию календаря) всегда включена интеграция для пользователей в Teams, если они интегрированы с Outlook.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="3e6ee-160">Режим *последнего* просмотра ( \*\* если в двойной среде с поддержкой Skype для бизнеса) всегда включен для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3e6ee-161">Возможность администраторам Teams настраивать эти параметры в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3e6ee-161">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="3e6ee-162">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3e6ee-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="3e6ee-163">Узнайте подробнее о том, как работает функция присутствия в Skype для бизнеса, в [Skype для бизнеса](coexistence-chat-calls-presence.md) .</span><span class="sxs-lookup"><span data-stu-id="3e6ee-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
