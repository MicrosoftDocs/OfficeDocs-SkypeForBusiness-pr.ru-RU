---
title: Присутствие пользователей в Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Сведения для администраторов о присутствии в Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863200"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="75328-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="75328-103">User presence in Teams</span></span>

<span data-ttu-id="75328-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и Office 365), которая показывает другим пользователям текущую доступность и состояние пользователя.</span><span class="sxs-lookup"><span data-stu-id="75328-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="75328-105">По умолчанию все пользователи в организации, в которой используется Teams, могут (практически в режиме реального времени) видеть, находятся ли в сети другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="75328-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75328-106">Когда пользователь перемещается в режим **Только Teams** и затем удаляется клиент Skype для бизнеса, присутствие в Outlook и других приложениях Office перестает отображаться.</span><span class="sxs-lookup"><span data-stu-id="75328-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="75328-107">Присутствие в Teams отображается нормально.</span><span class="sxs-lookup"><span data-stu-id="75328-107">Presence works fine in Teams.</span></span> <span data-ttu-id="75328-108">Временное решение. Для отображения присутствия в Outlook (и других приложениях Office) нужно установить Skype для бизнеса, даже если вы используете Teams в режиме**Только Teams**.</span><span class="sxs-lookup"><span data-stu-id="75328-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="75328-109">Мы знаем об этой проблеме и уже работаем над ее устранением.</span><span class="sxs-lookup"><span data-stu-id="75328-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="75328-110">Сведения о присутствии Teams в Outlook поддерживаются в классическом приложении Outlook 2013 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="75328-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="75328-111">Состояния присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="75328-111">Presence states in Teams</span></span>

