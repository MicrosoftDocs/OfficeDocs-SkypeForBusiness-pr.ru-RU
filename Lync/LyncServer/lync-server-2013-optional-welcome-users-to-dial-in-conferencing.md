---
title: 'Lync Server 2013: приветствие пользователей в конференции с телефонным подключением (необязательно)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Welcome users to dial-in conferencing
ms:assetid: caa4fd61-f506-4c09-bb5b-1aa260d7a720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398846(v=OCS.15)
ms:contentKeyID: 48185443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27abf5da520f1c5befd3a477783bc3f9ae67e1b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>Приветствие пользователей в конференции с телефонным подключением Lync Server 2013 (необязательно)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-30_

После настройки конференц-связи с телефонным подключением и проверки правильности ее функционирования вы должны задать начальные личные коды (PIN) для пользователей и уведомлять пользователей о доступности функции, включая вводные инструкции, такие в качестве первоначального PIN-кода и ссылки на веб-страницу параметров конференции с телефонным подключением. Этот шаг является необязательным. Как правило, вы можете сбросить контакты с помощью командлета **Set-ксклиентпин** , но если вы хотите отправить приветственное сообщение электронной почты с данными, воспользуйтесь процедурой, описанной в этом разделе. Если в таком сообщении нет необходимости, следует выполнить командлет **Set-CsClientPin**.

Сценарий **Set-CsPinSendCAWelcomeMail** позволяет задать ПИН‑код и отправить приветственное сообщение электронной почты одному пользователю. По умолчанию этот сценарий не сбрасывает ПИН-код, если он уже установлен, но вы можете использовать параметр **Force** для принудительного сброса ПИН-кода. Сообщение передается по протоколу SMTP.

Можно создать сценарий, предусматривающий многократное выполнение сценариев **Set-CsPinSendCAWelcomeMail** для задания ПИН‑кодов и передачи сообщения электронной почты группе пользователей. Вы можете изменить шаблон электронной почты (файл **кавелкомимаилтемплате. HTML** ), чтобы добавить дополнительные ссылки на страницы интрасети или изменить текст сообщения электронной почты.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Настройка начального ПИН-кода и отправка приветственного сообщения электронной почты

1.  Войдите в систему как участник группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующую команду в командной строке:
    
        Set-CsPinSendCAWelcomeMail -UserUri <user identifier>
        -From <email address of sender> [-Subject <subject for email message>]
        [-UserEmailAddress <destination email address>]
        [-Cc <email address of recipients who receive copy of email>]
        [-Bcc <email address of recipients who receive blind copies>]
        [-TemplatePath <path for email template>]
        [-SmtpServer] <SMTP server name>]
        [-BodyAsPlainText] [-UseSsl]
        [-Pin <new numeric PIN>] [-Force] `
        [-Credential <SMTP server credentials used to send email with the specified From address>]
    
    **Смтпсервер**   по умолчанию в сценарии используется значение зарезервированной переменной среды **$PSEmailServer** для этого параметра. Если переменной **$PSEmailServer** не назначено значение, необходимо задать этот параметр вручную.
    
    **Учетные данные**   по умолчанию сценарий использует учетные данные текущего пользователя. Если текущему пользователю не предоставлено разрешение на передачу сообщений электронной почты с адреса, указанного в поле "От", необходимо задать этот параметр вручную. Как правило, этот параметр задает пользователь, адрес которого не указан в поле "От".
    
    Например:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    В этом примере создается новый ПИН-код, а затем отправляется приветственное сообщение от Марко на Боба. Текст формируется на основе шаблона по умолчанию, а сообщение создается в формате HTML. По умолчанию используется тема "Добро пожаловать в Конференц-связь".
    
    Еще один пример:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    В этом примере в качестве нового ПИН-кода принудительно задается значение "383042650" для Боба, несмотря на то, что Боб имел существующий ПИН-код, а затем отправляет приветственное сообщение от Марко на Боба. Поскольку задан параметр Credential, пользователю, выполняющему команду, предлагается ввести пароль. Сообщение электронной почты отправляется с использованием протокола SSL (Secure Sockets Layer).

</div>

</div>

<span> </span>

</div>

</div>

</div>

