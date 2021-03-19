---
title: Режим собраний только для просмотра
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения об режиме собраний Teams только для просмотра администраторами, выступающими и участниками
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875059"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="9982a-103">Режим собраний Teams только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9982a-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="9982a-104">Трансляции только для просмотра доступны в Microsoft 365 E3/E5 и Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="9982a-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="9982a-105">Эта функция станет доступна 1 марта 2021 г. в отключенном по умолчанию состоянии.</span><span class="sxs-lookup"><span data-stu-id="9982a-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="9982a-106">Развертывание функции в облаке сообщества для государственных организаций Microsoft 365 (GCC) начнется в конце марта 2021 г.</span><span class="sxs-lookup"><span data-stu-id="9982a-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="9982a-107">Развертывание в облаке сообщества для государственных организаций High (GCCH) и Министерства обороны (DoD) будет осуществлено позже.</span><span class="sxs-lookup"><span data-stu-id="9982a-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="9982a-108">Если нужно включить эту функцию по умолчанию, после указанной даты измените политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9982a-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="9982a-109">Используйте PowerShell, чтобы включить политику `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="9982a-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="9982a-110">Если ваше собрание или вебинар достигает ограничения по вместимости, Teams легко масштабируется для поддержки режима трансляции только для просмотра 10 000 пользователями.</span><span class="sxs-lookup"><span data-stu-id="9982a-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="9982a-111">Кроме того, сейчас, когда возрос объем удаленной работы, вы можете воспользоваться трансляциями для 20 000 человек до конца этого года.</span><span class="sxs-lookup"><span data-stu-id="9982a-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="9982a-112">Microsoft Teams позволяет присоединить к собранию Teams до 10 000 участников.</span><span class="sxs-lookup"><span data-stu-id="9982a-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="9982a-113">После достижения предельной вместимости основного собрания дополнительные участники будут присоединяться в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="9982a-114">Участники, присоединившиеся к собранию первыми (до достижения предельной вместимости собрания), смогут использовать все возможности собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="9982a-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="9982a-115">Они могут делиться звуком и видео, просматривать демонстрируемые видео и участвовать в чате собрания.</span><span class="sxs-lookup"><span data-stu-id="9982a-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="9982a-116">Участникам, присоединившимся после достижения предельной вместимости собрания, будет доступен режим только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="9982a-117">Присоединение участников полностью поддерживается на мобильных устройствах с Android и iOS.</span><span class="sxs-lookup"><span data-stu-id="9982a-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="9982a-118">Текущее ограничение по количеству людей, которые могут общаться в чате и звонить в собрание, составляет 300 человек в облаке WW и 250 человек — в облаках GCC, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="9982a-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="9982a-119">Режим только для просмотра отключен по умолчанию для любого организатора с SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="9982a-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="9982a-120">Дальнейшая настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="9982a-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="9982a-121">Отключение режима Teams только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9982a-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="9982a-122">Администраторы могут отключить режим только просмотра с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9982a-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="9982a-123">В будущем администраторы также смогут отключить режим только для просмотра в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="9982a-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="9982a-124">Влияние на пользователей</span><span class="sxs-lookup"><span data-stu-id="9982a-124">Impact to users</span></span>

<span data-ttu-id="9982a-125">Взаимодействие с пользователем зависит от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="9982a-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="9982a-126">После достижения предельной вместимости собрания участник не сможет присоединиться к собранию, если выполняется любое из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="9982a-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="9982a-127">Администратор отключил режим Teams только для просмотра. </span><span class="sxs-lookup"><span data-stu-id="9982a-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="9982a-128">У участника нет разрешения на обход "зала ожидания".</span><span class="sxs-lookup"><span data-stu-id="9982a-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="9982a-129">После достижения предельной вместимости собрания организатор и выступающие собрания увидят баннер, информирующий о том, что достигнута предельная вместимость собрания и что новые участники будут присоединяться с правом только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![клиент Teams и сообщение баннера для организаторов и выступающих](media/chat-and-banner-message.png)

<span data-ttu-id="9982a-131">После достижения предельной вместимости собрания участники собрания увидят на экране предварительного присоединения уведомление о том, что они присоединяются в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![экран предварительного присоединения к Teams и сообщение для участников о том, что они присоединятся в режиме только для просмотра](media/view-only-pre-join-screen.png)

