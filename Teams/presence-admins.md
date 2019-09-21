---
title: Присутствие пользователей в Teams
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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd57165cbb88df135827ae72fa3952dd8ddd452
ms.sourcegitcommit: 299f854bbb73887ba315b09b9adf9ea9ff91e8ec
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37062965"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="d9265-103">Присутствие пользователей в Teams</span><span class="sxs-lookup"><span data-stu-id="d9265-103">User presence in Teams</span></span>

<span data-ttu-id="d9265-104">Присутствие — это часть профиля пользователя в Microsoft Teams (и в Office 365), указывающая на текущую доступность пользователя и его состояние другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="d9265-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="d9265-105">По умолчанию любой пользователь в вашей организации, использующий Teams, может видеть (в реальном времени), если другие пользователи доступны через Интернет.</span><span class="sxs-lookup"><span data-stu-id="d9265-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9265-106">Если вы удалите клиент Skype для бизнеса после того, как вы перемещаете пользователя в режим " **только для Teams** ", присутствие перестает работать в Outlook и других приложениях Office.</span><span class="sxs-lookup"><span data-stu-id="d9265-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="d9265-107">В Teams присутствие в состоянии прекрасно работает.</span><span class="sxs-lookup"><span data-stu-id="d9265-107">Presence works fine in Teams.</span></span> <span data-ttu-id="d9265-108">Временное решение: для просмотра сведений о присутствии в Outlook (и других приложениях Office) необходимо установить Skype для бизнеса, даже если вы используете Teams в режиме " **только для Teams** ".</span><span class="sxs-lookup"><span data-stu-id="d9265-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="d9265-109">Корпорация Майкрософт осведомлена об этой проблеме и работает над ее устранением.</span><span class="sxs-lookup"><span data-stu-id="d9265-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="d9265-110">Состояние присутствия в Teams</span><span class="sxs-lookup"><span data-stu-id="d9265-110">Presence states in Teams</span></span>

