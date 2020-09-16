---
title: Присутствие пользователей в Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 3a5adfcfd6002f9069934bb25dde5aa8b51e452f
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820523"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="f45eb-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="f45eb-103">User presence in Teams</span></span>

<span data-ttu-id="f45eb-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в Microsoft 365 или Office 365), указывающая на текущую доступность пользователя и его состояние другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="f45eb-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="f45eb-105">По умолчанию все пользователи в организации, в которой используется Teams, могут (практически в режиме реального времени) видеть, находятся ли в сети другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="f45eb-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="f45eb-106">Сведения о присутствии Teams в Outlook поддерживаются в классическом приложении Outlook 2013 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="f45eb-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="f45eb-107">Подробные сведения о профилях пользователей Teams на разных платформах можно найти в разделе [функции групп на платформе](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="f45eb-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="f45eb-108">Состояния присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="f45eb-108">Presence states in Teams</span></span>

|<span data-ttu-id="f45eb-109">Настроено пользователем</span><span class="sxs-lookup"><span data-stu-id="f45eb-109">User configured</span></span>|<span data-ttu-id="f45eb-110">Настроено в приложении</span><span class="sxs-lookup"><span data-stu-id="f45eb-110">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="f45eb-112">В сети</span><span class="sxs-lookup"><span data-stu-id="f45eb-112">Available</span></span>|![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="f45eb-114">В сети</span><span class="sxs-lookup"><span data-stu-id="f45eb-114">Available</span></span>|
|| ![Открытый зеленый флажок означает "В сети, нет на месте"](media/Presence_Available_OOF.png) <span data-ttu-id="f45eb-116">В сети, нет на месте</span><span class="sxs-lookup"><span data-stu-id="f45eb-116">Available, Out of Office</span></span> |
|  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="f45eb-118">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="f45eb-118">Busy</span></span> |  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="f45eb-120">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="f45eb-120">Busy</span></span>  |
|| ![Сплошной красный кружок означает "Занят(а), говорю по телефону"](media/Presence_Busy.png) <span data-ttu-id="f45eb-122">Говорю по телефону</span><span class="sxs-lookup"><span data-stu-id="f45eb-122">On a call</span></span>|
|| ![Сплошной красный кружок означает "Занят(а), на собрании"](media/Presence_Busy.png) <span data-ttu-id="f45eb-124">На собрании</span><span class="sxs-lookup"><span data-stu-id="f45eb-124">In a meeting</span></span> |
|| ![Открытый красный кружок означает "Занят(а)"](media/Presence_Busy_OOF.png) <span data-ttu-id="f45eb-126">Говорю по телефону, нет на месте</span><span class="sxs-lookup"><span data-stu-id="f45eb-126">On a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "Не беспокоить"](media/Presence_DND.png) <span data-ttu-id="f45eb-128">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="f45eb-128">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией означает "Показ презентации"](media/Presence_DND.png) <span data-ttu-id="f45eb-130">Показ презентации</span><span class="sxs-lookup"><span data-stu-id="f45eb-130">Presenting</span></span>|
|| ![Красный кружок с белой линией означает "Концентрация"](media/Presence_DND.png) <span data-ttu-id="f45eb-132">Концентрация</span><span class="sxs-lookup"><span data-stu-id="f45eb-132">Focusing</span></span>|
| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="f45eb-134">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="f45eb-134">Away</span></span>| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="f45eb-136">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="f45eb-136">Away</span></span>|
|| <span data-ttu-id="f45eb-137">![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) Последний раз в сети в *время*</span><span class="sxs-lookup"><span data-stu-id="f45eb-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов означает "Отсутствую, скоро вернусь"](media/Presence_Away.png) <span data-ttu-id="f45eb-139">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="f45eb-139">Be right back</span></span>| |
|| ![Желтый значок часов означает "Отсутствую, не на работе"](media/Presence_Away.png)  <span data-ttu-id="f45eb-141">Не на работе</span><span class="sxs-lookup"><span data-stu-id="f45eb-141">Off Work</span></span>|
|| ![Серый кружок со знаком "Х" означает "Автономный режим"](media/Presence_Offline.png) <span data-ttu-id="f45eb-143">Автономный режим</span><span class="sxs-lookup"><span data-stu-id="f45eb-143">Offline</span></span> |
|| ![Открытый серый кружок означает "Состояние неизвестно"](media/Presence_Unknown.png) <span data-ttu-id="f45eb-145">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="f45eb-145">Status unknown</span></span>|
||![Открытый красный кружок с линией по диагонали означает "Заблокировано"](media/Presence_Blocked.png) <span data-ttu-id="f45eb-147">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="f45eb-147">Blocked</span></span> |
|| ![Сиреневый кружок со стрелкой означает "Нет на месте"](media/Presence_OOF.png) <span data-ttu-id="f45eb-149">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="f45eb-149">Out of Office</span></span>|
|||

