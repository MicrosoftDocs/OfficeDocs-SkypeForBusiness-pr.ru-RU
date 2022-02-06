---
title: Создание или удаление объявления в Skype для бизнеса Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Создание или удаление объявлений для приложения Объявления в Skype для бизнеса Server Корпоративная голосовая связь. Это влияет на обработку вызовов на ненанаписаные номера.
---

# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Создание или удаление объявления в Skype для бизнеса Server

Создание или удаление объявлений для приложения Объявления в Skype для бизнеса Server Корпоративная голосовая связь. Это влияет на обработку вызовов на ненанаписаные номера.

При настройке объявлений в действительности вы настраиваете то, как будут обрабатываться звонки на неназначенные номера. Можно воспроизводить подсказку — аудиофайл или TTS-файл синтезированной речи, или можно просто перевести вызов на указанный пункт назначения без подсказки.

Для создания объявлений сначала нужно определить таблицу неназначенных номеров. Данную процедуру необходимо выполнить для всех объявлений, использующих звуковую подсказку, подсказку TTS, или объявлений, не использующих подсказку.

В этом разделе описывается импорт и создание оповещений. Дополнительные сведения о назначении оповещений в таблице неназначенных номеров см. в разделе [Configure the Unassigned Number Table](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-unassigned-number-table).

## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Создание нового объявления для ненаписаных номеров

Чтобы создать новое оповещение, выполните следующие действия.

1. Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.

2. Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.

3. Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**. С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.

    > [!TIP]
    > Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.

4. Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.

### <a name="to-create-a-new-announcement"></a>Создание нового оповещения

1. Если планируется использовать звуковые приглашения, создайте звуковой файл.

2. Войдите на компьютер, на котором Skype для бизнеса Server в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**

3. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.

4. Для звуковых приглашений выполните следующую команду:

   ```powershell
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Запуск:

   ```powershell
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).

    Например, чтобы указать звуковое приглашение, выполните следующую команду:

   ```powershell
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:

   ```powershell
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

   Дополнительные подробности об этих комлетах и списке языковых кодов, которые необходимо использовать в параметре **TextToSpeechPrompt** , см. в рублях [New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps).

## <a name="delete-an-announcement-for-unassigned-numbers"></a>Удаление объявления для ненаписаных номеров

### <a name="to-delete-an-announcement"></a>Порядок удаления оповещения

1. Войдите на компьютер, на котором Skype для бизнеса Server в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**

2. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.

3. Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:

   ```powershell
   Get-CsAnnouncement
   ```

4. В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:

   ```powershell
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
   ```

    Пример:

   ```powershell
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Дополнительные сведения см. в [дополнительных параметрах Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps) и [Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps).

## <a name="see-also"></a>См. также

[Создание или удаление объявления в Skype для бизнеса Server](create-an-announcement.md)

[Import-CsAnnouncementFile](/powershell/module/skype/import-csannouncementfile?view=skype-ps)

[New-CsAnnouncement](/powershell/module/skype/new-csannouncement?view=skype-ps)

[Remove-CsAnnouncement](/powershell/module/skype/remove-csannouncement?view=skype-ps)

[Get-CsAnnouncement](/powershell/module/skype/get-csannouncement?view=skype-ps)