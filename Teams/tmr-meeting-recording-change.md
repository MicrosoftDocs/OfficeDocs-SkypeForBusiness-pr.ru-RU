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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444235"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="4509d-103">Использование OneDrive для бизнеса и SharePoint или Stream для записей собраний</span><span class="sxs-lookup"><span data-stu-id="4509d-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="4509d-104">Поэтапный подход к изменению с помощью Microsoft Stream для OneDrive для бизнеса и Microsoft SharePoint для записей собраний.</span><span class="sxs-lookup"><span data-stu-id="4509d-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>

|||
|---|-----------------|
|<span data-ttu-id="4509d-105">Дата</span><span class="sxs-lookup"><span data-stu-id="4509d-105">Date</span></span>|<span data-ttu-id="4509d-106">Событие</span><span class="sxs-lookup"><span data-stu-id="4509d-106">Event</span></span>|
|<span data-ttu-id="4509d-107">Ранний квартал CY20</span><span class="sxs-lookup"><span data-stu-id="4509d-107">Early Q4 CY20</span></span>|<span data-ttu-id="4509d-108">**Запись собрания Teams в OneDrive для бизнеса и SharePoint, доступных для использования или отказа от нее.**</span><span class="sxs-lookup"><span data-stu-id="4509d-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="4509d-109">Администраторы клиентов могут отказаться от использования OneDrive для бизнеса и SharePoint, указав политику Teams в PowerShell</span><span class="sxs-lookup"><span data-stu-id="4509d-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="4509d-110">MID квартал CY20</span><span class="sxs-lookup"><span data-stu-id="4509d-110">Mid Q4 CY20</span></span>|<span data-ttu-id="4509d-111">**Запись собрания Teams в OneDrive для бизнеса и SharePoint по умолчанию настроены для клиентов, которые не отказывается**</span><span class="sxs-lookup"><span data-stu-id="4509d-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="4509d-112">Это рекомендуемый путь для большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="4509d-112">This is the  recommended path for most customers</span></span>|
<span data-ttu-id="4509d-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="4509d-113">Q1 CY21</span></span>|<span data-ttu-id="4509d-114">**Сохранение записи собрания группы в классическом потоке больше не разрешено**</span><span class="sxs-lookup"><span data-stu-id="4509d-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="4509d-115">Все клиенты будут сохранять запись собрания группы в OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="4509d-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|
|||