<span data-ttu-id="f45eb-150">Состояния присутствия, настроенные приложением, основываются на действиях пользователя (доступно, нет), состояниях календаря Outlook (на собрании) и о состояниях приложений Teams (во время звонка).</span><span class="sxs-lookup"><span data-stu-id="f45eb-150">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="f45eb-151">Обратите внимание, что при переходе в режим фокусировки, основанный на вашем календаре, фокусировка будет видна людям в Teams, но в других продуктах оно будет отображаться как "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="f45eb-151">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="f45eb-152">Текущее состояние присутствия будет изменено на "нет на месте", если вы блокируете компьютер, а затем переходите в режим сна или в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="f45eb-152">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="f45eb-153">На мобильном устройстве состояние присутствия меняется на "нет на месте", если приложение Teams находится в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="f45eb-153">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="f45eb-154">Пользователи получают все сообщения, отправленные им в чатах Teams, независимо от состояния их присутствия.</span><span class="sxs-lookup"><span data-stu-id="f45eb-154">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="f45eb-155">При отправке сообщения в чате пользователю, который находится не в сети, это сообщение чата появится в Teams, когда пользователь окажется в сети.</span><span class="sxs-lookup"><span data-stu-id="f45eb-155">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="f45eb-156">Если пользователь не находится в режиме "не беспокоить", он по-прежнему будет получать сообщения в чате, но уведомления на экране приветствия не отображаются.</span><span class="sxs-lookup"><span data-stu-id="f45eb-156">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="f45eb-157">Пользователи получают звонки во всех состояниях присутствия, кроме Do "не беспокоить", в котором входящие звонки проходят на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="f45eb-157">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="f45eb-158">Если получатель заблокировал звонящего , звонок не будет доставлен, а для звонящего присутствие вызываемого абонента отобразится как "Не в сети".</span><span class="sxs-lookup"><span data-stu-id="f45eb-158">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="f45eb-159">Пользователь может добавлять других пользователей в свой список приоритетного доступа, перейдя в **Параметры** > **Конфиденциальность** в Teams.</span><span class="sxs-lookup"><span data-stu-id="f45eb-159">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="f45eb-160">Пользователи, у которых есть приоритет доступа, могут связываться с пользователем, даже если пользователь находится в разделе "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="f45eb-160">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="f45eb-161">Параметры администрирования в Teams по сравнению с параметрами в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f45eb-161">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="f45eb-162">Параметры администрирования в Teams, которые отличаются от параметров в Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="f45eb-162">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="f45eb-163">В Teams возможность поделиться присутствием для пользователей организации всегда включена.</span><span class="sxs-lookup"><span data-stu-id="f45eb-163">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="f45eb-164">Настройка конфиденциальности (когда можно определять, кто может видеть присутствие) в Teams недоступна.</span><span class="sxs-lookup"><span data-stu-id="f45eb-164">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="f45eb-165">Для пользователей в Teams всегда включена возможность поделиться присутствием со всеми пользователями , в том числе федеративными службами.</span><span class="sxs-lookup"><span data-stu-id="f45eb-165">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="f45eb-166">Список контактов (если он был у пользователя в Skype для бизнеса) отображается в**Чат > Контакты** или в **Звонки> Контакты**.</span><span class="sxs-lookup"><span data-stu-id="f45eb-166">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="f45eb-167">Для пользователей в Teams функции клиента "Не беспокоить" и "Прорыв" всегда включены.</span><span class="sxs-lookup"><span data-stu-id="f45eb-167">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="f45eb-168">При интеграции Teams c Outlook интеграция календаря (включая данные об отсутствии на месте и другие данные календаря) для пользователей всегда включена.</span><span class="sxs-lookup"><span data-stu-id="f45eb-168">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="f45eb-169">Индикатор *Последний раз в сети* или*Отсутствую с* всегда включен для пользователей Teams, если в организации также используется Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f45eb-169">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="f45eb-170">Возможность настройки этих параметров администратором в Teams в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f45eb-170">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="f45eb-171">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f45eb-171">Coexistence with Skype for Business</span></span>

<span data-ttu-id="f45eb-172">Дополнительные сведения о том, как функционирует присутствие Teams, если в организации используется также Skype для бизнеса, см. в статье [Сосуществование со Skype для бизнеса](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="f45eb-172">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
