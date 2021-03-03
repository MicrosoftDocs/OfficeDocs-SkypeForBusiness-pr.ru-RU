---
title: Только просмотр собраний
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Информация о представлении собраний Teams для администраторов, пользователей и участников
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49f65e1ff47caefd61a9b2753b12da23fd2184e9
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401323"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="ea9fb-103">Представление только для просмотра собраний Teams</span><span class="sxs-lookup"><span data-stu-id="ea9fb-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="ea9fb-104">Доступ к собраниям, доступным только для просмотра, будет доступен в начале марта 2021 г.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-104">View-only meeting experience will be available in early March 2021.</span></span> <span data-ttu-id="ea9fb-105">Эта функция будет включена 1 марта 2021 г. как выключенная по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-105">This feature will be enabled on March 1,2021 as default OFF.</span></span> <span data-ttu-id="ea9fb-106">Вы должны изменить политику по умолчанию после этой даты, если вы хотите, чтобы функция была по умолчанию ON.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-106">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="ea9fb-107">Чтобы включить политику, используйте `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-107">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="ea9fb-108">Если ваши собрания или вебинар похитят производительность, Teams без проблем масштабируется, чтобы вместить только просмотр в 10 000 человек.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-108">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="ea9fb-109">Кроме того, в это время, когда увеличивается объем удаленной работы, вы можете воспользоваться еще более крупными трансляциями с 20 000 человек до конца этого года.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-109">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="ea9fb-110">Microsoft Teams позволяет присоединиться к собранию Teams до 10 000 участников.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-110">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="ea9fb-111">После того как будет достигнуто количество участников основного собрания, другие участники будут присоединяться с представлением только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-111">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="ea9fb-112">Участники, которые первыми присоединяются к собранию (до его емкости), получают все возможности собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-112">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="ea9fb-113">Они могут делиться звуком и видео, видеть общие видео и участвовать в чате собрания.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-113">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="ea9fb-114">Участники, которые присоединяются к собранию после того, как достигнуто основное количество собраний, смогут работать только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-114">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="ea9fb-115">Участники присоединяются к собраниям с полной поддержкой мобильных устройств с Android и iOS.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-115">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="ea9fb-116">В настоящее время ограничение на количество пользователей, которые могут общаться и звонить на собрание, составляет 300 в WW и 250 в GCC, GCC High и DoD.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-116">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="ea9fb-117">По умолчанию режим просмотра отключен для всех организаторов, у которых есть SKU E3,E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-117">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="ea9fb-118">Дальнейшая настройка и настройка не требуются.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-118">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="ea9fb-119">Отключение только просмотра в Teams</span><span class="sxs-lookup"><span data-stu-id="ea9fb-119">Disable Teams view-only experience</span></span>

<span data-ttu-id="ea9fb-120">Администраторы могут отключить только просмотр с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-120">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="ea9fb-121">В будущем администраторы также смогут отключить возможности просмотра в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-121">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="ea9fb-122">Влияние на пользователей</span><span class="sxs-lookup"><span data-stu-id="ea9fb-122">Impact to users</span></span>

<span data-ttu-id="ea9fb-123">Пользовательский интерфейс зависит от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-123">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="ea9fb-124">После того как будет достигнуто количество участников основного собрания, участник не сможет присоединиться к собранию, если:</span><span class="sxs-lookup"><span data-stu-id="ea9fb-124">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="ea9fb-125">Администратор отключил для Teams только просмотр.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-125">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="ea9fb-126">У участника нет разрешения на обход "вести".</span><span class="sxs-lookup"><span data-stu-id="ea9fb-126">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="ea9fb-127">После того как будет достигнуто количество участников основного собрания, организатор и один из его участников увидят баннер, информирующий о том, что количество участников достигается и новые участники присоединятся к собранию только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-127">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![The Teams client and banner messsage for organizers and presenters](media/chat-and-banner-message.png)

<span data-ttu-id="ea9fb-129">После того как будет достигнуто количество участников основного собрания, участники собрания будут на экране предварительного присоединения сообщать о том, что они присоединяются в режиме просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-129">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Экран предварительного присоединиться к Teams и сообщение для участников о том, что они будут присоединяться в режиме только для просмотра](media/view-only-pre-join-screen.png)

<span data-ttu-id="ea9fb-131">Если места достаточно, пользователь всегда будет присоединяться к основному собранию.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-131">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="ea9fb-132">Если основное собрание достигается и один или несколько участников покидают главное собрание, его можно вместить.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-132">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="ea9fb-133">Участники, которые присоединяются к собранию или присоединяются к нему повторно, будут присоединяться к основному собранию, пока оно не достигнет мощности.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-133">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="ea9fb-134">Участники, которые работают только с просмотром, не будут автоматически повышены до главного собрания и в настоящее время не могут быть вручную повышены до основного собрания.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-134">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="ea9fb-135">Если роли участника и участника не заданы, пробелы в главном собрании заполняются первым.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-135">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="ea9fb-136">Когда собрание будет достигнуто, все остальные пользователи будут присоединяться к собранию только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-136">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="ea9fb-137">Влияние на лицев собраний</span><span class="sxs-lookup"><span data-stu-id="ea9fb-137">Impact to meeting presenters</span></span>

