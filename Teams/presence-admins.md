---
title: Присутствие пользователей в Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Сведения для администраторов о присутствии в Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b829fbffa728d3449ba19466d0a2cb85f266c9c2
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010602"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="cd189-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="cd189-103">User presence in Teams</span></span>

<span data-ttu-id="cd189-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в Office 365), указывающая на текущую доступность пользователя и его состояние другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="cd189-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="cd189-105">По умолчанию любой пользователь в вашей организации, использующий Teams, может видеть (в реальном времени), если другие пользователи доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="cd189-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd189-106">Когда пользователь перемещается в режим **Только Teams** и затем удаляется клиент Skype для бизнеса, присутствие в Outlook и других приложениях Office перестает отображаться.</span><span class="sxs-lookup"><span data-stu-id="cd189-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="cd189-107">Присутствие в Teams отображается нормально.</span><span class="sxs-lookup"><span data-stu-id="cd189-107">Presence works fine in Teams.</span></span> <span data-ttu-id="cd189-108">Временное решение: для просмотра сведений о присутствии в Outlook (и других приложениях Office) необходимо установить Skype для бизнеса, даже если вы используете Teams в режиме " **только для Teams** ".</span><span class="sxs-lookup"><span data-stu-id="cd189-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="cd189-109">Мы знаем об этой проблеме и уже работаем над ее устранением.</span><span class="sxs-lookup"><span data-stu-id="cd189-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="cd189-110">Присутствие Teams в Outlook поддерживается в классическом приложении Outlook 2013 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="cd189-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="cd189-111">Состояние присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="cd189-111">Presence states in Teams</span></span>

<span data-ttu-id="cd189-112">Состояние присутствия пользователя доступно в teams:</span><span class="sxs-lookup"><span data-stu-id="cd189-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="cd189-113">Настраиваемый пользователем</span><span class="sxs-lookup"><span data-stu-id="cd189-113">User configured</span></span>|<span data-ttu-id="cd189-114">Настроенное приложение</span><span class="sxs-lookup"><span data-stu-id="cd189-114">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает доступность присутствия](media/Presence_Available.png) <span data-ttu-id="cd189-116">Доступно</span><span class="sxs-lookup"><span data-stu-id="cd189-116">Available</span></span>|![Сплошной зеленый флажок означает доступность присутствия](media/Presence_Available.png) <span data-ttu-id="cd189-118">Доступно</span><span class="sxs-lookup"><span data-stu-id="cd189-118">Available</span></span>|
|| ![Открытие зеленой галочки означает, что вы можете получить доступ к отсутствием](media/Presence_Available_OOF.png) <span data-ttu-id="cd189-120">Доступно, нет на месте</span><span class="sxs-lookup"><span data-stu-id="cd189-120">Available, Out of Office</span></span> |
|  ![Сплошной красный круг, обозначает "занято"](media/Presence_Busy.png) <span data-ttu-id="cd189-122">Сильно</span><span class="sxs-lookup"><span data-stu-id="cd189-122">Busy</span></span> |  ![Сплошной красный круг, обозначает "занято"](media/Presence_Busy.png) <span data-ttu-id="cd189-124">Сильно</span><span class="sxs-lookup"><span data-stu-id="cd189-124">Busy</span></span>  |
|| ![Сплошной красный круг, указывает на то, что звонок занят](media/Presence_Busy.png) <span data-ttu-id="cd189-126">В звонке</span><span class="sxs-lookup"><span data-stu-id="cd189-126">In a call</span></span>|
|| ![Сплошной красный круг, указывает на то, что собрание занято](media/Presence_Busy.png) <span data-ttu-id="cd189-128">На собрании</span><span class="sxs-lookup"><span data-stu-id="cd189-128">In a meeting</span></span> |
|| ![Открыть красный круг, обозначает "занято"](media/Presence_Busy_OOF.png) <span data-ttu-id="cd189-130">В звонке, нет на месте</span><span class="sxs-lookup"><span data-stu-id="cd189-130">In a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "не беспокоить"](media/Presence_DND.png) <span data-ttu-id="cd189-132">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="cd189-132">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией, обозначает представление](media/Presence_DND.png) <span data-ttu-id="cd189-134">Указав</span><span class="sxs-lookup"><span data-stu-id="cd189-134">Presenting</span></span>|
|| ![Красный кружок с белой линией указывает на фокусировку](media/Presence_DND.png) <span data-ttu-id="cd189-136">Фокусировка</span><span class="sxs-lookup"><span data-stu-id="cd189-136">Focusing</span></span>|
| ![Значок желтого синхронизирующего импульса, индикатор "нет на месте"](media/Presence_Away.png) <span data-ttu-id="cd189-138">Уйти</span><span class="sxs-lookup"><span data-stu-id="cd189-138">Away</span></span>| ![Значок желтого синхронизирующего импульса, индикатор "нет на месте"](media/Presence_Away.png) <span data-ttu-id="cd189-140">Уйти</span><span class="sxs-lookup"><span data-stu-id="cd189-140">Away</span></span>|
|| <span data-ttu-id="cd189-141">![Значок желтого синхронизирующего импульса](media/Presence_Away.png) , указывает на *время* последнего просмотра</span><span class="sxs-lookup"><span data-stu-id="cd189-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов, указывает на отсутствие, должен быть сзади](media/Presence_Away.png) <span data-ttu-id="cd189-143">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="cd189-143">Be right back</span></span>| |
|| ![Желтый значок синхронизирующих сигналов, указывает на отсутствие, не работает](media/Presence_Away.png)  <span data-ttu-id="cd189-145">Не на работе</span><span class="sxs-lookup"><span data-stu-id="cd189-145">Off Work</span></span>|
|| ![Серый круг с крестиком означает "не в сети"](media/Presence_Offline.png) <span data-ttu-id="cd189-147">Доступ</span><span class="sxs-lookup"><span data-stu-id="cd189-147">Offline</span></span> |
|| ![Открыть серый круг, обозначает состояние Unknown](media/Presence_Unknown.png) <span data-ttu-id="cd189-149">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="cd189-149">Status unknown</span></span>|
||![Открытие красного круга с диагональной линией означает, что она заблокирована](media/Presence_Blocked.png) <span data-ttu-id="cd189-151">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="cd189-151">Blocked</span></span> |
|| ![Сиреневый круг со стрелкой, указывает на "нет на месте"](media/Presence_OOF.png) <span data-ttu-id="cd189-153">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="cd189-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="cd189-154">Пользователи могут вручную установить для своего текущего состояния присутствия некоторые параметры, и их состояние будет отражено для всех других пользователей.</span><span class="sxs-lookup"><span data-stu-id="cd189-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="cd189-155">Дополнительные сведения о присутствии пользователя также обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="cd189-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="cd189-156">Изменения основываются на действиях пользователя (доступные, недоступные), состояниях календаря Outlook (на собрании) и о состояниях приложений Teams (в вызове, презентации) и состояниях, в которых отступы находятся в списке.</span><span class="sxs-lookup"><span data-stu-id="cd189-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> 

