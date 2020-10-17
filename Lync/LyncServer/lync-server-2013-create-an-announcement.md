---
title: 'Lync Server 2013: создание извещения'
description: 'Lync Server 2013: создание извещения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc064686ef86e04b89951fcaac7abbec28b7257c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562395"
---
# <a name="create-an-announcement-in-lync-server-2013"></a>Создание извещения в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Чтобы создать новое оповещение, выполните следующие действия.

1.  Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.

2.  Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.

3.  Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**. С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.
    
    <div>
    

    > [!TIP]  
    > Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.

    
    </div>

4.  Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.

В этом разделе описывается импорт и создание оповещений. Подробнее о назначении объявлений в таблице неназначенных номеров можно узнать в статье [Настройка таблицы неназначенных номеров в Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).

<div>

## <a name="to-create-a-new-announcement"></a>Создание нового оповещения

1.  Если планируется использовать звуковые приглашения, создайте звуковой файл.

2.  Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  Для звуковых приглашений выполните следующую команду:
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  Выполняем
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).
    
    Например, чтобы указать звуковое приглашение, выполните следующую команду:
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    Для получения дополнительных сведений об этих командлетах и просмотра списка языковых кодов, используемых в параметре **тексттоспичпромпт** , ознакомьтесь со статьей [New – ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).

</div>

<div>

## <a name="see-also"></a>См. также


[Import — CsAnnouncementFile](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[New — Ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[Настройка таблицы неназначенных номеров в Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

