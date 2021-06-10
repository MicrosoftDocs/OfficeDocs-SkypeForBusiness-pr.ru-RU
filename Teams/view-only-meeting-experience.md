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
ms.openlocfilehash: ca53c75d12964de2d4d458b240878b14fd2ad04b
ms.sourcegitcommit: ea9a0119d184179300e51f58ca4fee249c12d00a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2021
ms.locfileid: "52699350"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="9db08-103">Режим собраний Teams только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9db08-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="9db08-104">Трансляции только для просмотра доступны в Microsoft 365 E3/E5 и Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="9db08-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="9db08-105">Эта функция станет доступна 1 марта 2021 г. в отключенном по умолчанию состоянии.</span><span class="sxs-lookup"><span data-stu-id="9db08-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="9db08-106">Развертывание функции в облаке сообщества для государственных организаций Microsoft 365 (GCC) начнется в конце марта 2021 г.</span><span class="sxs-lookup"><span data-stu-id="9db08-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="9db08-107">Развертывание в облаке сообщества для государственных организаций High (GCCH) и Министерства обороны (DoD) будет осуществлено позже.</span><span class="sxs-lookup"><span data-stu-id="9db08-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="9db08-108">Если нужно включить эту функцию по умолчанию, после указанной даты измените политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9db08-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="9db08-109">Используйте PowerShell, чтобы включить политику `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="9db08-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="9db08-110">Если ваше собрание проходит в Teams масштаб будет полностью масштабироваться, чтобы вместить только 10 000 человек для широковещательного просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-110">If your meeting hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="9db08-111">Кроме того, сейчас, когда возрос объем удаленной работы, вы можете воспользоваться трансляциями для 20 000 человек до конца этого года.</span><span class="sxs-lookup"><span data-stu-id="9db08-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="9db08-112">Microsoft Teams позволяет присоединить к собранию Teams до 10 000 участников.</span><span class="sxs-lookup"><span data-stu-id="9db08-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="9db08-113">После того как будет достигнуто количество участников основного собрания (в которое входит 1000 пользователей), дополнительные участники присоединятся к собранию с доступом только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-113">After the capacity of the main meeting has been reached (which is when 1000 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="9db08-114">Участники, которые присоединяются к собранию в первую очередь (до основного), получают полный Teams собрания.</span><span class="sxs-lookup"><span data-stu-id="9db08-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="9db08-115">Они могут делиться звуком и видео, просматривать демонстрируемые видео и участвовать в чате собрания.</span><span class="sxs-lookup"><span data-stu-id="9db08-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="9db08-116">Участникам, присоединившимся после достижения предельной вместимости собрания, будет доступен режим только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="9db08-117">Участники смогут присоединиться к представлению только с помощью рабочего стола, браузера и мобильного Teams (Android и iOS).</span><span class="sxs-lookup"><span data-stu-id="9db08-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="9db08-118">Текущее предельное количество участников "основного собрания", то есть количество полностью интерактивных пользователей, составляет 1000, и в него входит GCC.</span><span class="sxs-lookup"><span data-stu-id="9db08-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 1000 and includes GCC.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="9db08-119">Teams только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9db08-119">Teams view-only experience controls</span></span>

<span data-ttu-id="9db08-120">Вы можете включить только просмотр с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9db08-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="9db08-121">Чтобы отключить представление только для просмотра, можно также использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9db08-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="9db08-122">В будущем вы сможете включить или отключить интерфейс только для Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="9db08-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="9db08-123">Влияние на пользователей</span><span class="sxs-lookup"><span data-stu-id="9db08-123">Impact to users</span></span>

<span data-ttu-id="9db08-124">Взаимодействие с пользователем зависит от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="9db08-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="9db08-125">После достижения предельной вместимости собрания участник не сможет присоединиться к собранию, если выполняется любое из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="9db08-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="9db08-126">Администратор отключил Teams только для организатора или для всего клиента.</span><span class="sxs-lookup"><span data-stu-id="9db08-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="9db08-127">Участники, которые будут использовать только просмотр, не могут минуть "lobby".</span><span class="sxs-lookup"><span data-stu-id="9db08-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="9db08-128">Например, если организатор собрания выбирает, что в  "вестибюле" должны быть только люди из моей организации, а участник за пределами организации пытается присоединиться как участник только для просмотра, он не сможет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="9db08-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="9db08-129">После того как будет достигнуто максимальное количество участников основного собрания, организатор собрания и его участники увидят баннер, информирующий о том, что новые участники будут присоединяться в качестве участников только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![клиент Teams и сообщение баннера для организаторов и выступающих](media/chat-and-banner-message.png)

<span data-ttu-id="9db08-131">После достижения предельной вместимости собрания участники собрания увидят на экране предварительного присоединения уведомление о том, что они присоединяются в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![экран предварительного присоединения к Teams и сообщение для участников о том, что они присоединятся в режиме только для просмотра](media/view-only-pre-join-screen.png)

<span data-ttu-id="9db08-133">При наличии мест пользователь всегда присоединяется к основному собранию.</span><span class="sxs-lookup"><span data-stu-id="9db08-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="9db08-134">Если в основном собрании достигнута предельная вместимость и один или несколько участников покидают основное собрание, в основном собрании появляются свободные места.</span><span class="sxs-lookup"><span data-stu-id="9db08-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="9db08-135">Участники, которые присоединяются (или повторно присоединяются) к собранию, присоединяются к основному собранию, пока не будет достигнута его предельная вместимость.</span><span class="sxs-lookup"><span data-stu-id="9db08-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="9db08-136">Участники, которые имеют представление только для просмотра, не будут автоматически повышены до основного собрания и не могут быть вручную повышены до основного собрания.</span><span class="sxs-lookup"><span data-stu-id="9db08-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="9db08-137">Если установлены роли участника и он пытается присоединиться к собранию после того, как основное собрание достигло необходимой емкости, он присоединяется к собранию как участник только для просмотра и имеет те же ограничения, что и другие участники, только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="9db08-138">Поддержка для того, чтобы все ли они присоединились к основному собранию, будут развернуты позже.</span><span class="sxs-lookup"><span data-stu-id="9db08-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="9db08-139">Организатору всегда будет гарантировано место в главном собрании.</span><span class="sxs-lookup"><span data-stu-id="9db08-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="9db08-140">Влияние на организаторов и организаторов собраний</span><span class="sxs-lookup"><span data-stu-id="9db08-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="9db08-141">К ограничениям, которые могут быть у организаторов и лицев собраний, относятся:</span><span class="sxs-lookup"><span data-stu-id="9db08-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="9db08-142">У вас не будет сведений об участнике с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="9db08-143">Обнаружение электронных данных не поддерживается для участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="9db08-144">Пользователи в основном собрании не могут видеть участников, которые будут видеть только просмотр.</span><span class="sxs-lookup"><span data-stu-id="9db08-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="9db08-145">Вы не можете удалить из собрания участника с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="9db08-146">Число участников будет отражено только в основном собрании, а не в представлении.</span><span class="sxs-lookup"><span data-stu-id="9db08-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="9db08-147">Поэтому выступающие не могут узнать точное количество пользователей в режиме только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="9db08-148">Возможности для участников с разрешением только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9db08-148">Experience for view-only attendees</span></span>

<span data-ttu-id="9db08-149">Режим только для просмотра Teams позволяет участникам:</span><span class="sxs-lookup"><span data-stu-id="9db08-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="9db08-150">Слушать участников основного собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="9db08-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="9db08-151">Просматривать канал видео активного докладчика (если активный докладчик демонстрирует видео).</span><span class="sxs-lookup"><span data-stu-id="9db08-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="9db08-152">Просмотр общего содержимого с помощью функций общего использования рабочего стола или экрана.</span><span class="sxs-lookup"><span data-stu-id="9db08-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="9db08-153">Участник с разрешением только для просмотра не сможет воспользоваться следующими возможностями собраний.</span><span class="sxs-lookup"><span data-stu-id="9db08-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="9db08-154">Присоединение к собранию, если у участника нет разрешения на обход "зала ожидания" на основе установленных политик или параметров "зала ожидания".</span><span class="sxs-lookup"><span data-stu-id="9db08-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="9db08-155">Присоединение к комнате только для просмотра с помощью аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="9db08-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="9db08-156">Присоединяйтесь к комнате, которая используется только для просмотра, Комнаты Microsoft Teams систему или службы Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="9db08-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="9db08-157">Демонстрация видео или звука.</span><span class="sxs-lookup"><span data-stu-id="9db08-157">Share their audio or video.</span></span>
- <span data-ttu-id="9db08-158">Просмотр чата собрания или участие в нем.</span><span class="sxs-lookup"><span data-stu-id="9db08-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="9db08-159">Просмотр канала видео участников собрания, если участник не является активным докладчиком.</span><span class="sxs-lookup"><span data-stu-id="9db08-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="9db08-160">См. PowerPoint файлов, к которые совместно используется функция PowerPoint Live или отдельные общие папки приложений (кроме общего доступа к рабочему столу или экрану).</span><span class="sxs-lookup"><span data-stu-id="9db08-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="9db08-161">Подними руку на собрании.</span><span class="sxs-lookup"><span data-stu-id="9db08-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="9db08-162">Отправка и просмотр реакций.</span><span class="sxs-lookup"><span data-stu-id="9db08-162">Send or see reactions.</span></span>
- <span data-ttu-id="9db08-163">Взаимодействие с любым приложением 3P, интегрированным в Teams собрания, включая опросы.</span><span class="sxs-lookup"><span data-stu-id="9db08-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="9db08-164">Ограничения режима только для просмотра</span><span class="sxs-lookup"><span data-stu-id="9db08-164">View-only feature limitations</span></span>

- <span data-ttu-id="9db08-165">Только для просмотра участники смогут видеть субтитры только в классических и веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="9db08-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="9db08-166">В настоящее время поддерживаются только субтитры на английском языке.</span><span class="sxs-lookup"><span data-stu-id="9db08-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="9db08-167">Для участников с разрешением только для просмотра доступна поддержка технологии потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="9db08-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="9db08-168">Участники с разрешением только для просмотра не включаются в отчет об участниках.</span><span class="sxs-lookup"><span data-stu-id="9db08-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="9db08-169">Участникам с разрешением только для просмотра доступен режим одного видеоокна.</span><span class="sxs-lookup"><span data-stu-id="9db08-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="9db08-170">Они могут видеть либо активного выступающего, либо демонстрируемое содержимое (но не оба окна одновременно).</span><span class="sxs-lookup"><span data-stu-id="9db08-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="9db08-171">В настоящее время макеты **Галерея**, **Большая галерея** и **Режим "Вместе"** не поддерживаются для участников с разрешением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="9db08-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="9db08-172">Задержка для участников с разрешением только для просмотра будет отличаться от задержки обычных участников.</span><span class="sxs-lookup"><span data-stu-id="9db08-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="9db08-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9db08-173"><sup>1</sup></span></span>

  <span data-ttu-id="9db08-174"><sup>1</sup> Для участников с разрешением только для просмотра будет применяться 30-секундная задержка видео и звука на собрании.</span><span class="sxs-lookup"><span data-stu-id="9db08-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
