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
ms.openlocfilehash: d1072f86d019415dbc97d0507ff9d76b2cbdc6e6
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269643"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="e71c9-103">Использование OneDrive для бизнеса и SharePoint или Stream для записей собраний</span><span class="sxs-lookup"><span data-stu-id="e71c9-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="e71c9-104">Переход с использования Microsoft Stream на OneDrive для бизнеса и SharePoint для записей собраний будет поэтапным процессом.</span><span class="sxs-lookup"><span data-stu-id="e71c9-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="e71c9-105">При запуске Администраторы клиентов могут выбрать этот вариант рабочего процесса сегодня и начать просмотр записей с автоматическим добавлением в OneDrive для бизнеса и SharePoint в октябре 2020.</span><span class="sxs-lookup"><span data-stu-id="e71c9-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="e71c9-106">В ноябре вам придется отказаться от использования Stream, и на раннем этапе 2021 потребуется, чтобы все пользователи использовали OneDrive для бизнеса и SharePoint для новых записей собрания.</span><span class="sxs-lookup"><span data-stu-id="e71c9-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="e71c9-107">В Microsoft Teams имеется новый способ сохранения записей собраний.</span><span class="sxs-lookup"><span data-stu-id="e71c9-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="e71c9-108">Как и в случае с потоком, этот метод использует Microsoft OneDrive и SharePoint в Microsoft 365 и предоставляет множество преимуществ.</span><span class="sxs-lookup"><span data-stu-id="e71c9-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="e71c9-109">С помощью OneDrive для бизнеса и SharePoint для хранения записей доступны следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="e71c9-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="e71c9-110">Политики хранения для записи собрания в Teams (TMR) (S + C, метки автохранения)</span><span class="sxs-lookup"><span data-stu-id="e71c9-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="e71c9-111">Преимущества из OneDrive для бизнеса и информационной системы SharePoint</span><span class="sxs-lookup"><span data-stu-id="e71c9-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="e71c9-112">Простота настройки разрешений и общего доступа</span><span class="sxs-lookup"><span data-stu-id="e71c9-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="e71c9-113">Предоставление общего доступа к записям для гостей (внешних пользователей) с явной общим доступом</span><span class="sxs-lookup"><span data-stu-id="e71c9-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="e71c9-114">Поток запросов на доступ</span><span class="sxs-lookup"><span data-stu-id="e71c9-114">Request access flow</span></span>
- <span data-ttu-id="e71c9-115">Предоставление общих ссылок в OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="e71c9-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="e71c9-116">Повышенная квота</span><span class="sxs-lookup"><span data-stu-id="e71c9-116">Increased quota</span></span>
- <span data-ttu-id="e71c9-117">Записи собраний доступны быстрее</span><span class="sxs-lookup"><span data-stu-id="e71c9-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="e71c9-118">**Переход** на поддержку локального клиента</span><span class="sxs-lookup"><span data-stu-id="e71c9-118">**Go local** tenant support</span></span>
- <span data-ttu-id="e71c9-119">Поддержка нескольких географических регионов — записи хранятся в определенном пользователем регионе.</span><span class="sxs-lookup"><span data-stu-id="e71c9-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="e71c9-120">Подведите поддержку ключа (BYOK)</span><span class="sxs-lookup"><span data-stu-id="e71c9-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="e71c9-121">Улучшенное качество транскрипции и атрибуты динамиков</span><span class="sxs-lookup"><span data-stu-id="e71c9-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="e71c9-122">Есть ряд ограничений, которые следует принимать во что:</span><span class="sxs-lookup"><span data-stu-id="e71c9-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="e71c9-123">Будут закрыты субтитры и записи с английским языком.</span><span class="sxs-lookup"><span data-stu-id="e71c9-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="e71c9-124">Вы не сможете искать записи и их содержимое.</span><span class="sxs-lookup"><span data-stu-id="e71c9-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="e71c9-125">Вы не сможете изменять транскрипции, но сможете включать и отключать субтитры.</span><span class="sxs-lookup"><span data-stu-id="e71c9-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="e71c9-126">Вы можете управлять тем, кому предоставлен доступ к записи, но вы не сможете блокировать пользователей с общим доступом для загрузки записи.</span><span class="sxs-lookup"><span data-stu-id="e71c9-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="e71c9-127">Вы не получите сообщение по электронной почте, когда запись завершит сохранение, но запись появится в разделе чата собрания после ее завершения.</span><span class="sxs-lookup"><span data-stu-id="e71c9-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="e71c9-128">Это происходит гораздо быстрее, чем в потоке ранее</span><span class="sxs-lookup"><span data-stu-id="e71c9-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="e71c9-129">Дополнительные сведения смотрите в записях собрания.</span><span class="sxs-lookup"><span data-stu-id="e71c9-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="e71c9-130">Настройка параметров записи собраний для OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="e71c9-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="e71c9-131">Установите консоль администрирования PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e71c9-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="e71c9-132">а)</span><span class="sxs-lookup"><span data-stu-id="e71c9-132">a.</span></span> <span data-ttu-id="e71c9-133">Скачайте [Skype для бизнеса Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="e71c9-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="e71c9-134">б)</span><span class="sxs-lookup"><span data-stu-id="e71c9-134">b.</span></span> <span data-ttu-id="e71c9-135">Следуйте инструкциям по установке.</span><span class="sxs-lookup"><span data-stu-id="e71c9-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="e71c9-136">в.</span><span class="sxs-lookup"><span data-stu-id="e71c9-136">c.</span></span> <span data-ttu-id="e71c9-137">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="e71c9-137">Restart your machine.</span></span>

2. <span data-ttu-id="e71c9-138">Запуск PowerShell с правами администратора</span><span class="sxs-lookup"><span data-stu-id="e71c9-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="e71c9-139">Импортируйте соединитель SkypeOnline и войдите в систему как администратор Teams.</span><span class="sxs-lookup"><span data-stu-id="e71c9-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="e71c9-140">С помощью [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) можно настроить политику собрания Teams на переход из хранилища потоков в ODSP.</span><span class="sxs-lookup"><span data-stu-id="e71c9-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="e71c9-141">Отказ от OneDrive для бизнеса и SharePoint для продолжения использования потока</span><span class="sxs-lookup"><span data-stu-id="e71c9-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="e71c9-142">Даже если политика говорит о том, что для нее уже задано значение **Stream**, возможно, она не задана.</span><span class="sxs-lookup"><span data-stu-id="e71c9-142">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="e71c9-143">Если для него установлено значение Nothing, по умолчанию используется Stream.</span><span class="sxs-lookup"><span data-stu-id="e71c9-143">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="e71c9-144">Если вы хотите отказаться от этого, **необходимо** сбросить политику на **Stream** , чтобы обеспечить, чтобы поток был установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e71c9-144">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="e71c9-145">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="e71c9-145">Frequently asked questions</span></span>

<span data-ttu-id="e71c9-146">**Где будет храниться запись собрания?**</span><span class="sxs-lookup"><span data-stu-id="e71c9-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="e71c9-147">Для собраний, не являющихся каналами, запись сохраняется в папке с именем.</span><span class="sxs-lookup"><span data-stu-id="e71c9-147">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="e71c9-148">Записи \* \* находятся на высшем уровне OneDrive, принадлежащем пользователю, который запустил запись собрания.</span><span class="sxs-lookup"><span data-stu-id="e71c9-148">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="e71c9-149">Образом</span><span class="sxs-lookup"><span data-stu-id="e71c9-149">Example:</span></span>

  <span data-ttu-id="e71c9-150"><i>OneDrive для бизнеса</i> / с записью **Записи**</span><span class="sxs-lookup"><span data-stu-id="e71c9-150"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="e71c9-151">Для собраний по каналам запись сохраняется в библиотеке документации сайта Teams в папке с именем Records ( **записи**).</span><span class="sxs-lookup"><span data-stu-id="e71c9-151">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="e71c9-152">Образом</span><span class="sxs-lookup"><span data-stu-id="e71c9-152">Example:</span></span>

  <span data-ttu-id="e71c9-153"><i>Имя группы: название канала</i> / **Документы** / **Записи**</span><span class="sxs-lookup"><span data-stu-id="e71c9-153"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="e71c9-154">**У кого есть разрешения на просмотр записи собрания?**</span><span class="sxs-lookup"><span data-stu-id="e71c9-154">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="e71c9-155">Для собраний, не являющихся каналами, все участники собрания, кроме внешних пользователей, будут автоматически получать общую ссылку.</span><span class="sxs-lookup"><span data-stu-id="e71c9-155">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="e71c9-156">Внешние пользователи должны быть явно добавлены в общий список организатором собрания или пользователем, который запустил запись собрания.</span><span class="sxs-lookup"><span data-stu-id="e71c9-156">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="e71c9-157">Для собраний по каналам разрешения наследуются из списка владельцы и участники в канале.</span><span class="sxs-lookup"><span data-stu-id="e71c9-157">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="e71c9-158">**Как управлять записями?**</span><span class="sxs-lookup"><span data-stu-id="e71c9-158">**How can I manage transcripts?**</span></span>

<span data-ttu-id="e71c9-159">Пользователи, не прошедшие в этом предварительном просмотре, не смогут использовать субтитры, доступные в записях собрания Teams, которые перенесены в OneDrive и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e71c9-159">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="e71c9-160">Мы работаем над добавлением субтитров, начинающих с субтитров на английском языке и записями о собраниях в октябре 2020.</span><span class="sxs-lookup"><span data-stu-id="e71c9-160">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="e71c9-161">Закрытые субтитры будут доступны в записях собраний Teams для пользователей, которые не участвуют в разрешении на запись, как описано в [облачных записях Teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="e71c9-161">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="e71c9-162">С помощью подписей вы создадите инклюзивное содержимое для просмотра всех возможностей.</span><span class="sxs-lookup"><span data-stu-id="e71c9-162">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="e71c9-163">Как владелец, вы можете скрыть субтитры, хотя он по-прежнему будет доступен в Teams, если вы не удалите их из Teams.</span><span class="sxs-lookup"><span data-stu-id="e71c9-163">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="e71c9-164">Узнайте [, как включить или отключить записи собраний](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="e71c9-164">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="e71c9-165">Скрытые субтитры поддерживаются для записей собраний Teams в течение 60 дней с момента регистрации собрания.</span><span class="sxs-lookup"><span data-stu-id="e71c9-165">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="e71c9-166">**Как будет влиять квота хранилища**</span><span class="sxs-lookup"><span data-stu-id="e71c9-166">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="e71c9-167">Файлы записываются в OneDrive для бизнеса и SharePoint с помощью группового собрания, которые включены в вашу квоту для этих служб.</span><span class="sxs-lookup"><span data-stu-id="e71c9-167">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="e71c9-168">Ознакомьтесь с [квотой SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) и [квота OneDrive для бизнеса] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="e71c9-168">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="e71c9-169">**Как можно воспроизвести запись собрания группы?**</span><span class="sxs-lookup"><span data-stu-id="e71c9-169">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="e71c9-170">Видео будет воспроизводиться на видеопроигрывателе OneDrive для бизнеса или SharePoint в зависимости от того, где вы хотите получить доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="e71c9-170">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>
