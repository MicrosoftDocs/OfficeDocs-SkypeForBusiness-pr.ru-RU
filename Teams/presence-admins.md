---
title: Присутствие пользователей в Teams
author: msdmaguire
ms.author: dmaguire
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
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369214"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="b6875-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="b6875-103">User presence in Teams</span></span>

<span data-ttu-id="b6875-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в Microsoft 365 или Office 365), указывающая на текущую доступность пользователя и его состояние другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="b6875-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="b6875-105">По умолчанию все пользователи в организации, в которой используется Teams, могут (практически в режиме реального времени) видеть, находятся ли в сети другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="b6875-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="b6875-106">Сведения о присутствии Teams в Outlook поддерживаются в классическом приложении Outlook 2013 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="b6875-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="b6875-107">Подробные сведения о профилях пользователей Teams на разных платформах можно найти в разделе [функции групп на платформе](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="b6875-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="b6875-108">Состояния присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="b6875-108">Presence states in Teams</span></span>

|<span data-ttu-id="b6875-109">Настроено пользователем</span><span class="sxs-lookup"><span data-stu-id="b6875-109">User configured</span></span>|<span data-ttu-id="b6875-110">Настроено в приложении</span><span class="sxs-lookup"><span data-stu-id="b6875-110">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="b6875-112">В сети</span><span class="sxs-lookup"><span data-stu-id="b6875-112">Available</span></span>|![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="b6875-114">В сети</span><span class="sxs-lookup"><span data-stu-id="b6875-114">Available</span></span>|
|| ![Открытый зеленый флажок означает "В сети, нет на месте"](media/Presence_Available_OOF.png) <span data-ttu-id="b6875-116">В сети, нет на месте</span><span class="sxs-lookup"><span data-stu-id="b6875-116">Available, Out of Office</span></span> |
|  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="b6875-118">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="b6875-118">Busy</span></span> |  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="b6875-120">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="b6875-120">Busy</span></span>  |
|| ![Сплошной красный кружок означает "Занят(а), говорю по телефону"](media/Presence_Busy.png) <span data-ttu-id="b6875-122">Говорю по телефону</span><span class="sxs-lookup"><span data-stu-id="b6875-122">On a call</span></span>|
|| ![Сплошной красный кружок означает "Занят(а), на собрании"](media/Presence_Busy.png) <span data-ttu-id="b6875-124">На собрании</span><span class="sxs-lookup"><span data-stu-id="b6875-124">In a meeting</span></span> |
|| ![Открытый красный кружок означает "Занят(а)"](media/Presence_Busy_OOF.png) <span data-ttu-id="b6875-126">Говорю по телефону, нет на месте</span><span class="sxs-lookup"><span data-stu-id="b6875-126">On a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "Не беспокоить"](media/Presence_DND.png) <span data-ttu-id="b6875-128">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="b6875-128">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией означает "Показ презентации"](media/Presence_DND.png) <span data-ttu-id="b6875-130">Показ презентации</span><span class="sxs-lookup"><span data-stu-id="b6875-130">Presenting</span></span>|
|| ![Красный кружок с белой линией означает "Концентрация"](media/Presence_DND.png) <span data-ttu-id="b6875-132">Концентрация</span><span class="sxs-lookup"><span data-stu-id="b6875-132">Focusing</span></span>|
| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="b6875-134">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="b6875-134">Away</span></span>| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="b6875-136">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="b6875-136">Away</span></span>|
|| <span data-ttu-id="b6875-137">![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) Последний раз в сети в *время*</span><span class="sxs-lookup"><span data-stu-id="b6875-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов означает "Отсутствую, скоро вернусь"](media/Presence_Away.png) <span data-ttu-id="b6875-139">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="b6875-139">Be right back</span></span>| |
|![Серый кружок со знаком "Х" означает "Автономный режим"](media/Presence_Offline.png) <span data-ttu-id="b6875-141">Отображается в автономном режиме</span><span class="sxs-lookup"><span data-stu-id="b6875-141">Appear offline</span></span> | ![Серый кружок со знаком "Х" означает "Автономный режим"](media/Presence_Offline.png) <span data-ttu-id="b6875-143">Автономный режим</span><span class="sxs-lookup"><span data-stu-id="b6875-143">Offline</span></span>| |
|| ![Открытый серый кружок означает "Состояние неизвестно"](media/Presence_Unknown.png) <span data-ttu-id="b6875-145">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="b6875-145">Status unknown</span></span>|
|| ![Сиреневый кружок со стрелкой означает "Нет на месте"](media/Presence_OOF.png) <span data-ttu-id="b6875-147">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="b6875-147">Out of Office</span></span>|
|||

