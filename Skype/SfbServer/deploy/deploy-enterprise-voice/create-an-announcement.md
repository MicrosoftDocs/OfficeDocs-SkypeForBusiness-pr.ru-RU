---
title: Создание и удаление объявлений в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Создание и удаление объявлений для приложения объявления в Skype для бизнеса Server Enterprise. От этих действий зависит способ обработки вызовов на неназначенные номера.
ms.openlocfilehash: 7cde8c268c66d19e6806a4b6c3e585a7271ef2ff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767962"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="e66ab-104">Создание и удаление объявлений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e66ab-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="e66ab-105">Создание и удаление объявлений для приложения объявления в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e66ab-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="e66ab-106">От этих действий зависит способ обработки вызовов на неназначенные номера.</span><span class="sxs-lookup"><span data-stu-id="e66ab-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="e66ab-p103">При настройке объявлений в действительности вы настраиваете то, как будут обрабатываться звонки на неназначенные номера. Можно воспроизводить подсказку — аудиофайл или TTS-файл синтезированной речи, или можно просто перевести вызов на указанный пункт назначения без подсказки.</span><span class="sxs-lookup"><span data-stu-id="e66ab-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="e66ab-p104">Для создания объявлений сначала нужно определить таблицу неназначенных номеров. Данную процедуру необходимо выполнить для всех объявлений, использующих звуковую подсказку, подсказку TTS, или объявлений, не использующих подсказку.</span><span class="sxs-lookup"><span data-stu-id="e66ab-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="e66ab-p105">В этом разделе описывается импорт и создание оповещений. Дополнительные сведения о назначении оповещений в таблице неназначенных номеров см. в разделе [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="e66ab-p105">This topic describes how to import and create announcements. For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="e66ab-113">Создание нового объявления для неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="e66ab-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="e66ab-114">Чтобы создать новое оповещение, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e66ab-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="e66ab-115">Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.</span><span class="sxs-lookup"><span data-stu-id="e66ab-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="e66ab-116">Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.</span><span class="sxs-lookup"><span data-stu-id="e66ab-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="e66ab-117">Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**.</span><span class="sxs-lookup"><span data-stu-id="e66ab-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="e66ab-118">С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.</span><span class="sxs-lookup"><span data-stu-id="e66ab-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="e66ab-119">Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.</span><span class="sxs-lookup"><span data-stu-id="e66ab-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="e66ab-120">Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="e66ab-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="e66ab-121">Создание нового оповещения</span><span class="sxs-lookup"><span data-stu-id="e66ab-121">To create a new announcement</span></span>

1. <span data-ttu-id="e66ab-122">Если планируется использовать звуковые приглашения, создайте звуковой файл.</span><span class="sxs-lookup"><span data-stu-id="e66ab-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="e66ab-123">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="e66ab-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="e66ab-124">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e66ab-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="e66ab-125">Для звуковых приглашений выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e66ab-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="e66ab-126">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e66ab-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="e66ab-p107">Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="e66ab-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="e66ab-129">Например, чтобы указать звуковое приглашение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e66ab-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="e66ab-130">Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:</span><span class="sxs-lookup"><span data-stu-id="e66ab-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="e66ab-131">Подробнее об этих командлетах и о том, как просмотреть список кодов языков, используемых в параметре **тексттоспичпромпт** , можно найти в статьях [New-ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e66ab-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="e66ab-132">Удаление объявления для неназначенных номеров</span><span class="sxs-lookup"><span data-stu-id="e66ab-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="e66ab-133">Порядок удаления оповещения</span><span class="sxs-lookup"><span data-stu-id="e66ab-133">To delete an announcement</span></span>

1. <span data-ttu-id="e66ab-134">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="e66ab-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="e66ab-135">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e66ab-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="e66ab-p108">Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e66ab-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="e66ab-p109">В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e66ab-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="e66ab-140">Например:</span><span class="sxs-lookup"><span data-stu-id="e66ab-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="e66ab-141">Подробнее о дополнительных параметрах можно узнать в [статьях Get-ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) и [Remove-ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e66ab-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="e66ab-142">См. также</span><span class="sxs-lookup"><span data-stu-id="e66ab-142">See also</span></span>

[<span data-ttu-id="e66ab-143">Создание и удаление объявлений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e66ab-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="e66ab-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="e66ab-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="e66ab-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="e66ab-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="e66ab-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="e66ab-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="e66ab-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="e66ab-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