<span data-ttu-id="4509d-116">В Microsoft Teams имеется новый способ сохранения записей собраний.</span><span class="sxs-lookup"><span data-stu-id="4509d-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="4509d-117">В качестве первого этапа перехода из классической версии Microsoft Stream в [новый поток](https://docs.microsoft.com/stream/streamnew/new-stream)этот метод сохраняет записи в Microsoft OneDrive и SharePoint в Microsoft 365 и предоставляет множество преимуществ.</span><span class="sxs-lookup"><span data-stu-id="4509d-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="4509d-118">С помощью OneDrive для бизнеса и SharePoint для хранения записей доступны следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="4509d-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="4509d-119">Политики хранения для записи собрания в Teams (TMR) (S + C, метки автохранения)</span><span class="sxs-lookup"><span data-stu-id="4509d-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="4509d-120">Преимущества из OneDrive для бизнеса и информационной системы SharePoint</span><span class="sxs-lookup"><span data-stu-id="4509d-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="4509d-121">Простота настройки разрешений и общего доступа</span><span class="sxs-lookup"><span data-stu-id="4509d-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="4509d-122">Предоставление общего доступа к записям для гостей (внешних пользователей) с явной общим доступом</span><span class="sxs-lookup"><span data-stu-id="4509d-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="4509d-123">Поток запросов на доступ</span><span class="sxs-lookup"><span data-stu-id="4509d-123">Request access flow</span></span>
- <span data-ttu-id="4509d-124">Предоставление общих ссылок в OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="4509d-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="4509d-125">Повышенная квота</span><span class="sxs-lookup"><span data-stu-id="4509d-125">Increased quota</span></span>
- <span data-ttu-id="4509d-126">Записи собраний доступны быстрее</span><span class="sxs-lookup"><span data-stu-id="4509d-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="4509d-127">**Переход** на поддержку локального клиента</span><span class="sxs-lookup"><span data-stu-id="4509d-127">**Go local** tenant support</span></span>
- <span data-ttu-id="4509d-128">Поддержка нескольких географических регионов — записи хранятся в определенном пользователем регионе.</span><span class="sxs-lookup"><span data-stu-id="4509d-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="4509d-129">Подведите поддержку ключа (BYOK)</span><span class="sxs-lookup"><span data-stu-id="4509d-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="4509d-130">Улучшенное качество транскрипции и атрибуты динамиков</span><span class="sxs-lookup"><span data-stu-id="4509d-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="4509d-131">Есть ряд ограничений, которые следует принимать во что:</span><span class="sxs-lookup"><span data-stu-id="4509d-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="4509d-132">Будут закрыты субтитры и записи с английским языком.</span><span class="sxs-lookup"><span data-stu-id="4509d-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="4509d-133">Вы не сможете искать записи и их содержимое.</span><span class="sxs-lookup"><span data-stu-id="4509d-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="4509d-134">Вы не сможете изменять транскрипции, но сможете включать и отключать субтитры.</span><span class="sxs-lookup"><span data-stu-id="4509d-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="4509d-135">Вы можете управлять тем, кому предоставлен доступ к записи, но вы не сможете блокировать пользователей с общим доступом для загрузки записи.</span><span class="sxs-lookup"><span data-stu-id="4509d-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="4509d-136">Вы не получите сообщение по электронной почте, когда запись завершит сохранение, но запись появится в разделе чата собрания после ее завершения.</span><span class="sxs-lookup"><span data-stu-id="4509d-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="4509d-137">Это происходит гораздо быстрее, чем в потоке ранее</span><span class="sxs-lookup"><span data-stu-id="4509d-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="4509d-138">Дополнительные сведения смотрите в записях собрания.</span><span class="sxs-lookup"><span data-stu-id="4509d-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="4509d-139">Настройка параметров записи собраний для OneDrive для бизнеса и SharePoint</span><span class="sxs-lookup"><span data-stu-id="4509d-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="4509d-140">Установите консоль администрирования PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4509d-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="4509d-141">а)</span><span class="sxs-lookup"><span data-stu-id="4509d-141">a.</span></span> <span data-ttu-id="4509d-142">Скачайте [Skype для бизнеса Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4509d-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="4509d-143">б)</span><span class="sxs-lookup"><span data-stu-id="4509d-143">b.</span></span> <span data-ttu-id="4509d-144">Следуйте инструкциям по установке.</span><span class="sxs-lookup"><span data-stu-id="4509d-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="4509d-145">в.</span><span class="sxs-lookup"><span data-stu-id="4509d-145">c.</span></span> <span data-ttu-id="4509d-146">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="4509d-146">Restart your machine.</span></span>

2. <span data-ttu-id="4509d-147">Запуск PowerShell с правами администратора</span><span class="sxs-lookup"><span data-stu-id="4509d-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="4509d-148">Импортируйте соединитель SkypeOnline и войдите в систему как администратор Teams.</span><span class="sxs-lookup"><span data-stu-id="4509d-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="4509d-149">С помощью [Set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) можно настроить политику собрания Teams на переход из хранилища потоков в ODSP.</span><span class="sxs-lookup"><span data-stu-id="4509d-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="4509d-150">Отказ от OneDrive для бизнеса и SharePoint для продолжения использования потока</span><span class="sxs-lookup"><span data-stu-id="4509d-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="4509d-151">Даже если политика сообщает, что она настроена на **поток**, она может быть не настроена.</span><span class="sxs-lookup"><span data-stu-id="4509d-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="4509d-152">Как правило, если политика не задана, по умолчанию используется значение **Stream**.</span><span class="sxs-lookup"><span data-stu-id="4509d-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="4509d-153">Тем не менее, если вы хотите отказаться от использования SharePoint или OneDrive с новым изменением, необходимо сбросить политику в **Stream** , чтобы убедиться, что она используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4509d-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="4509d-154">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="4509d-154">Frequently asked questions</span></span>

