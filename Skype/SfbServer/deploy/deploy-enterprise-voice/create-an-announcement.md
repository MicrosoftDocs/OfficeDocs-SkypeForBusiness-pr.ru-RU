---
title: Создание и удаление оповещения в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
description: Создание и удаление объявлений для объявлений приложения в Скайп Business Server корпоративной голосовой связи. От этих действий зависит способ обработки вызовов на неназначенные номера.
ms.openlocfilehash: 3270daf8d157be0b6307f4112081cb331f84d69f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019512"
---
# <a name="create-or-delete-an-announcement-in-skype-for-business-server"></a>Создание и удаление оповещения в Скайп для Business Server
 
Создание и удаление объявлений для объявлений приложения в Скайп Business Server корпоративной голосовой связи. От этих действий зависит способ обработки вызовов на неназначенные номера.
  
При настройке объявлений в действительности вы настраиваете то, как будут обрабатываться звонки на неназначенные номера. Можно воспроизводить подсказку — аудиофайл или TTS-файл синтезированной речи, или можно просто перевести вызов на указанный пункт назначения без подсказки.
  
Для создания объявлений сначала нужно определить таблицу неназначенных номеров. Данную процедуру необходимо выполнить для всех объявлений, использующих звуковую подсказку, подсказку TTS, или объявлений, не использующих подсказку.
  
В этом разделе описывается импорт и создание оповещений. Для получения дополнительных сведений о назначении объявлений в таблице неназначенных номеров видеть [настройки таблицы неназначенных номер](http://technet.microsoft.com/library/eaa01986-e92f-4328-acf6-4e46c4306a04.aspx).
  
## <a name="create-a-new-announcement-for-unassigned-numbers"></a>Создание нового объявления для неназначенных номеров

Чтобы создать новое оповещение, выполните следующие действия. 
  
1. Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.
    
2. Для звуковых приглашений выполните командлет **Import-CsAnnouncementFile** , чтобы импортировать содержимое звукового файла в хранилище файлов.
    
3. Выполните командлет **New-CsAnnouncement** , чтобы создать оповещение. С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.
    
    > [!TIP]
    > Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения. 
  
4. Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.
    
### <a name="to-create-a-new-announcement"></a>Создание нового оповещения

1. Если планируется использовать звуковые приглашения, создайте звуковой файл.
    
2. Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.
    
3. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
4. Для звуковых приглашений выполните следующую команду:
    
   ```
   Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]
   ```

5. Выполните следующую команду:
    
   ```
   New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
   ```

    Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).
    
    Например, чтобы указать звуковое приглашение, выполните следующую команду:
    
   ```
   $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
   Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
   ```

    Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:
    
   ```
   New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
   ```

  Дополнительные сведения об этих командлетах, а для просмотра списка кодов языков для использования в параметре **TextToSpeechPrompt** в разделе [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps).
    
## <a name="delete-an-announcement-for-unassigned-numbers"></a>Удаление объявления для неназначенных номеров

### <a name="to-delete-an-announcement"></a>Порядок удаления оповещения

1. Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Получите список всех оповещений, используемых в организации. Выполните в командной строке следующую команду:
     
   ```
   Get-CsAnnouncement
   ```

4. В полученном списке найдите оповещение, которое требуется удалить, и скопируйте его идентификатор GUID. Затем выполните в командной строке следующую команду:
    
   ```
   Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
   ```

    Например:
    
   ```
   Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
   ```

    > [!NOTE]
    > Для получения дополнительных сведений о Дополнительные параметры просмотра [Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps) и [Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps). 
  
## <a name="see-also"></a>См. также

[Создание и удаление оповещения в Скайп для Business Server](create-an-announcement.md)

[Import-CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/import-csannouncementfile?view=skype-ps)
  
[Новый CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/new-csannouncement?view=skype-ps)
  
[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/remove-csannouncement?view=skype-ps)
  
[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/get-csannouncement?view=skype-ps)