<span data-ttu-id="ea9fb-138">В число ограничений, накладывающихся на собрание, входят:</span><span class="sxs-lookup"><span data-stu-id="ea9fb-138">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="ea9fb-139">У вас не будет сведений об этом участнике.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-139">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="ea9fb-140">Мы не поддерживаем обнаружение электронных почты только для просмотров.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-140">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="ea9fb-141">Пользователи не могут просматривать только просмотр участников.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-141">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="ea9fb-142">Удалить участника из собрания, только для просмотра, нельзя.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-142">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="ea9fb-143">Число участников будет учитываться только для участников собрания, а не для участников в переполненном помещении.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-143">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="ea9fb-144">Таким образом, вы не сможете получить точное количество пользователей, которые будут использовать только просмотр.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-144">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="ea9fb-145">Просмотр только для участников</span><span class="sxs-lookup"><span data-stu-id="ea9fb-145">Experience for view-only attendees</span></span>

<span data-ttu-id="ea9fb-146">Возможность просмотра Только в Teams позволяет участникам:</span><span class="sxs-lookup"><span data-stu-id="ea9fb-146">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="ea9fb-147">Прослушав участников основного собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-147">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="ea9fb-148">Посмотрите видеосвязь активного выступающего (если активный докладчик обменивается видео).</span><span class="sxs-lookup"><span data-stu-id="ea9fb-148">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="ea9fb-149">Просмотр общего содержимого с помощью функции совместного использования рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-149">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="ea9fb-150">Участники, доступные только для просмотра, не смогут просматривать на собраниях следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ea9fb-150">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="ea9fb-151">Присоединитесь к собранию, если у участника нет разрешения на обход "вести", исходя из установленных политик и параметров "вести".</span><span class="sxs-lookup"><span data-stu-id="ea9fb-151">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="ea9fb-152">Присоединитесь к комнате переполнения с помощью аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-152">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="ea9fb-153">Присоединитесь к окну "Переполнение" с помощью системы комнат Microsoft Teams или службы Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="ea9fb-153">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="ea9fb-154">Поделитесь звуком или видео.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-154">Share their audio or video.</span></span>
- <span data-ttu-id="ea9fb-155">Смотреть или участвовать в чате собрания.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-155">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="ea9fb-156">Просмотр видеосвязи участников собрания, если участник не является активным выступающим.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-156">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="ea9fb-157">Вы можете видеть файлы PowerPoint, которые совместно используют функции общего доступа PowerPoint или отдельные общие папки приложений (кроме общего доступа к рабочему столу).</span><span class="sxs-lookup"><span data-stu-id="ea9fb-157">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="ea9fb-158">Ограничения функций только для просмотра</span><span class="sxs-lookup"><span data-stu-id="ea9fb-158">View-only feature limitations</span></span>

- <span data-ttu-id="ea9fb-159">Участники, только для просмотра, всегда будут видеть субтитры в прямом эфире независимо от параметров трансляции для этого собрания.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-159">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="ea9fb-160">В настоящее время поддерживаются только английские субтитры.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-160">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="ea9fb-161">Участники, только просматривавшие собрания, будут поддерживаться с помощью потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-161">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="ea9fb-162">Только для просмотра участники не включаются в отчет об посещение.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-162">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="ea9fb-163">Только для просмотра участники будут иметь один видеосвязь.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-163">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="ea9fb-164">Они могут видеть либо активного выступающего, либо совместное содержимое, но не оба.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-164">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="ea9fb-165">В настоящее время не поддерживаются  макеты **"Галерея",**"Большая **галерея"** и "Режим «Вместе» для участников, только для просмотра.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-165">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="ea9fb-166">У участников, только для просмотра, не будет такой же задержки, как у обычных участников.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-166">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="ea9fb-167"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea9fb-167"><sup>1</sup></span></span>

  <span data-ttu-id="ea9fb-168"><sup>1</sup> Участники собрания будут проходить с задержкой в 30 секунд по видеосвязи и звуку.</span><span class="sxs-lookup"><span data-stu-id="ea9fb-168"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="ea9fb-169">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ea9fb-169">Related topics</span></span>

- [<span data-ttu-id="ea9fb-170">Надстройка "Дополнительные коммуникации" для Teams</span><span class="sxs-lookup"><span data-stu-id="ea9fb-170">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="ea9fb-171">Ограничения и спецификации для Teams</span><span class="sxs-lookup"><span data-stu-id="ea9fb-171">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
