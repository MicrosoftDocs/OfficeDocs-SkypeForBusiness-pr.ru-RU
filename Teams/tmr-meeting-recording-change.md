---
title: Использование OneDrive и SharePoint для записей собраний
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как переключаться между потоком в OneDrive для бизнеса и в хранилище записей собраний SharePoint в Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c0d50686346b715ca7e10b455845927ff22341
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218410"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="8d620-103">Использование OneDrive для бизнеса и SharePoint или Stream для записей собраний</span><span class="sxs-lookup"><span data-stu-id="8d620-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="8d620-104">Поэтапный подход к изменению с помощью Microsoft Stream для OneDrive для бизнеса и SharePoint для записей собраний.</span><span class="sxs-lookup"><span data-stu-id="8d620-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="8d620-105">На этапе запуска вы сможете принять участие в этой службе, в ноябре вам придется отказаться от использования потока, и в некоторых случаях на раннем этапе 2021 мы постараемся, чтобы все пользователи могли использовать OneDrive для бизнеса и SharePoint для новых записей о собраниях.</span><span class="sxs-lookup"><span data-stu-id="8d620-105">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="8d620-106">В Microsoft Teams имеется новый способ сохранения записей собраний.</span><span class="sxs-lookup"><span data-stu-id="8d620-106">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="8d620-107">Как и в случае с потоком, этот метод использует Microsoft OneDrive и SharePoint в Microsoft 365 и предоставляет множество преимуществ.</span><span class="sxs-lookup"><span data-stu-id="8d620-107">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits:</span></span>

<span data-ttu-id="8d620-108">С помощью OneDrive для бизнеса и SharePoint для хранения записей доступны следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="8d620-108">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="8d620-109">Политики хранения для записи собрания в Teams (TMR) (S + C, метки автохранения)</span><span class="sxs-lookup"><span data-stu-id="8d620-109">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="8d620-110">Преимущества из OneDrive для бизнеса и информационной системы SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d620-110">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="8d620-111">Простота настройки разрешений и общего доступа</span><span class="sxs-lookup"><span data-stu-id="8d620-111">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="8d620-112">Предоставление общего доступа к записям для гостей (внешних пользователей) с явной общим доступом</span><span class="sxs-lookup"><span data-stu-id="8d620-112">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="8d620-113">Поток запросов на доступ</span><span class="sxs-lookup"><span data-stu-id="8d620-113">Request access flow</span></span>
- <span data-ttu-id="8d620-114">Предоставление общих ссылок в OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d620-114">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="8d620-115">Повышенная квота</span><span class="sxs-lookup"><span data-stu-id="8d620-115">Increased quota</span></span>
- <span data-ttu-id="8d620-116">Записи собраний доступны быстрее</span><span class="sxs-lookup"><span data-stu-id="8d620-116">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="8d620-117">**Переход** на поддержку локального клиента</span><span class="sxs-lookup"><span data-stu-id="8d620-117">**Go local** tenant support</span></span>
- <span data-ttu-id="8d620-118">Поддержка нескольких географических регионов — записи хранятся в определенном пользователем регионе.</span><span class="sxs-lookup"><span data-stu-id="8d620-118">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="8d620-119">Подведите поддержку ключа (BYOK)</span><span class="sxs-lookup"><span data-stu-id="8d620-119">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="8d620-120">Улучшенное качество транскрипции и атрибуты динамиков</span><span class="sxs-lookup"><span data-stu-id="8d620-120">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="8d620-121">Есть ряд ограничений, которые следует принимать во что:</span><span class="sxs-lookup"><span data-stu-id="8d620-121">There are some limitations to consider:</span></span>

