---
title: 'Lync Server 2013: (необязательно) Добро пожаловать пользователи в Конференц-связь с телефонным подключением'
description: 'Lync Server 2013: (необязательно) Добро пожаловать пользователям в Конференц-связь с телефонным подключением.'
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
ms.openlocfilehash: 0d33c7184a8cf22699b4ebe8d8ea8b4ef1c133a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546905"
---
# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a>Необязательно Добро пожаловать в Конференц-связь с телефонным подключением в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-30_

После настройки конференц-связи с телефонным подключением и проверки, чтобы убедиться, что она работает должным образом, необходимо задать исходные идентификационные номера (ПИН-коды) для пользователей и уведомить пользователей о доступности функции, в том числе вводные инструкции, такие как начальный ПИН-код и ссылка на веб-страницу параметров конференц-связи с телефонным подключением. Это действие необязательно. Как правило, командлет **Set-CsClientPin** используется для сброса ПИН-кодов, но вы можете использовать процедуру, описанную в этом разделе, в первый раз, если вы хотите отправить приветственное сообщение с информацией. Если вы не хотите отправлять электронную почту, вместо этого можно использовать **Set – CsClientPin** .

С помощью скрипта **Set-CsPinSendCAWelcomeMail** можно задать ПИН-код и отправить приветственное сообщение одному пользователю. По умолчанию этот параметр не сбрасывает ПИН-код, если он уже задан, но вы можете использовать параметр **Force** для принудительного сброса ПИН-кода. Сообщение электронной почты отправляется с помощью протокола SMTP.

Вы можете создать скрипт, выполняющий скрипт **Set-CsPinSendCAWelcomeMail** для последовательного задания ПИН-кодов и отправки электронной почты группе пользователей. Вы можете изменить шаблон электронной почты (то есть, файл **CAWelcomeEmailTemplate.html** ), чтобы добавить дополнительные ссылки на страницы интрасети или изменить текст сообщения электронной почты.

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a>Установка начального ПИН-кода и отправка приветственного сообщения электронной почты

1.  Войдите в систему с учетной записью члена группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните в командной строке следующую команду:
    
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
    
    **Смтпсервер**     По умолчанию скрипт использует значение зарезервированной переменной среды **$PSEmailServer** для этого параметра. Если переменная **$PSEmailServer** не задана, необходимо указать этот параметр.
    
    **Учетные данные**     По умолчанию скрипт использует учетные данные текущего пользователя. Если текущий пользователь не имеет разрешения на отправку почты от имени указанного адреса отправителя, необходимо указать этот параметр. В качестве общего правила укажите этот параметр, если вы не укажете адрес электронной почты в качестве адреса отправителя.
    
    Например:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    В этом примере создается новый ПИН-код, а затем отправляется приветственное сообщение от Марко Бобу. Он использует текст сообщения электронной почты из шаблона по умолчанию и создает сообщение электронной почты в формате HTML. По умолчанию темой является "Добро пожаловать в Конференц-связь".
    
    Другой пример:
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    В этом примере задается новый ПИН-код со значением "383042650" для Боба, несмотря на то, что Боб имел существующий ПИН-код, а затем отправляет приветственное сообщение от Марко Бобу. Так как указан параметр Credential, пользователю, выполняющему команду, предлагается ввести пароль. Сообщение отправляется с помощью протокола SSL.

</div>

</div>

<span> </span>

</div>

</div>

</div>