<span data-ttu-id="9982a-133">При наличии мест пользователь всегда присоединяется к основному собранию.</span><span class="sxs-lookup"><span data-stu-id="9982a-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="9982a-134">Если в основном собрании достигнута предельная вместимость и один или несколько участников покидают основное собрание, в основном собрании появляются свободные места.</span><span class="sxs-lookup"><span data-stu-id="9982a-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="9982a-135">Участники, которые присоединяются (или повторно присоединяются) к собранию, присоединяются к основному собранию, пока не будет достигнута его предельная вместимость.</span><span class="sxs-lookup"><span data-stu-id="9982a-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="9982a-136">Участники, присоединившиеся в режиме только для просмотра, не повышаются автоматически до основного собрания, и в настоящее время их нельзя повысить до основного собрания вручную.</span><span class="sxs-lookup"><span data-stu-id="9982a-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="9982a-137">Если роли выступающего или участника не заданы, места в основном собрании заполняются в порядке очереди.</span><span class="sxs-lookup"><span data-stu-id="9982a-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="9982a-138">После достижения предельной вместимости собрания все остальные пользователи присоединяются к собранию в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="9982a-139">Влияние на выступающих на собраниях</span><span class="sxs-lookup"><span data-stu-id="9982a-139">Impact to meeting presenters</span></span>

<span data-ttu-id="9982a-140">Ограничения для выступающих на собраниях:</span><span class="sxs-lookup"><span data-stu-id="9982a-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="9982a-141">У вас не будет сведений об участнике с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="9982a-142">Обнаружение электронных данных не поддерживается для участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="9982a-143">Пользователи не могут видеть участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="9982a-144">Вы не можете удалить из собрания участника с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="9982a-145">Количество участников отражает только участников собрания, а не людей в комнате только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="9982a-146">Поэтому выступающие не могут узнать точное количество пользователей в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="9982a-147">Возможности для участников с разрешением только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9982a-147">Experience for view-only attendees</span></span>

<span data-ttu-id="9982a-148">Режим только для просмотра Teams позволяет участникам:</span><span class="sxs-lookup"><span data-stu-id="9982a-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="9982a-149">Слушать участников основного собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="9982a-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="9982a-150">Просматривать канал видео активного докладчика (если активный докладчик демонстрирует видео).</span><span class="sxs-lookup"><span data-stu-id="9982a-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="9982a-151">Просматривать содержимое, предоставляемое с помощью функции общего рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="9982a-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="9982a-152">Участник с разрешением только для просмотра не сможет воспользоваться следующими возможностями собраний.</span><span class="sxs-lookup"><span data-stu-id="9982a-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="9982a-153">Присоединение к собранию, если у участника нет разрешения на обход "зала ожидания" на основе установленных политик или параметров "зала ожидания".</span><span class="sxs-lookup"><span data-stu-id="9982a-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="9982a-154">Присоединение к комнате только для просмотра с помощью аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="9982a-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="9982a-155">Присоединение к комнате только для просмотра с помощью системы комнат Microsoft Teams или служб облачного видеовзаимодействия (CVI).</span><span class="sxs-lookup"><span data-stu-id="9982a-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="9982a-156">Демонстрация видео или звука.</span><span class="sxs-lookup"><span data-stu-id="9982a-156">Share their audio or video.</span></span>
- <span data-ttu-id="9982a-157">Просмотр чата собрания или участие в нем.</span><span class="sxs-lookup"><span data-stu-id="9982a-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="9982a-158">Просмотр канала видео участников собрания, если участник не является активным докладчиком.</span><span class="sxs-lookup"><span data-stu-id="9982a-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="9982a-159">Просмотр файлов PowerPoint, демонстрируемых с помощью собственных функций общего доступа PowerPoint или общего доступа отдельных приложений (кроме общего доступа к рабочему столу).</span><span class="sxs-lookup"><span data-stu-id="9982a-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="9982a-160">Ограничения режима только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9982a-160">View-only feature limitations</span></span>

- <span data-ttu-id="9982a-161">Участники с разрешением только для просмотра всегда будут видеть субтитры независимо от параметра субтитров для собрания.</span><span class="sxs-lookup"><span data-stu-id="9982a-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="9982a-162">В настоящее время поддерживаются только субтитры на английском языке.</span><span class="sxs-lookup"><span data-stu-id="9982a-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="9982a-163">Для участников с разрешением только для просмотра доступна поддержка технологии потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="9982a-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="9982a-164">Участники с разрешением только для просмотра не включаются в отчет об участниках.</span><span class="sxs-lookup"><span data-stu-id="9982a-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="9982a-165">Участникам с разрешением только для просмотра доступен режим одного видеоокна.</span><span class="sxs-lookup"><span data-stu-id="9982a-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="9982a-166">Они могут видеть либо активного выступающего, либо демонстрируемое содержимое (но не оба окна одновременно).</span><span class="sxs-lookup"><span data-stu-id="9982a-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="9982a-167">В настоящее время макеты **Галерея**, **Большая галерея** и **Режим "Вместе"** не поддерживаются для участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9982a-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="9982a-168">Задержка для участников с разрешением только для просмотра будет отличаться от задержки обычных участников.</span><span class="sxs-lookup"><span data-stu-id="9982a-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="9982a-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9982a-169"><sup>1</sup></span></span>

  <span data-ttu-id="9982a-170"><sup>1</sup> Для участников с разрешением только для просмотра будет применяться 30-секундная задержка видео и звука на собрании.</span><span class="sxs-lookup"><span data-stu-id="9982a-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