<span data-ttu-id="b6875-148">Состояния присутствия, настроенные приложением, основываются на действиях пользователя (доступно, нет), состояниях календаря Outlook (на собрании) и о состояниях приложений Teams (во время звонка).</span><span class="sxs-lookup"><span data-stu-id="b6875-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="b6875-149">Обратите внимание, что при переходе в режим фокусировки, основанный на вашем календаре, фокусировка будет видна людям в Teams, но в других продуктах оно будет отображаться как "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="b6875-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="b6875-150">Текущее состояние присутствия будет изменено на "нет на месте", если вы блокируете компьютер или переходите в режим бездействия или в режиме сна.</span><span class="sxs-lookup"><span data-stu-id="b6875-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="b6875-151">На мобильном устройстве состояние присутствия меняется на "нет на месте", если приложение Teams находится в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="b6875-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="b6875-152">Пользователи получают все сообщения, отправленные им в чатах Teams, независимо от состояния их присутствия.</span><span class="sxs-lookup"><span data-stu-id="b6875-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="b6875-153">При отправке сообщения в чате пользователю, который находится не в сети, это сообщение чата появится в Teams, когда пользователь окажется в сети.</span><span class="sxs-lookup"><span data-stu-id="b6875-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="b6875-154">Если для пользователя установлено состояние "не беспокоить", пользователь по-прежнему будет получать сообщения в чате, но уведомления о баннерах не отображаются.</span><span class="sxs-lookup"><span data-stu-id="b6875-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="b6875-155">Пользователи получают звонки во всех состояниях присутствия, кроме Do "не беспокоить", в котором входящие звонки проходят на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="b6875-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="b6875-156">Если получатель заблокировал звонящего , звонок не будет доставлен, а для звонящего присутствие вызываемого абонента отобразится как "Не в сети".</span><span class="sxs-lookup"><span data-stu-id="b6875-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="b6875-157">Пользователь может добавлять других пользователей в свой список приоритетного доступа, перейдя в **Параметры** > **Конфиденциальность** в Teams.</span><span class="sxs-lookup"><span data-stu-id="b6875-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="b6875-158">Пользователи, у которых есть приоритет доступа, смогут связаться с пользователем, даже если у него установлено состояние "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="b6875-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="b6875-159">Срок действия состояния, настроенного пользователем</span><span class="sxs-lookup"><span data-stu-id="b6875-159">User configured states expiration</span></span>
<span data-ttu-id="b6875-160">Когда пользователь выбирает конкретное состояние присутствия, оно имеет приоритет перед обновлением действия в приложении.</span><span class="sxs-lookup"><span data-stu-id="b6875-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="b6875-161">Например, если пользователь задает себе состояние "не беспокоить", его присутствие останется в состоянии "не беспокоить", даже если она пойдет на собрание или ответит на звонок.</span><span class="sxs-lookup"><span data-stu-id="b6875-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="b6875-162">Состояния, настроенные пользователем, имеют параметры срока действия по умолчанию в Teams, чтобы пользователи не могли отобразить состояние, которое может быть недоступно по истечении определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="b6875-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="b6875-163">Состояние, настроенное пользователем</span><span class="sxs-lookup"><span data-stu-id="b6875-163">User configured state</span></span>|<span data-ttu-id="b6875-164">Срок действия по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b6875-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="b6875-165">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="b6875-165">Busy</span></span>|<span data-ttu-id="b6875-166">1 день</span><span class="sxs-lookup"><span data-stu-id="b6875-166">1 day</span></span>|
| <span data-ttu-id="b6875-167">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="b6875-167">Do not disturb</span></span>|<span data-ttu-id="b6875-168">1 день</span><span class="sxs-lookup"><span data-stu-id="b6875-168">1 day</span></span>|
| <span data-ttu-id="b6875-169">Нему</span><span class="sxs-lookup"><span data-stu-id="b6875-169">Others</span></span>|<span data-ttu-id="b6875-170">7 дней</span><span class="sxs-lookup"><span data-stu-id="b6875-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="b6875-171">Параметры администрирования в Teams по сравнению с параметрами в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b6875-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="b6875-172">Параметры администрирования в Teams, которые отличаются от параметров в Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="b6875-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="b6875-173">В Teams возможность поделиться присутствием для пользователей организации всегда включена.</span><span class="sxs-lookup"><span data-stu-id="b6875-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="b6875-174">Настройка конфиденциальности (когда можно определять, кто может видеть присутствие) в Teams недоступна.</span><span class="sxs-lookup"><span data-stu-id="b6875-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="b6875-175">Для пользователей в Teams всегда включена возможность поделиться присутствием со всеми пользователями , в том числе федеративными службами.</span><span class="sxs-lookup"><span data-stu-id="b6875-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="b6875-176">Список контактов (если он был у пользователя в Skype для бизнеса) отображается в**Чат > Контакты** или в **Звонки> Контакты**.</span><span class="sxs-lookup"><span data-stu-id="b6875-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="b6875-177">Для пользователей в Teams функции клиента "Не беспокоить" и "Прорыв" всегда включены.</span><span class="sxs-lookup"><span data-stu-id="b6875-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="b6875-178">При интеграции Teams c Outlook интеграция календаря (включая данные об отсутствии на месте и другие данные календаря) для пользователей всегда включена.</span><span class="sxs-lookup"><span data-stu-id="b6875-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="b6875-179">Индикатор *Последний раз в сети* или*Отсутствую с* всегда включен для пользователей Teams, если в организации также используется Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b6875-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="b6875-180">Возможность настройки этих параметров администратором в Teams в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b6875-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="b6875-181">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b6875-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="b6875-182">Дополнительные сведения о том, как функционирует присутствие Teams, если в организации используется также Skype для бизнеса, см. в статье [Сосуществование со Skype для бизнеса](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="b6875-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
