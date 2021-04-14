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
ms.openlocfilehash: 09fe424dc576b6b167eec49e7cd8edf2f61d6cce
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697804"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="650e1-103">Режим собраний Teams только для просмотра</span><span class="sxs-lookup"><span data-stu-id="650e1-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="650e1-104">Трансляции только для просмотра доступны в Microsoft 365 E3/E5 и Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="650e1-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="650e1-105">Эта функция станет доступна 1 марта 2021 г. в отключенном по умолчанию состоянии.</span><span class="sxs-lookup"><span data-stu-id="650e1-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="650e1-106">Развертывание функции в облаке сообщества для государственных организаций Microsoft 365 (GCC) начнется в конце марта 2021 г.</span><span class="sxs-lookup"><span data-stu-id="650e1-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="650e1-107">Развертывание в облаке сообщества для государственных организаций High (GCCH) и Министерства обороны (DoD) будет осуществлено позже.</span><span class="sxs-lookup"><span data-stu-id="650e1-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="650e1-108">Если нужно включить эту функцию по умолчанию, после указанной даты измените политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="650e1-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="650e1-109">Используйте PowerShell, чтобы включить политику `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="650e1-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="650e1-110">Если ваше собрание или вебинар достигает ограничения по вместимости, Teams легко масштабируется для поддержки режима трансляции только для просмотра 10 000 пользователями.</span><span class="sxs-lookup"><span data-stu-id="650e1-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="650e1-111">Кроме того, сейчас, когда возрос объем удаленной работы, вы можете воспользоваться трансляциями для 20 000 человек до конца этого года.</span><span class="sxs-lookup"><span data-stu-id="650e1-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="650e1-112">Microsoft Teams позволяет присоединить к собранию Teams до 10 000 участников.</span><span class="sxs-lookup"><span data-stu-id="650e1-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="650e1-113">После того как будет достигнуто количество участников основного собрания (когда к собранию присоединяется 300 пользователей), к собранию будут присоединяться дополнительные участники с доступом только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-113">After the capacity of the main meeting has been reached (which is when 300 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="650e1-114">Участники, которые первыми присоединяются к собранию (до возможности основного собрания), получают все возможности собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="650e1-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="650e1-115">Они могут делиться звуком и видео, просматривать демонстрируемые видео и участвовать в чате собрания.</span><span class="sxs-lookup"><span data-stu-id="650e1-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="650e1-116">Участникам, присоединившимся после достижения предельной вместимости собрания, будет доступен режим только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="650e1-117">Участники смогут присоединиться к представлению с помощью рабочего стола, браузера и Teams Mobile (Android и iOS).</span><span class="sxs-lookup"><span data-stu-id="650e1-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="650e1-118">По текущему ограничению количество полностью интерактивных пользователей для "основного собрания" составляет 300 в WW и 250 в GCC, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="650e1-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="650e1-119">Элементы управления только просмотром в Teams</span><span class="sxs-lookup"><span data-stu-id="650e1-119">Teams view-only experience controls</span></span>

<span data-ttu-id="650e1-120">Вы можете включить только просмотр с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="650e1-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="650e1-121">Отключить только просмотр можно с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="650e1-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="650e1-122">В будущем вы сможете включить или отключить возможности просмотра в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="650e1-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="650e1-123">Влияние на пользователей</span><span class="sxs-lookup"><span data-stu-id="650e1-123">Impact to users</span></span>

<span data-ttu-id="650e1-124">Взаимодействие с пользователем зависит от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="650e1-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="650e1-125">После достижения предельной вместимости собрания участник не сможет присоединиться к собранию, если выполняется любое из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="650e1-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="650e1-126">Администратор отключил возможность просмотра Teams только для организатора или для всего клиента.</span><span class="sxs-lookup"><span data-stu-id="650e1-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="650e1-127">Участники, которые будут использовать только просмотр, не могут обойти "вести".</span><span class="sxs-lookup"><span data-stu-id="650e1-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="650e1-128">Например, если организатор собрания выбирает, что в  "вестибюле" будут участвовать только люди из моей организации, а участник за пределами организации по попытке присоединиться в качестве участника только для просмотра, он не сможет присоединиться.</span><span class="sxs-lookup"><span data-stu-id="650e1-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="650e1-129">Когда будет достигнуто максимальное количество участников основного собрания, организатор и зрители увидят баннер с данными о том, что новые участники будут присоединяться в качестве участников только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![клиент Teams и сообщение баннера для организаторов и выступающих](media/chat-and-banner-message.png)

<span data-ttu-id="650e1-131">После достижения предельной вместимости собрания участники собрания увидят на экране предварительного присоединения уведомление о том, что они присоединяются в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![экран предварительного присоединения к Teams и сообщение для участников о том, что они присоединятся в режиме только для просмотра](media/view-only-pre-join-screen.png)

<span data-ttu-id="650e1-133">При наличии мест пользователь всегда присоединяется к основному собранию.</span><span class="sxs-lookup"><span data-stu-id="650e1-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="650e1-134">Если в основном собрании достигнута предельная вместимость и один или несколько участников покидают основное собрание, в основном собрании появляются свободные места.</span><span class="sxs-lookup"><span data-stu-id="650e1-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="650e1-135">Участники, которые присоединяются (или повторно присоединяются) к собранию, присоединяются к основному собранию, пока не будет достигнута его предельная вместимость.</span><span class="sxs-lookup"><span data-stu-id="650e1-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="650e1-136">Участники, которые имеют режим только для просмотра, не будут автоматически выпучены на основное собрание и не могут быть вручную выпучены на основное собрание.</span><span class="sxs-lookup"><span data-stu-id="650e1-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="650e1-137">Если были назначены роли участника и один из них пытается присоединиться к собранию после того, как количество участников основного собрания достигло максимальной мощности, он присоединяется к собранию только для просмотра и имеет те же ограничения, что и другие участники, только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="650e1-138">Поддержка, при этом все ли они присоединятся к основному собранию, будет разорена позднее.</span><span class="sxs-lookup"><span data-stu-id="650e1-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="650e1-139">Организатору всегда будет гарантировано место в главном собрании.</span><span class="sxs-lookup"><span data-stu-id="650e1-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="650e1-140">Влияние на организаторов и организаторов собраний</span><span class="sxs-lookup"><span data-stu-id="650e1-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="650e1-141">К ограничениям для организаторов и организаторов собраний относятся:</span><span class="sxs-lookup"><span data-stu-id="650e1-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="650e1-142">У вас не будет сведений об участнике с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="650e1-143">Обнаружение электронных данных не поддерживается для участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="650e1-144">Пользователи в главном собрании не могут видеть только просмотр участников.</span><span class="sxs-lookup"><span data-stu-id="650e1-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="650e1-145">Вы не можете удалить из собрания участника с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="650e1-146">Число участников будет отражено только для участников основного собрания, а не для участников в комнате, только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="650e1-147">Поэтому выступающие не могут узнать точное количество пользователей в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="650e1-148">Возможности для участников с разрешением только для просмотра</span><span class="sxs-lookup"><span data-stu-id="650e1-148">Experience for view-only attendees</span></span>

<span data-ttu-id="650e1-149">Режим только для просмотра Teams позволяет участникам:</span><span class="sxs-lookup"><span data-stu-id="650e1-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="650e1-150">Слушать участников основного собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="650e1-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="650e1-151">Просматривать канал видео активного докладчика (если активный докладчик демонстрирует видео).</span><span class="sxs-lookup"><span data-stu-id="650e1-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="650e1-152">Просмотр общего содержимого с помощью функций совместного использования рабочего стола или экрана.</span><span class="sxs-lookup"><span data-stu-id="650e1-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="650e1-153">Участник с разрешением только для просмотра не сможет воспользоваться следующими возможностями собраний.</span><span class="sxs-lookup"><span data-stu-id="650e1-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="650e1-154">Присоединение к собранию, если у участника нет разрешения на обход "зала ожидания" на основе установленных политик или параметров "зала ожидания".</span><span class="sxs-lookup"><span data-stu-id="650e1-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="650e1-155">Присоединение к комнате только для просмотра с помощью аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="650e1-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="650e1-156">Присоединяйтесь к комнате, которая будет только для просмотра, с помощью системы комнат Microsoft Teams или службЫ Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="650e1-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="650e1-157">Демонстрация видео или звука.</span><span class="sxs-lookup"><span data-stu-id="650e1-157">Share their audio or video.</span></span>
- <span data-ttu-id="650e1-158">Просмотр чата собрания или участие в нем.</span><span class="sxs-lookup"><span data-stu-id="650e1-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="650e1-159">Просмотр канала видео участников собрания, если участник не является активным докладчиком.</span><span class="sxs-lookup"><span data-stu-id="650e1-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="650e1-160">См. файлы PowerPoint, к которые совместно используется функция PowerPoint Live или отдельные общие папки приложений (кроме общего доступа к рабочему столу или экрану).</span><span class="sxs-lookup"><span data-stu-id="650e1-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="650e1-161">Подними руку на собрании.</span><span class="sxs-lookup"><span data-stu-id="650e1-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="650e1-162">Отправка или просмотр реакций.</span><span class="sxs-lookup"><span data-stu-id="650e1-162">Send or see reactions.</span></span>
- <span data-ttu-id="650e1-163">Взаимодействие с приложением 3P, интегрированным в собрание Teams, включая опросы.</span><span class="sxs-lookup"><span data-stu-id="650e1-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="650e1-164">Ограничения режима только для просмотра</span><span class="sxs-lookup"><span data-stu-id="650e1-164">View-only feature limitations</span></span>

- <span data-ttu-id="650e1-165">Только для просмотра участники смогут просматривать субтитры в представлении "В сети" и "Рабочий стол".</span><span class="sxs-lookup"><span data-stu-id="650e1-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="650e1-166">В настоящее время поддерживаются только субтитры на английском языке.</span><span class="sxs-lookup"><span data-stu-id="650e1-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="650e1-167">Для участников с разрешением только для просмотра доступна поддержка технологии потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="650e1-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="650e1-168">Участники с разрешением только для просмотра не включаются в отчет об участниках.</span><span class="sxs-lookup"><span data-stu-id="650e1-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="650e1-169">Участникам с разрешением только для просмотра доступен режим одного видеоокна.</span><span class="sxs-lookup"><span data-stu-id="650e1-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="650e1-170">Они могут видеть либо активного выступающего, либо демонстрируемое содержимое (но не оба окна одновременно).</span><span class="sxs-lookup"><span data-stu-id="650e1-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="650e1-171">В настоящее время макеты **Галерея**, **Большая галерея** и **Режим "Вместе"** не поддерживаются для участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="650e1-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="650e1-172">Задержка для участников с разрешением только для просмотра будет отличаться от задержки обычных участников.</span><span class="sxs-lookup"><span data-stu-id="650e1-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="650e1-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="650e1-173"><sup>1</sup></span></span>

  <span data-ttu-id="650e1-174"><sup>1</sup> Для участников с разрешением только для просмотра будет применяться 30-секундная задержка видео и звука на собрании.</span><span class="sxs-lookup"><span data-stu-id="650e1-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