<span data-ttu-id="d9265-111">Состояние присутствия пользователя доступно в teams:</span><span class="sxs-lookup"><span data-stu-id="d9265-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="d9265-112">Настраиваемый пользователем</span><span class="sxs-lookup"><span data-stu-id="d9265-112">User configured</span></span>|<span data-ttu-id="d9265-113">Настроенное приложение</span><span class="sxs-lookup"><span data-stu-id="d9265-113">App configured</span></span>|
|:--- |:---|
| ![Сплошной зеленый флажок означает доступность присутствия](media/Presence_Available.png) <span data-ttu-id="d9265-115">Доступно</span><span class="sxs-lookup"><span data-stu-id="d9265-115">Available</span></span>|![Сплошной зеленый флажок означает доступность присутствия](media/Presence_Available.png) <span data-ttu-id="d9265-117">Доступно</span><span class="sxs-lookup"><span data-stu-id="d9265-117">Available</span></span>|
|| ![Открытие зеленой галочки означает, что вы можете получить доступ к отсутствием](media/Presence_Available_OOF.png) <span data-ttu-id="d9265-119">Доступно, нет на месте</span><span class="sxs-lookup"><span data-stu-id="d9265-119">Available, Out of Office</span></span> |
|  ![Сплошной красный круг, обозначает "занято"](media/Presence_Busy.png) <span data-ttu-id="d9265-121">Сильно</span><span class="sxs-lookup"><span data-stu-id="d9265-121">Busy</span></span> |  ![Сплошной красный круг, обозначает "занято"](media/Presence_Busy.png) <span data-ttu-id="d9265-123">Сильно</span><span class="sxs-lookup"><span data-stu-id="d9265-123">Busy</span></span>  |
|| ![Сплошной красный круг, указывает на то, что звонок занят](media/Presence_Busy.png) <span data-ttu-id="d9265-125">В звонке</span><span class="sxs-lookup"><span data-stu-id="d9265-125">In a call</span></span>|
|| ![Сплошной красный круг, указывает на то, что собрание занято](media/Presence_Busy.png) <span data-ttu-id="d9265-127">На собрании</span><span class="sxs-lookup"><span data-stu-id="d9265-127">In a meeting</span></span> |
|| ![Открыть красный круг, обозначает "занято"](media/Presence_Busy_OOF.png) <span data-ttu-id="d9265-129">В звонке, нет на месте</span><span class="sxs-lookup"><span data-stu-id="d9265-129">In a call, out of office</span></span>|
|  ![Красный кружок с белой линией означает "не беспокоить"](media/Presence_DND.png) <span data-ttu-id="d9265-131">Не беспокоить</span><span class="sxs-lookup"><span data-stu-id="d9265-131">Do not disturb</span></span> ||
|| ![Красный кружок с белой линией, обозначает представление](media/Presence_DND.png) <span data-ttu-id="d9265-133">Указав</span><span class="sxs-lookup"><span data-stu-id="d9265-133">Presenting</span></span>|
|| ![Красный кружок с белой линией указывает на фокусировку](media/Presence_DND.png) <span data-ttu-id="d9265-135">Фокусировка</span><span class="sxs-lookup"><span data-stu-id="d9265-135">Focusing</span></span>|
| ![Значок желтого синхронизирующего импульса, индикатор "нет на месте"](media/Presence_Away.png) <span data-ttu-id="d9265-137">Уйти</span><span class="sxs-lookup"><span data-stu-id="d9265-137">Away</span></span>| ![Значок желтого синхронизирующего импульса, индикатор "нет на месте"](media/Presence_Away.png) <span data-ttu-id="d9265-139">Уйти</span><span class="sxs-lookup"><span data-stu-id="d9265-139">Away</span></span>|
|| <span data-ttu-id="d9265-140">![Значок желтого синхронизирующего импульса](media/Presence_Away.png) , указывает на *время* последнего просмотра</span><span class="sxs-lookup"><span data-stu-id="d9265-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Желтый значок часов, указывает на отсутствие, должен быть сзади](media/Presence_Away.png) <span data-ttu-id="d9265-142">Скоро вернусь</span><span class="sxs-lookup"><span data-stu-id="d9265-142">Be right back</span></span>| |
|| ![Желтый значок синхронизирующих сигналов, указывает на отсутствие, не работает](media/Presence_Away.png)  <span data-ttu-id="d9265-144">Не на работе</span><span class="sxs-lookup"><span data-stu-id="d9265-144">Off Work</span></span>|
|| ![Серый круг с крестиком означает "не в сети"](media/Presence_Offline.png) <span data-ttu-id="d9265-146">Доступ</span><span class="sxs-lookup"><span data-stu-id="d9265-146">Offline</span></span> |
|| ![Открыть серый круг, обозначает состояние Unknown](media/Presence_Unknown.png) <span data-ttu-id="d9265-148">Состояние неизвестно</span><span class="sxs-lookup"><span data-stu-id="d9265-148">Status unknown</span></span>|
||![Открытие красного круга с диагональной линией означает, что она заблокирована](media/Presence_Blocked.png) <span data-ttu-id="d9265-150">Заблокировано</span><span class="sxs-lookup"><span data-stu-id="d9265-150">Blocked</span></span> |
|| ![Сиреневый круг со стрелкой, указывает на "нет на месте"](media/Presence_OOF.png) <span data-ttu-id="d9265-152">Нет на месте</span><span class="sxs-lookup"><span data-stu-id="d9265-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="d9265-153">Пользователи могут вручную установить для своего текущего состояния присутствия некоторые параметры, и их состояние будет отражено для всех других пользователей.</span><span class="sxs-lookup"><span data-stu-id="d9265-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="d9265-154">Дополнительные сведения о присутствии пользователя также обновляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="d9265-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="d9265-155">Изменения основываются на действиях пользователя (доступные, недоступные), состояниях календаря Outlook (на собрании) и о состояниях приложений Teams (в вызове, презентации) и состояниях, в которых отступы находятся в списке.</span><span class="sxs-lookup"><span data-stu-id="d9265-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="d9265-156">Время ожидания бездействия в 15 минут, после которого текущее состояние присутствия сбрасывается на нет на месте.</span><span class="sxs-lookup"><span data-stu-id="d9265-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="d9265-157">Пользователи могут указать, кто может переключиться (то есть общаться с ними несмотря на состояние "не беспокоить").</span><span class="sxs-lookup"><span data-stu-id="d9265-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="d9265-158">Эти параметры доступны в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="d9265-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="d9265-159">Параметры администрирования в Teams по сравнению с Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d9265-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="d9265-160">Следующие параметры администратора в Skype для бизнеса отличаются в teams:</span><span class="sxs-lookup"><span data-stu-id="d9265-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="d9265-161">В Teams доступ к присутствии всегда включен для пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="d9265-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="d9265-162">Конфиденциальность (определение пользователей, которые могут видеть состояние присутствия) недоступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="d9265-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="d9265-163">Предоставление общего предоставления сведений о присутствии для всех пользователей (в том числе федеративных служб) всегда разрешено пользователям в Teams.</span><span class="sxs-lookup"><span data-stu-id="d9265-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="d9265-164">Список контактов в Skype для бизнеса отображается в разделе " **чат" > "Контакты** " или " **звонки > контакты**".</span><span class="sxs-lookup"><span data-stu-id="d9265-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="d9265-165">Клиент не переносятся, а функции, появляющиеся неактивными, всегда включаются для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="d9265-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="d9265-166">Календарь (в том числе сведения об отсутствии на рабочем месте и другие данные календаря) интеграция всегда включена для пользователей при интеграции Teams с Outlook.</span><span class="sxs-lookup"><span data-stu-id="d9265-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="d9265-167">Если в организации также используется Skype для бизнеса, индикатор " *Последнее обнаружение* " или "нет на *месте* " всегда включен для пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="d9265-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="d9265-168">Возможность администраторам Teams настраивать эти параметры в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d9265-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="d9265-169">Сосуществование со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d9265-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="d9265-170">Узнайте подробнее о том, как работает функция присутствия в вашей организации, если в вашей компании используется Skype для бизнеса ( [сосуществование в Skype для бизнеса](coexistence-chat-calls-presence.md) ).</span><span class="sxs-lookup"><span data-stu-id="d9265-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
