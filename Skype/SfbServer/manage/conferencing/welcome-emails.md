---
title: Отправка приветствия по электронной почте пользователям с телефонным номером в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: Сводка. Узнайте, как поприветствовать пользователей в skype для бизнеса Server.
ms.openlocfilehash: dea63f02bcdd3fab323f7f4eff8f420bf012e9a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817499"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a>Отправка приветствия по электронной почте пользователям с телефонным номером в Skype для бизнеса Server
 
**Сводка:** Узнайте, как поприветствовать пользователей в skype для бизнеса Server.
  
После настройки функции телефонного доступа и проверки ее правильной работы необходимо установить для пользователей начальные пин-коды и уведомить пользователей о доступности этой функции. Можно включить вводные инструкции, например исходный ПИН-код и ссылку на веб-страницу параметров телефонной связи. 
  
Как правило, для сброса ПИН-кодов используется cmdlet **Set-CsClientPin,** но вы можете использовать процедуру, используемую в этом разделе, если вы хотите отправить приветствие с информацией о ПИН-коде. Если вы не хотите отправлять сообщение электронной почты, используйте **set-CsClientPin.**
  
Вы можете использовать **сценарий Set-CsPinSendCAWelcomeMail,** чтобы установить ПИН-код и отправить приветствие одному пользователю. По умолчанию сценарий не сбрасывает ПИН-код, если он уже задан, но для принудительного сброса ПИН-кода можно использовать параметр Force. Сообщение электронной почты отправляется по протоколу SMTP.
  
Можно создать сценарий, который запускает сценарий **Set-CsPinSendCAWelcomeMail** итеративным образом, чтобы установить ПИН-адреса и отправлять сообщения электронной почты группе пользователей. Вы можете изменить шаблон электронной почты (то есть файл CAWelcomeEmailTemplate.html), чтобы добавить дополнительные ссылки на страницы интрасети или изменить текст электронной почты.
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a>Настройка начального ПИН-кода и отправка приветствия по электронной почте

1. Войдите как член группы RTCUniversalServerAdmins.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Выполните в командной строке следующую команду:
    
   ```PowerShell
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
   ```

**SmtpServer** По умолчанию сценарий использует значение зарезервированной переменной **среды** $PSEmailServer для этого параметра. Если **переменная $PSEmailServer** не задана, необходимо указать этот параметр.
    
**Учетные данные** По умолчанию сценарий использует учетные данные текущего пользователя. Если у текущего пользователя нет разрешения на отправку электронной почты от имени указанного адреса отправитель, необходимо указать этот параметр. Как правило, укажите этот параметр, если адрес электронной почты не указан в качестве адреса "От".
    
В следующем примере создается новый ПИН-код, а затем отправляется приветствие электронной почты от Боба от Боба. Он использует текст электронной почты из шаблона по умолчанию и создает сообщение электронной почты в формате HTML. Тема по умолчанию — "Добро пожаловать в conferencing с номером":
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

В следующем примере новый ПИН-код со значением "383042650" для Боба, несмотря на то что у Боба уже есть ПИН-код, отправляет приветствие электронной почты от Сергея Бобу. Так как указан параметр Credential, для пользователя, запускаемого командой, будет предложено ввести пароль. Сообщение отправляется с помощью SSL:
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
