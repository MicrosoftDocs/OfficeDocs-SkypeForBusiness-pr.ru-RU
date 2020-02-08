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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863200"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="92844-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="92844-103">User presence in Teams</span></span>

<span data-ttu-id="92844-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в Office 365), указывающая на текущую доступность пользователя и его состояние другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="92844-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="92844-105">По умолчанию любой пользователь в вашей организации, использующий Teams, может видеть (в реальном времени), если другие пользователи доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="92844-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92844-106">Когда пользователь перемещается в режим **Только Teams** и затем удаляется клиент Skype для бизнеса, присутствие в Outlook и других приложениях Office перестает отображаться.</span><span class="sxs-lookup"><span data-stu-id="92844-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="92844-107">Присутствие в Teams отображается нормально.</span><span class="sxs-lookup"><span data-stu-id="92844-107">Presence works fine in Teams.</span></span> <span data-ttu-id="92844-108">Временное решение: для просмотра сведений о присутствии в Outlook (и других приложениях Office) необходимо установить Skype для бизнеса, даже если вы используете Teams в режиме " **только для Teams** ".</span><span class="sxs-lookup"><span data-stu-id="92844-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="92844-109">Мы знаем об этой проблеме и уже работаем над ее устранением.</span><span class="sxs-lookup"><span data-stu-id="92844-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="92844-110">Сведения о присутствии Teams в Outlook поддерживаются в классическом приложении Outlook 2013 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="92844-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="92844-111">Состояние присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="92844-111">Presence states in Teams</span></span>