<span data-ttu-id="cd189-157">Время ожидания бездействия в 15 минут, после которого текущее состояние присутствия сбрасывается на нет на месте.</span><span class="sxs-lookup"><span data-stu-id="cd189-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="cd189-158">Пользователи могут указать, кто может переключиться (то есть общаться с ними несмотря на состояние "не беспокоить").</span><span class="sxs-lookup"><span data-stu-id="cd189-158">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="cd189-159">Эти параметры доступны в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="cd189-159">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="cd189-160">Параметры администрирования в Teams по сравнению с Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cd189-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="cd189-161">Следующие параметры администратора в Skype для бизнеса отличаются в teams:</span><span class="sxs-lookup"><span data-stu-id="cd189-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="cd189-162">В Teams доступ к присутствии всегда включен для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="cd189-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="cd189-163">Конфиденциальность (определение пользователей, которые могут видеть состояние присутствия) недоступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="cd189-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="cd189-164">Предоставление общего предоставления сведений о присутствии для всех пользователей (в том числе федеративных служб) всегда разрешено пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="cd189-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="cd189-165">Список контактов в Skype для бизнеса отображается в разделе " **чат" > "Контакты** " или " **звонки > контакты**".</span><span class="sxs-lookup"><span data-stu-id="cd189-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="cd189-166">Клиент не переносятся, а функции, появляющиеся неактивными, всегда включаются для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="cd189-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="cd189-167">Календарь (в том числе сведения об отсутствии на рабочем месте и другие данные календаря) интеграция всегда включена для пользователей при интеграции Teams с Outlook.</span><span class="sxs-lookup"><span data-stu-id="cd189-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="cd189-168">Если в организации также используется Skype для бизнеса, индикатор " *Последнее обнаружение* " или "нет на *месте* " всегда включен для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="cd189-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="cd189-169">Возможность администраторам Teams настраивать эти параметры в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cd189-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="cd189-170">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cd189-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="cd189-171">Узнайте подробнее о том, как работает функция присутствия в вашей организации, если в вашей компании используется Skype для бизнеса ( [сосуществование в Skype для бизнеса](coexistence-chat-calls-presence.md) ).</span><span class="sxs-lookup"><span data-stu-id="cd189-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
