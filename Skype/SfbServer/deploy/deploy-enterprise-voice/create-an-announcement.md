---
title: Создание или удаление объявления в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Создание или удаление объявлений для приложения "Объявления" в Skype для бизнеса Server Корпоративная голосовая связь. Это влияет на то, как обрабатываются вызовы на ненаписаные номера.
ms.openlocfilehash: 9f2b4fcda8e98d4b939b6b443da875dbe153546c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824909"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a><span data-ttu-id="fd09d-104">Создание или удаление объявления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fd09d-104">Create or delete an announcement in Skype for Business Server</span></span>

<span data-ttu-id="fd09d-105">Создание или удаление объявлений для приложения "Объявления" в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="fd09d-105">Create or delete announcements for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="fd09d-106">Это влияет на то, как обрабатываются вызовы на ненаписаные номера.</span><span class="sxs-lookup"><span data-stu-id="fd09d-106">This affects how calls to unassigned numbers are handled.</span></span>

<span data-ttu-id="fd09d-p103">При настройке объявлений в действительности вы настраиваете то, как будут обрабатываться звонки на неназначенные номера. Можно воспроизводить подсказку — аудиофайл или TTS-файл синтезированной речи, или можно просто перевести вызов на указанный пункт назначения без подсказки.</span><span class="sxs-lookup"><span data-stu-id="fd09d-p103">When you configure announcements, you are really configuring how you want calls to unassigned numbers to be handled. You can play a prompt, which can be an audio file or a text-to-speech (TTS) file, or you can just transfer the call to a specified destination without playing a prompt.</span></span>

<span data-ttu-id="fd09d-p104">Для создания объявлений сначала нужно определить таблицу неназначенных номеров. Данную процедуру необходимо выполнить для всех объявлений, использующих звуковую подсказку, подсказку TTS, или объявлений, не использующих подсказку.</span><span class="sxs-lookup"><span data-stu-id="fd09d-p104">You need to create announcements before you define the unassigned number table. You need to perform this step for all announcements that use an audio prompt, a TTS prompt, or no prompt.</span></span>

<span data-ttu-id="fd09d-111">В этом разделе описывается импорт и создание оповещений.</span><span class="sxs-lookup"><span data-stu-id="fd09d-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="fd09d-112">Дополнительные сведения о назначении оповещений в таблице неназначенных номеров см. в разделе [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd09d-112">For details about assigning announcements in the unassigned number table, see [Configure the Unassigned Number Table](https://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).</span></span>

## <a name="create-a-new-announcement-for-unassigned-numbers"></a><span data-ttu-id="fd09d-113">Создание нового объявления для ненаписаных номеров</span><span class="sxs-lookup"><span data-stu-id="fd09d-113">Create a new announcement for unassigned numbers</span></span>

<span data-ttu-id="fd09d-114">Чтобы создать новое оповещение, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fd09d-114">To create a new announcement, you need to perform the following steps:</span></span>

1. <span data-ttu-id="fd09d-115">Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.</span><span class="sxs-lookup"><span data-stu-id="fd09d-115">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2. <span data-ttu-id="fd09d-116">Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.</span><span class="sxs-lookup"><span data-stu-id="fd09d-116">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3. <span data-ttu-id="fd09d-117">Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**.</span><span class="sxs-lookup"><span data-stu-id="fd09d-117">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="fd09d-118">С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.</span><span class="sxs-lookup"><span data-stu-id="fd09d-118">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>

    > [!TIP]
    > <span data-ttu-id="fd09d-119">Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.</span><span class="sxs-lookup"><span data-stu-id="fd09d-119">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

4. <span data-ttu-id="fd09d-120">Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="fd09d-120">Assign the new announcement to a number range in the unassigned number table.</span></span>

### <a name="to-create-a-new-announcement"></a><span data-ttu-id="fd09d-121">Создание нового оповещения</span><span class="sxs-lookup"><span data-stu-id="fd09d-121">To create a new announcement</span></span>

1. <span data-ttu-id="fd09d-122">Если планируется использовать звуковые приглашения, создайте звуковой файл.</span><span class="sxs-lookup"><span data-stu-id="fd09d-122">For audio prompts, create the audio file.</span></span>

2. <span data-ttu-id="fd09d-123">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**</span><span class="sxs-lookup"><span data-stu-id="fd09d-123">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

3. <span data-ttu-id="fd09d-124">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="fd09d-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

4. <span data-ttu-id="fd09d-125">Для звуковых приглашений выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd09d-125">For audio prompts, run:</span></span>

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. <span data-ttu-id="fd09d-126">Запустите:</span><span class="sxs-lookup"><span data-stu-id="fd09d-126">Run:</span></span>

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    <span data-ttu-id="fd09d-p107">Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="fd09d-p107">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>

    <span data-ttu-id="fd09d-129">Например, чтобы указать звуковое приглашение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd09d-129">For example, to specify an audio prompt:</span></span>

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    <span data-ttu-id="fd09d-130">Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:</span><span class="sxs-lookup"><span data-stu-id="fd09d-130">For example, to specify a TTS prompt:</span></span>

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   <span data-ttu-id="fd09d-131">Дополнительные подробные данные об этих cmdlets и список кодов языка для использования в **параметре TextToSpeechPrompt** см. в [new-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="fd09d-131">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).</span></span>

## <a name="delete-an-announcement-for-unassigned-numbers"></a><span data-ttu-id="fd09d-132">Удаление объявления для ненаписаных номеров</span><span class="sxs-lookup"><span data-stu-id="fd09d-132">Delete an announcement for unassigned numbers</span></span>

### <a name="to-delete-an-announcement"></a><span data-ttu-id="fd09d-133">Порядок удаления оповещения</span><span class="sxs-lookup"><span data-stu-id="fd09d-133">To delete an announcement</span></span>

1. <span data-ttu-id="fd09d-134">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**</span><span class="sxs-lookup"><span data-stu-id="fd09d-134">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="fd09d-135">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="fd09d-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="fd09d-p108">Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd09d-p108">List all the announcements in your organization. At the command line, run:</span></span>

   ```powershell
   Get-CsAnnouncement
   ```

4. <span data-ttu-id="fd09d-p109">В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd09d-p109">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    <span data-ttu-id="fd09d-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="fd09d-140">For example:</span></span>

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > <span data-ttu-id="fd09d-141">Дополнительные сведения о дополнительных параметрах см. в дополнительных сведениях о [get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) и [Remove-CsAnnouncement.](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="fd09d-141">For details about more options, see [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) and [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd09d-142">См. также</span><span class="sxs-lookup"><span data-stu-id="fd09d-142">See also</span></span>

[<span data-ttu-id="fd09d-143">Создание или удаление объявления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fd09d-143">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md)

[<span data-ttu-id="fd09d-144">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="fd09d-144">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[<span data-ttu-id="fd09d-145">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="fd09d-145">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)

[<span data-ttu-id="fd09d-146">Remove-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="fd09d-146">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)

[<span data-ttu-id="fd09d-147">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="fd09d-147">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