<span data-ttu-id="92844-112">Состояние присутствия пользователя доступно в teams:</span><span class="sxs-lookup"><span data-stu-id="92844-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="92844-113">Настраиваемый пользователем</span><span class="sxs-lookup"><span data-stu-id="92844-113">User configured</span></span>|<span data-ttu-id="92844-114">Настроенное приложение</span><span class="sxs-lookup"><span data-stu-id="92844-114">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает доступность присутствия](media/Presence_Available.png) <span data-ttu-id="92844-116">Доступно</span><span class="sxs-lookup"><span data-stu-id="92844-116">Available</span></span>|![Сплошной зеленый флажок означает доступность присутствия](media/Presence_Available.png) <span data-ttu-id="92844-118">Доступно</span><span class="sxs-lookup"><span data-stu-id="92844-118">Available</span></span>|
|| ![Открытие зеленой галочки означает, что вы можете получить доступ к отсутствием](media/Presence_Available_OOF.png) <span data-ttu-id="92844-120">Доступно, нет на месте</span><span class="sxs-lookup"><span data-stu-id="92844-120">Available, Out of Office</span></span> |
|  ![Сплошной красный круг, обозначает "занято"](media/Presence_Busy.png) <span data-ttu-id="92844-122">Сильно</span><span class="sxs-lookup"><span data-stu-id="92844-122">Busy</span></span> |  ![Сплошной красный круг, обозначает "занято"](media/Presence_Busy.png) <span data-ttu-id="92844-124">Сильно</span><span class="sxs-lookup"><span data-stu-id="92844-124">Busy</span></span>  |
|| ![Сплошной красный круг, указывает на то, что звонок занят](media/Presence_Busy.png) <span data-ttu-id="92844-126">На звонке</span><span class="sxs-lookup"><span data-stu-id="92844-126">On a call</span></span>|
|| ![Сплошной красный круг, указывает на то, что собрание занято](media/Presence_Busy.png) <span data-ttu-id="92844-128">На собрании</span><span class="sxs-lookup"><span data-stu-id="92844-128">In a meeting</span></span> |
|| ![Открыть красный круг, обозначает "занято"](media/Presence_Busy_OOF.png) <span data-ttu-id="92844-130">На звонке, нет на месте</span><span class="sxs-lookup"><span data-stu-id="92844-130">On a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "не беспокоить"](media/Presence_DND.png) <span data-ttu-id="92844-132">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="92844-132">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией, обозначает представление](media/Presence_DND.png) <span data-ttu-id="92844-134">Указав</span><span class="sxs-lookup"><span data-stu-id="92844-134">Presenting</span></span>|
|| ![Красный кружок с белой линией указывает на фокусировку](media/Presence_DND.png) <span data-ttu-id="92844-136">Фокусировка</span><span class="sxs-lookup"><span data-stu-id="92844-136">Focusing</span></span>|
| ![Значок желтого синхронизирующего импульса, индикатор "нет на месте"](media/Presence_Away.png) <span data-ttu-id="92844-138">Уйти</span><span class="sxs-lookup"><span data-stu-id="92844-138">Away</span></span>| ![Значок желтого синхронизирующего импульса, индикатор "нет на месте"](media/Presence_Away.png) <span data-ttu-id="92844-140">Уйти</span><span class="sxs-lookup"><span data-stu-id="92844-140">Away</span></span>|
|| <span data-ttu-id="92844-141">![Значок желтого синхронизирующего импульса](media/Presence_Away.png) , указывает на *время* последнего просмотра</span><span class="sxs-lookup"><span data-stu-id="92844-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов, указывает на отсутствие, должен быть сзади](media/Presence_Away.png) <span data-ttu-id="92844-143">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="92844-143">Be right back</span></span>| |
|| ![Желтый значок синхронизирующих сигналов, указывает на отсутствие, не работает](media/Presence_Away.png)  <span data-ttu-id="92844-145">Не на работе</span><span class="sxs-lookup"><span data-stu-id="92844-145">Off Work</span></span>|
|| ![Серый круг с крестиком означает "не в сети"](media/Presence_Offline.png) <span data-ttu-id="92844-147">Доступ</span><span class="sxs-lookup"><span data-stu-id="92844-147">Offline</span></span> |
|| ![Открыть серый круг, обозначает состояние Unknown](media/Presence_Unknown.png) <span data-ttu-id="92844-149">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="92844-149">Status unknown</span></span>|
||![Открытие красного круга с диагональной линией означает, что она заблокирована](media/Presence_Blocked.png) <span data-ttu-id="92844-151">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="92844-151">Blocked</span></span> |
|| ![Сиреневый круг со стрелкой, указывает на "нет на месте"](media/Presence_OOF.png) <span data-ttu-id="92844-153">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="92844-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="92844-154">Пользователи могут вручную установить для своего текущего состояния присутствия некоторые параметры, и их состояние будет отражено для всех других пользователей.</span><span class="sxs-lookup"><span data-stu-id="92844-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="92844-155">Дополнительные сведения о присутствии пользователя также обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="92844-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="92844-156">Изменения основываются на действиях пользователя (доступные, недоступные), состояниях календаря Outlook (на собрании) и о состояниях приложений Teams (в вызове, презентации) и состояниях, в которых отступы находятся в списке.</span><span class="sxs-lookup"><span data-stu-id="92844-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="92844-157">Время ожидания бездействия в 15 минут, после которого текущее состояние присутствия сбрасывается на нет на месте.</span><span class="sxs-lookup"><span data-stu-id="92844-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="92844-158">Пользователи получают все сообщения чата, отправленные им в Teams, независимо от их состояния присутствия.</span><span class="sxs-lookup"><span data-stu-id="92844-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="92844-159">Если пользователь отправляет сообщение в автономном режиме, сообщение чата отображается в Teams в следующий раз, когда пользователь в сети.</span><span class="sxs-lookup"><span data-stu-id="92844-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="92844-160">Если пользователь находится в состоянии "не беспокоить", пользователь по-прежнему будет получать сообщения в чате, но уведомление о рекламе не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="92844-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="92844-161">Пользователи получают звонки во всех состояниях присутствия, кроме состояния "не беспокоить", в котором входящие звонки доставляются в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="92844-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="92844-162">Если получатель заблокировал вызывающего абонента, Звонок не будет доставлен, а вызывающий абонент увидит состояние "не в сети".</span><span class="sxs-lookup"><span data-stu-id="92844-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="92844-163">Пользователи могут добавлять людей в список приоритетов доступа, применяя **Параметры** > **конфиденциальности** в Teams.</span><span class="sxs-lookup"><span data-stu-id="92844-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="92844-164">Пользователи, у которых есть приоритет доступа, могут связываться с пользователем, даже если пользователь находится в состоянии "не беспокоить".</span><span class="sxs-lookup"><span data-stu-id="92844-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="92844-165">Параметры администрирования в Teams по сравнению с Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="92844-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="92844-166">Следующие параметры администратора в Skype для бизнеса отличаются в teams:</span><span class="sxs-lookup"><span data-stu-id="92844-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="92844-167">В Teams доступ к присутствии всегда включен для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="92844-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="92844-168">Конфиденциальность (определение пользователей, которые могут видеть состояние присутствия) недоступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="92844-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="92844-169">Предоставление общего предоставления сведений о присутствии для всех пользователей (в том числе федеративных служб) всегда разрешено пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="92844-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="92844-170">Список контактов в Skype для бизнеса отображается в разделе " **чат" > "Контакты** " или " **звонки > контакты**".</span><span class="sxs-lookup"><span data-stu-id="92844-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="92844-171">Клиент не переносятся, а функции, появляющиеся неактивными, всегда включаются для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="92844-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="92844-172">Календарь (в том числе сведения об отсутствии на рабочем месте и другие данные календаря) интеграция всегда включена для пользователей при интеграции Teams с Outlook.</span><span class="sxs-lookup"><span data-stu-id="92844-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="92844-173">Если в организации также используется Skype для бизнеса, индикатор " *Последнее обнаружение* " или "нет на *месте* " всегда включен для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="92844-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="92844-174">Возможность администраторам Teams настраивать эти параметры в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="92844-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="92844-175">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="92844-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="92844-176">Узнайте подробнее о том, как работает функция присутствия в вашей организации, если в вашей компании используется Skype для бизнеса ( [сосуществование в Skype для бизнеса](coexistence-chat-calls-presence.md) ).</span><span class="sxs-lookup"><span data-stu-id="92844-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
