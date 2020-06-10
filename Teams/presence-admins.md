---
title: Присутствие пользователей в Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Сведения о состояниях присутствия в Teams, а также об административных параметрах для функции присутствия.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 249fbd646cf6c01f282fe73b28e9d02ec48db90b
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665981"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="8c62b-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="8c62b-103">User presence in Teams</span></span>

<span data-ttu-id="8c62b-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в Microsoft 365 или Office 365), указывающая на текущую доступность пользователя и его состояние другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="8c62b-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="8c62b-105">По умолчанию все пользователи в организации, в которой используется Teams, могут (практически в режиме реального времени) видеть, находятся ли в сети другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="8c62b-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="8c62b-106">Сведения о присутствии Teams в Outlook поддерживаются в классическом приложении Outlook 2013 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="8c62b-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="8c62b-107">Состояния присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="8c62b-107">Presence states in Teams</span></span>

|<span data-ttu-id="8c62b-108">Настроено пользователем</span><span class="sxs-lookup"><span data-stu-id="8c62b-108">User configured</span></span>|<span data-ttu-id="8c62b-109">Настроено в приложении</span><span class="sxs-lookup"><span data-stu-id="8c62b-109">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="8c62b-111">В сети</span><span class="sxs-lookup"><span data-stu-id="8c62b-111">Available</span></span>|![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="8c62b-113">В сети</span><span class="sxs-lookup"><span data-stu-id="8c62b-113">Available</span></span>|
|| ![Открытый зеленый флажок означает "В сети, нет на месте"](media/Presence_Available_OOF.png) <span data-ttu-id="8c62b-115">В сети, нет на месте</span><span class="sxs-lookup"><span data-stu-id="8c62b-115">Available, Out of Office</span></span> |
|  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="8c62b-117">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="8c62b-117">Busy</span></span> |  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="8c62b-119">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="8c62b-119">Busy</span></span>  |
|| ![Сплошной красный кружок означает "Занят(а), говорю по телефону"](media/Presence_Busy.png) <span data-ttu-id="8c62b-121">Говорю по телефону</span><span class="sxs-lookup"><span data-stu-id="8c62b-121">On a call</span></span>|
|| ![Сплошной красный кружок означает "Занят(а), на собрании"](media/Presence_Busy.png) <span data-ttu-id="8c62b-123">На собрании</span><span class="sxs-lookup"><span data-stu-id="8c62b-123">In a meeting</span></span> |
|| ![Открытый красный кружок означает "Занят(а)"](media/Presence_Busy_OOF.png) <span data-ttu-id="8c62b-125">Говорю по телефону, нет на месте</span><span class="sxs-lookup"><span data-stu-id="8c62b-125">On a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "Не беспокоить"](media/Presence_DND.png) <span data-ttu-id="8c62b-127">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="8c62b-127">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией означает "Показ презентации"](media/Presence_DND.png) <span data-ttu-id="8c62b-129">Показ презентации</span><span class="sxs-lookup"><span data-stu-id="8c62b-129">Presenting</span></span>|
|| ![Красный кружок с белой линией означает "Концентрация"](media/Presence_DND.png) <span data-ttu-id="8c62b-131">Концентрация</span><span class="sxs-lookup"><span data-stu-id="8c62b-131">Focusing</span></span>|
| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="8c62b-133">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="8c62b-133">Away</span></span>| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="8c62b-135">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="8c62b-135">Away</span></span>|
|| <span data-ttu-id="8c62b-136">![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) Последний раз в сети в *время*</span><span class="sxs-lookup"><span data-stu-id="8c62b-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов означает "Отсутствую, скоро вернусь"](media/Presence_Away.png) <span data-ttu-id="8c62b-138">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="8c62b-138">Be right back</span></span>| |
|| ![Желтый значок часов означает "Отсутствую, не на работе"](media/Presence_Away.png)  <span data-ttu-id="8c62b-140">Не на работе</span><span class="sxs-lookup"><span data-stu-id="8c62b-140">Off Work</span></span>|
|| ![Серый кружок со знаком "Х" означает "Автономный режим"](media/Presence_Offline.png) <span data-ttu-id="8c62b-142">Автономный режим</span><span class="sxs-lookup"><span data-stu-id="8c62b-142">Offline</span></span> |
|| ![Открытый серый кружок означает "Состояние неизвестно"](media/Presence_Unknown.png) <span data-ttu-id="8c62b-144">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="8c62b-144">Status unknown</span></span>|
||![Открытый красный кружок с линией по диагонали означает "Заблокировано"](media/Presence_Blocked.png) <span data-ttu-id="8c62b-146">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="8c62b-146">Blocked</span></span> |
|| ![Сиреневый кружок со стрелкой означает "Нет на месте"](media/Presence_OOF.png) <span data-ttu-id="8c62b-148">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="8c62b-148">Out of Office</span></span>|
|||