- <span data-ttu-id="8d620-122">Будут закрыты субтитры и записи с английским языком.</span><span class="sxs-lookup"><span data-stu-id="8d620-122">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="8d620-123">Вы не сможете искать записи и их содержимое.</span><span class="sxs-lookup"><span data-stu-id="8d620-123">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="8d620-124">Вы не сможете изменять транскрипции, но сможете включать и отключать субтитры.</span><span class="sxs-lookup"><span data-stu-id="8d620-124">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="8d620-125">Вы можете управлять тем, кому предоставлен доступ к записи, но вы не сможете блокировать пользователей с общим доступом для загрузки записи.</span><span class="sxs-lookup"><span data-stu-id="8d620-125">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="8d620-126">Вы не получите сообщение по электронной почте, когда запись завершит сохранение, но запись появится в разделе чата собрания после ее завершения.</span><span class="sxs-lookup"><span data-stu-id="8d620-126">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="8d620-127">Это происходит гораздо быстрее, чем в потоке ранее</span><span class="sxs-lookup"><span data-stu-id="8d620-127">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="8d620-128">Дополнительные сведения смотрите в записях собрания.</span><span class="sxs-lookup"><span data-stu-id="8d620-128">Watch "Meeting Recording" for more information.</span></span> 

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8] 

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="8d620-129">Настройка параметров записи собраний для OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d620-129">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="8d620-130">Установите консоль администрирования PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8d620-130">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="8d620-131">а)</span><span class="sxs-lookup"><span data-stu-id="8d620-131">a.</span></span> <span data-ttu-id="8d620-132">Скачайте [Skype для бизнеса Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8d620-132">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="8d620-133">б)</span><span class="sxs-lookup"><span data-stu-id="8d620-133">b.</span></span> <span data-ttu-id="8d620-134">Следуйте инструкциям по установке.</span><span class="sxs-lookup"><span data-stu-id="8d620-134">Follow the prompts to install it.</span></span>

    <span data-ttu-id="8d620-135">в.</span><span class="sxs-lookup"><span data-stu-id="8d620-135">c.</span></span> <span data-ttu-id="8d620-136">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="8d620-136">Restart your machine.</span></span>

2. <span data-ttu-id="8d620-137">Запуск PowerShell с правами администратора</span><span class="sxs-lookup"><span data-stu-id="8d620-137">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="8d620-138">Импортируйте соединитель SkypeOnline и войдите в систему как администратор Teams.</span><span class="sxs-lookup"><span data-stu-id="8d620-138">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="8d620-139">С помощью [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) можно настроить политику собрания Teams на переход из хранилища потоков в ODSP.</span><span class="sxs-lookup"><span data-stu-id="8d620-139">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="8d620-140">Отказ от OneDrive для бизнеса и SharePoint для продолжения использования потока</span><span class="sxs-lookup"><span data-stu-id="8d620-140">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="8d620-141">Даже если политика говорит о том, что для нее уже задано значение **Stream**, возможно, она не задана.</span><span class="sxs-lookup"><span data-stu-id="8d620-141">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="8d620-142">Если для него установлено значение Nothing, по умолчанию используется Stream.</span><span class="sxs-lookup"><span data-stu-id="8d620-142">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="8d620-143">Если вы хотите отказаться от этого, **необходимо** сбросить политику на **Stream** , чтобы обеспечить, чтобы поток был установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8d620-143">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="8d620-144">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="8d620-144">Frequently asked questions</span></span>

<span data-ttu-id="8d620-145">**Где будет храниться запись собрания?**</span><span class="sxs-lookup"><span data-stu-id="8d620-145">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="8d620-146">Для собраний, не являющихся каналами, запись сохраняется в папке с именем.</span><span class="sxs-lookup"><span data-stu-id="8d620-146">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="8d620-147">Записи \* \* находятся на высшем уровне OneDrive, принадлежащем пользователю, который запустил запись собрания.</span><span class="sxs-lookup"><span data-stu-id="8d620-147">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="8d620-148">Образом</span><span class="sxs-lookup"><span data-stu-id="8d620-148">Example:</span></span>

  <span data-ttu-id="8d620-149"><i>OneDrive для бизнеса</i> / с записью **Записи**</span><span class="sxs-lookup"><span data-stu-id="8d620-149"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="8d620-150">Для собраний по каналам запись сохраняется в библиотеке документации сайта Teams в папке с именем Records ( **записи**).</span><span class="sxs-lookup"><span data-stu-id="8d620-150">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="8d620-151">Образом</span><span class="sxs-lookup"><span data-stu-id="8d620-151">Example:</span></span>

  <span data-ttu-id="8d620-152"><i>Имя группы: название канала</i> / **Документы** / **Записи**</span><span class="sxs-lookup"><span data-stu-id="8d620-152"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="8d620-153">**У кого есть разрешения на просмотр записи собрания?**</span><span class="sxs-lookup"><span data-stu-id="8d620-153">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="8d620-154">Для собраний, не являющихся каналами, все участники собрания, кроме внешних пользователей, будут автоматически получать общую ссылку.</span><span class="sxs-lookup"><span data-stu-id="8d620-154">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="8d620-155">Внешние пользователи должны быть явно добавлены в общий список организатором собрания или пользователем, который запустил запись собрания.</span><span class="sxs-lookup"><span data-stu-id="8d620-155">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="8d620-156">Для собраний по каналам разрешения наследуются из списка владельцы и участники в канале.</span><span class="sxs-lookup"><span data-stu-id="8d620-156">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="8d620-157">**Как управлять записями?**</span><span class="sxs-lookup"><span data-stu-id="8d620-157">**How can I manage transcripts?**</span></span>

<span data-ttu-id="8d620-158">Пользователи, не прошедшие в этом предварительном просмотре, не смогут использовать субтитры, доступные в записях собрания Teams, которые перенесены в OneDrive и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8d620-158">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="8d620-159">Мы работаем над добавлением субтитров, начинающих с субтитров на английском языке и записями о собраниях в октябре 2020.</span><span class="sxs-lookup"><span data-stu-id="8d620-159">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="8d620-160">Закрытые субтитры будут доступны в записях собраний Teams для пользователей, которые не участвуют в разрешении на запись, как описано в [облачных записях Teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="8d620-160">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="8d620-161">С помощью подписей вы создадите инклюзивное содержимое для просмотра всех возможностей.</span><span class="sxs-lookup"><span data-stu-id="8d620-161">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="8d620-162">Как владелец, вы можете скрыть субтитры, хотя он по-прежнему будет доступен в Teams, если вы не удалите их из Teams.</span><span class="sxs-lookup"><span data-stu-id="8d620-162">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="8d620-163">Узнайте [, как включить или отключить записи собраний](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="8d620-163">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="8d620-164">Скрытые субтитры поддерживаются для записей собраний Teams в течение 60 дней с момента регистрации собрания.</span><span class="sxs-lookup"><span data-stu-id="8d620-164">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="8d620-165">**Как будет влиять квота хранилища**</span><span class="sxs-lookup"><span data-stu-id="8d620-165">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="8d620-166">Файлы записываются в OneDrive для бизнеса и SharePoint с помощью группового собрания, которые включены в вашу квоту для этих служб.</span><span class="sxs-lookup"><span data-stu-id="8d620-166">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="8d620-167">Ознакомьтесь с [квотой SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) и [квота OneDrive для бизнеса] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="8d620-167">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="8d620-168">**Как можно воспроизвести запись собрания группы?**</span><span class="sxs-lookup"><span data-stu-id="8d620-168">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="8d620-169">Видео будет воспроизводиться на видеопроигрывателе OneDrive для бизнеса или SharePoint в зависимости от того, где вы хотите получить доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="8d620-169">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>
