---
title: Создание и удаление оповещения в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Создание и удаление объявлений для объявлений приложения в Скайп Business Server корпоративной голосовой связи. От этих действий зависит способ обработки вызовов на неназначенные номера.
ms.openlocfilehash: 79298dbe415071d9d773375f524dff95516cc4fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893009"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="992b2-104">Создание и удаление оповещения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="992b2-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="992b2-105">Создание и удаление объявлений для объявлений приложения в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="992b2-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="992b2-106">От этих действий зависит способ обработки вызовов на неназначенные номера.</span><span class="sxs-lookup"><span data-stu-id="992b2-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="992b2-p103">При настройке объявлений в действительности вы настраиваете то, как будут обрабатываться звонки на неназначенные номера. Можно воспроизводить подсказку — аудиофайл или TTS-файл синтезированной речи, или можно просто перевести вызов на указанный пункт назначения без подсказки.</span><span class="sxs-lookup"><span data-stu-id="992b2-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="992b2-p104">Для создания объявлений сначала нужно определить таблицу неназначенных номеров. Данную процедуру необходимо выполнить для всех объявлений, использующих звуковую подсказку, подсказку TTS, или объявлений, не использующих подсказку.</span><span class="sxs-lookup"><span data-stu-id="992b2-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="992b2-p105">В этом разделе описывается импорт и создание оповещений. Дополнительные сведения о назначении оповещений в таблице неназначенных номеров см. в разделе [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="992b2-p105">This topic describes how to import and create announcements. For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="992b2-113">Создание нового объявления для неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="992b2-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="992b2-114">Чтобы создать новое оповещение, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="992b2-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="992b2-115">Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.</span><span class="sxs-lookup"><span data-stu-id="992b2-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="992b2-116">Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.</span><span class="sxs-lookup"><span data-stu-id="992b2-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="992b2-117">Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**.</span><span class="sxs-lookup"><span data-stu-id="992b2-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="992b2-118">С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.</span><span class="sxs-lookup"><span data-stu-id="992b2-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="992b2-119">Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.</span><span class="sxs-lookup"><span data-stu-id="992b2-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="992b2-120">Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="992b2-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="992b2-121">Создание нового оповещения</span><span class="sxs-lookup"><span data-stu-id="992b2-121">To create a new announcement</span></span>

1. <span data-ttu-id="992b2-122">Если планируется использовать звуковые приглашения, создайте звуковой файл.</span><span class="sxs-lookup"><span data-stu-id="992b2-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="992b2-123">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="992b2-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="992b2-124">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="992b2-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="992b2-125">Для звуковых приглашений выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="992b2-125">For audio prompts, run:</span></span>

   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="992b2-126">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="992b2-126">Run:</span></span>

   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="992b2-p107">Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="992b2-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="992b2-129">Например, чтобы указать звуковое приглашение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="992b2-129">For example, to specify an audio prompt:</span></span>

   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="992b2-130">Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:</span><span class="sxs-lookup"><span data-stu-id="992b2-130">For example, to specify a TTS prompt:</span></span>

   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="992b2-131">Дополнительные сведения об этих командлетах, а для просмотра списка кодов языков для использования в параметре **TextToSpeechPrompt** в разделе [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="992b2-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="992b2-132">Удаление объявления для неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="992b2-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="992b2-133">Порядок удаления оповещения</span><span class="sxs-lookup"><span data-stu-id="992b2-133">To delete an announcement</span></span>

1. <span data-ttu-id="992b2-134">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="992b2-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="992b2-135">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="992b2-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="992b2-p108">Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="992b2-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="992b2-p109">В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="992b2-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="992b2-140">Например:</span><span class="sxs-lookup"><span data-stu-id="992b2-140">For example:</span></span>

   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="992b2-141">Для получения дополнительных сведений о Дополнительные параметры просмотра [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) и [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="992b2-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="992b2-142">См. также</span><span class="sxs-lookup"><span data-stu-id="992b2-142">See also</span></span>

[<span data-ttu-id="992b2-143">Создание и удаление оповещения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="992b2-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="992b2-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="992b2-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="992b2-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="992b2-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="992b2-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="992b2-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="992b2-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="992b2-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