<span data-ttu-id="8c62b-149">Состояния присутствия, настроенные приложением, основываются на действиях пользователя (доступно, нет), состояниях календаря Outlook (на собрании) и о состояниях приложений Teams (во время звонка).</span><span class="sxs-lookup"><span data-stu-id="8c62b-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="8c62b-150">Текущее состояние присутствия будет изменено на "нет на месте", если вы блокируете компьютер, а затем переходите в режим сна или в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="8c62b-150">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="8c62b-151">На мобильном устройстве состояние присутствия меняется на "нет на месте", если приложение Teams находится в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="8c62b-151">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="8c62b-152">Пользователи получают все сообщения, отправленные им в чатах Teams, независимо от состояния их присутствия.</span><span class="sxs-lookup"><span data-stu-id="8c62b-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="8c62b-153">При отправке сообщения в чате пользователю, который находится не в сети, это сообщение чата появится в Teams, когда пользователь окажется в сети.</span><span class="sxs-lookup"><span data-stu-id="8c62b-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="8c62b-154">Если пользователь не находится в режиме "не беспокоить", он по-прежнему будет получать сообщения в чате, но уведомления на экране приветствия не отображаются.</span><span class="sxs-lookup"><span data-stu-id="8c62b-154">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="8c62b-155">Пользователи получают звонки во всех состояниях присутствия, кроме Do "не беспокоить", в котором входящие звонки проходят на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="8c62b-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="8c62b-156">Если получатель заблокировал звонящего , звонок не будет доставлен, а для звонящего присутствие вызываемого абонента отобразится как "Не в сети".</span><span class="sxs-lookup"><span data-stu-id="8c62b-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="8c62b-157">Пользователь может добавлять других пользователей в свой список приоритетного доступа, перейдя в **Параметры** > **Конфиденциальность** в Teams.</span><span class="sxs-lookup"><span data-stu-id="8c62b-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="8c62b-158">Пользователи, у которых есть приоритет доступа, могут связываться с пользователем, даже если пользователь находится в разделе "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="8c62b-158">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="8c62b-159">Параметры администрирования в Teams по сравнению с параметрами в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8c62b-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="8c62b-160">Параметры администрирования в Teams, которые отличаются от параметров в Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="8c62b-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="8c62b-161">В Teams возможность поделиться присутствием для пользователей организации всегда включена.</span><span class="sxs-lookup"><span data-stu-id="8c62b-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="8c62b-162">Настройка конфиденциальности (когда можно определять, кто может видеть присутствие) в Teams недоступна.</span><span class="sxs-lookup"><span data-stu-id="8c62b-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="8c62b-163">Для пользователей в Teams всегда включена возможность поделиться присутствием со всеми пользователями , в том числе федеративными службами.</span><span class="sxs-lookup"><span data-stu-id="8c62b-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="8c62b-164">Список контактов (если он был у пользователя в Skype для бизнеса) отображается в**Чат > Контакты** или в **Звонки> Контакты**.</span><span class="sxs-lookup"><span data-stu-id="8c62b-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="8c62b-165">Для пользователей в Teams функции клиента "Не беспокоить" и "Прорыв" всегда включены.</span><span class="sxs-lookup"><span data-stu-id="8c62b-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="8c62b-166">При интеграции Teams c Outlook интеграция календаря (включая данные об отсутствии на месте и другие данные календаря) для пользователей всегда включена.</span><span class="sxs-lookup"><span data-stu-id="8c62b-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="8c62b-167">Индикатор *Последний раз в сети* или*Отсутствую с* всегда включен для пользователей Teams, если в организации также используется Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="8c62b-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="8c62b-168">Возможность настройки этих параметров администратором в Teams в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8c62b-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="8c62b-169">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8c62b-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="8c62b-170">Дополнительные сведения о том, как функционирует присутствие Teams, если в организации используется также Skype для бизнеса, см. в статье [Сосуществование со Skype для бизнеса](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="8c62b-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