<span data-ttu-id="75328-112">Доступные состояния присутствия пользователей в Teams:</span><span class="sxs-lookup"><span data-stu-id="75328-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="75328-113">Настроено пользователем</span><span class="sxs-lookup"><span data-stu-id="75328-113">User configured</span></span>|<span data-ttu-id="75328-114">Настроено в приложении</span><span class="sxs-lookup"><span data-stu-id="75328-114">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="75328-116">В сети</span><span class="sxs-lookup"><span data-stu-id="75328-116">Available</span></span>|![Сплошной зеленый флажок означает "В сети"](media/Presence_Available.png) <span data-ttu-id="75328-118">В сети</span><span class="sxs-lookup"><span data-stu-id="75328-118">Available</span></span>|
|| ![Открытый зеленый флажок означает "В сети, нет на месте"](media/Presence_Available_OOF.png) <span data-ttu-id="75328-120">В сети, нет на месте</span><span class="sxs-lookup"><span data-stu-id="75328-120">Available, Out of Office</span></span> |
|  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="75328-122">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="75328-122">Busy</span></span> |  ![Сплошной красный кружок означает "Занят(а)"](media/Presence_Busy.png) <span data-ttu-id="75328-124">Занят(а)</span><span class="sxs-lookup"><span data-stu-id="75328-124">Busy</span></span>  |
|| ![Сплошной красный кружок означает "Занят(а), говорю по телефону"](media/Presence_Busy.png) <span data-ttu-id="75328-126">Говорю по телефону</span><span class="sxs-lookup"><span data-stu-id="75328-126">On a call</span></span>|
|| ![Сплошной красный кружок означает "Занят(а), на собрании"](media/Presence_Busy.png) <span data-ttu-id="75328-128">На собрании</span><span class="sxs-lookup"><span data-stu-id="75328-128">In a meeting</span></span> |
|| ![Открытый красный кружок означает "Занят(а)"](media/Presence_Busy_OOF.png) <span data-ttu-id="75328-130">Говорю по телефону, нет на месте</span><span class="sxs-lookup"><span data-stu-id="75328-130">On a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "Не беспокоить"](media/Presence_DND.png) <span data-ttu-id="75328-132">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="75328-132">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией означает "Показ презентации"](media/Presence_DND.png) <span data-ttu-id="75328-134">Показ презентации</span><span class="sxs-lookup"><span data-stu-id="75328-134">Presenting</span></span>|
|| ![Красный кружок с белой линией означает "Концентрация"](media/Presence_DND.png) <span data-ttu-id="75328-136">Концентрация</span><span class="sxs-lookup"><span data-stu-id="75328-136">Focusing</span></span>|
| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="75328-138">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="75328-138">Away</span></span>| ![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) <span data-ttu-id="75328-140">Отсутствую</span><span class="sxs-lookup"><span data-stu-id="75328-140">Away</span></span>|
|| <span data-ttu-id="75328-141">![Желтый значок часов означает "Отсутствую"](media/Presence_Away.png) Последний раз в сети в *время*</span><span class="sxs-lookup"><span data-stu-id="75328-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов означает "Отсутствую, скоро вернусь"](media/Presence_Away.png) <span data-ttu-id="75328-143">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="75328-143">Be right back</span></span>| |
|| ![Желтый значок часов означает "Отсутствую, не на работе"](media/Presence_Away.png)  <span data-ttu-id="75328-145">Не на работе</span><span class="sxs-lookup"><span data-stu-id="75328-145">Off Work</span></span>|
|| ![Серый кружок со знаком "Х" означает "Автономный режим"](media/Presence_Offline.png) <span data-ttu-id="75328-147">Автономный режим</span><span class="sxs-lookup"><span data-stu-id="75328-147">Offline</span></span> |
|| ![Открытый серый кружок означает "Состояние неизвестно"](media/Presence_Unknown.png) <span data-ttu-id="75328-149">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="75328-149">Status unknown</span></span>|
||![Открытый красный кружок с линией по диагонали означает "Заблокировано"](media/Presence_Blocked.png) <span data-ttu-id="75328-151">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="75328-151">Blocked</span></span> |
|| ![Сиреневый кружок со стрелкой означает "Нет на месте"](media/Presence_OOF.png) <span data-ttu-id="75328-153">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="75328-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="75328-154">Пользователи могут вручную устанавливать текущее состояние присутствия, выбирая из нескольких вариантов, и их состояние отображается для всех остальных пользователей.</span><span class="sxs-lookup"><span data-stu-id="75328-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="75328-155">Обновление дополнительных сведений о присутствии пользователей также происходит автоматически.</span><span class="sxs-lookup"><span data-stu-id="75328-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="75328-156">Изменения основываются на активности пользователя ("В сети","Отсутствую"), состояния календаря Outlook или состояния приложений Teams ("Говорю по телефону","Показ презентации") на состояния, которые указаны в списке с отступами.</span><span class="sxs-lookup"><span data-stu-id="75328-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="75328-157">Предусмотрено 15-минутное время ожидания, по истечении которого текущее состояние присутствия сбрасывается на "Отсутствую".</span><span class="sxs-lookup"><span data-stu-id="75328-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="75328-158">Пользователи получают все сообщения, отправленные им в чатах Teams, независимо от состояния их присутствия.</span><span class="sxs-lookup"><span data-stu-id="75328-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="75328-159">При отправке сообщения в чате пользователю, который находится не в сети, это сообщение чата появится в Teams, когда пользователь окажется в сети.</span><span class="sxs-lookup"><span data-stu-id="75328-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="75328-160">Если пользователь находится в состоянии "Не беспокоить", пользователь сможет получить сообщения в чате, но всплывающее уведомление отображаться не будет.</span><span class="sxs-lookup"><span data-stu-id="75328-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="75328-161">Звонки поступают пользователям при любом состоянии присутствия, за исключением состояния "Не беспокоить", при котором входящие звонки поступают на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="75328-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="75328-162">Если получатель заблокировал звонящего , звонок не будет доставлен, а для звонящего присутствие вызываемого абонента отобразится как "Не в сети".</span><span class="sxs-lookup"><span data-stu-id="75328-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="75328-163">Пользователь может добавлять других пользователей в свой список приоритетного доступа, перейдя в **Параметры** > **Конфиденциальность** в Teams.</span><span class="sxs-lookup"><span data-stu-id="75328-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="75328-164">Пользователи, имеющие приоритетный доступ, могут связываться с пользователем даже в состоянии "Не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="75328-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="75328-165">Параметры администрирования в Teams по сравнению с параметрами в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="75328-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="75328-166">Параметры администрирования в Teams, которые отличаются от параметров в Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="75328-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="75328-167">В Teams возможность поделиться присутствием для пользователей организации всегда включена.</span><span class="sxs-lookup"><span data-stu-id="75328-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="75328-168">Настройка конфиденциальности (когда можно определять, кто может видеть присутствие) в Teams недоступна.</span><span class="sxs-lookup"><span data-stu-id="75328-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="75328-169">Для пользователей в Teams всегда включена возможность поделиться присутствием со всеми пользователями , в том числе федеративными службами.</span><span class="sxs-lookup"><span data-stu-id="75328-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="75328-170">Список контактов (если он был у пользователя в Skype для бизнеса) отображается в**Чат > Контакты** или в **Звонки> Контакты**.</span><span class="sxs-lookup"><span data-stu-id="75328-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="75328-171">Для пользователей в Teams функции клиента "Не беспокоить" и "Прорыв" всегда включены.</span><span class="sxs-lookup"><span data-stu-id="75328-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="75328-172">При интеграции Teams c Outlook интеграция календаря (включая данные об отсутствии на месте и другие данные календаря) для пользователей всегда включена.</span><span class="sxs-lookup"><span data-stu-id="75328-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="75328-173">Индикатор *Последний раз в сети* или*Отсутствую с* всегда включен для пользователей Teams, если в организации также используется Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="75328-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="75328-174">Возможность настройки этих параметров администратором в Teams в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="75328-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="75328-175">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="75328-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="75328-176">Дополнительные сведения о том, как функционирует присутствие Teams, если в организации используется также Skype для бизнеса, см. в статье [Сосуществование со Skype для бизнеса](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="75328-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