<span data-ttu-id="4509d-155">**Где будет храниться запись собрания?**</span><span class="sxs-lookup"><span data-stu-id="4509d-155">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="4509d-156">Для собраний, не являющихся каналами, запись сохраняется в папке с **именем "** Records", которая находится на верхнем уровне OneDrive, принадлежащем пользователю, который запустил запись собрания.</span><span class="sxs-lookup"><span data-stu-id="4509d-156">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="4509d-157">Образом</span><span class="sxs-lookup"><span data-stu-id="4509d-157">Example:</span></span>

  <span data-ttu-id="4509d-158"><i>OneDrive для бизнеса</i> / с записью **Записи**</span><span class="sxs-lookup"><span data-stu-id="4509d-158"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="4509d-159">Для собраний по каналам запись сохраняется в библиотеке документации сайта Teams в папке с именем Records ( **записи**).</span><span class="sxs-lookup"><span data-stu-id="4509d-159">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="4509d-160">Образом</span><span class="sxs-lookup"><span data-stu-id="4509d-160">Example:</span></span>

  <span data-ttu-id="4509d-161"><i>Имя группы: название канала</i> / **Документы** / **Записи**</span><span class="sxs-lookup"><span data-stu-id="4509d-161"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="4509d-162">**Как обрабатывать записи от бывших сотрудников?**</span><span class="sxs-lookup"><span data-stu-id="4509d-162">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="4509d-163">Так как видеоролики похожи на любые другие файлы в OneDrive и SharePoint, обработка владельца и хранение после выхода сотрудника будет пройдет за обычный [процесс OneDrive и SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span><span class="sxs-lookup"><span data-stu-id="4509d-163">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="4509d-164">**У кого есть разрешения на просмотр записи собрания?**</span><span class="sxs-lookup"><span data-stu-id="4509d-164">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="4509d-165">Для собраний, не являющихся каналами, все участники собрания, кроме внешних пользователей, будут автоматически получать общую ссылку.</span><span class="sxs-lookup"><span data-stu-id="4509d-165">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="4509d-166">Внешние пользователи должны быть явно добавлены в общий список организатором собрания или пользователем, который запустил запись собрания.</span><span class="sxs-lookup"><span data-stu-id="4509d-166">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="4509d-167">Для собраний по каналам разрешения наследуются из списка владельцы и участники в канале.</span><span class="sxs-lookup"><span data-stu-id="4509d-167">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="4509d-168">**Как управлять записями?**</span><span class="sxs-lookup"><span data-stu-id="4509d-168">**How can I manage transcripts?**</span></span>

<span data-ttu-id="4509d-169">Пользователи, не прошедшие в этом предварительном просмотре, не смогут использовать субтитры, доступные в записях собрания Teams, которые перенесены в OneDrive и SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4509d-169">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="4509d-170">Мы работаем над добавлением субтитров, начинающих с субтитров на английском языке и записями о собраниях в октябре 2020.</span><span class="sxs-lookup"><span data-stu-id="4509d-170">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="4509d-171">Закрытые субтитры будут доступны в записях собраний Teams для пользователей, которые не участвуют в разрешении на запись, как описано в [облачных записях Teams](cloud-recording.md) .</span><span class="sxs-lookup"><span data-stu-id="4509d-171">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="4509d-172">С помощью подписей вы создадите инклюзивное содержимое для просмотра всех возможностей.</span><span class="sxs-lookup"><span data-stu-id="4509d-172">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="4509d-173">Как владелец, вы можете скрыть субтитры, хотя он по-прежнему будет доступен в Teams, если вы не удалите их из Teams.</span><span class="sxs-lookup"><span data-stu-id="4509d-173">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="4509d-174">Узнайте [, как включить или отключить записи собраний](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization) .</span><span class="sxs-lookup"><span data-stu-id="4509d-174">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="4509d-175">Скрытые субтитры поддерживаются для записей собраний Teams в течение 60 дней с момента регистрации собрания.</span><span class="sxs-lookup"><span data-stu-id="4509d-175">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="4509d-176">**Как будет влиять квота хранилища**</span><span class="sxs-lookup"><span data-stu-id="4509d-176">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="4509d-177">Файлы записываются в OneDrive для бизнеса и SharePoint с помощью группового собрания, которые включены в вашу квоту для этих служб.</span><span class="sxs-lookup"><span data-stu-id="4509d-177">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="4509d-178">Ознакомьтесь с [квотой SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) и [квота OneDrive для бизнеса] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="4509d-178">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="4509d-179">**Как можно воспроизвести запись собрания группы?**</span><span class="sxs-lookup"><span data-stu-id="4509d-179">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="4509d-180">Видео будет воспроизводиться на видеопроигрывателе OneDrive для бизнеса или SharePoint в зависимости от того, где вы хотите получить доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="4509d-180">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="4509d-181">**Если вы планируете использовать устаревшее Добавление в поток, видеоролики будут оставаться как есть и как долго?**</span><span class="sxs-lookup"><span data-stu-id="4509d-181">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="4509d-182">Поток как платформа не будет считаться устаревшим в ближайшем будущем.</span><span class="sxs-lookup"><span data-stu-id="4509d-182">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="4509d-183">Видеоролики, которые в настоящее время проживают в потоке, будут оставаться на связи, пока не начнется перенос.</span><span class="sxs-lookup"><span data-stu-id="4509d-183">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="4509d-184">После миграции эти видеоролики также будут перенесены в ODSP.</span><span class="sxs-lookup"><span data-stu-id="4509d-184">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="4509d-185">Для получения дополнительных сведений ознакомьтесь с [этой страницей](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="4509d-185">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
