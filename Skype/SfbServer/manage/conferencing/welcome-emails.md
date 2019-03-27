---
title: Отправка приветственного сообщения для звонков в пользователей в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5507827b-6f8d-4ea4-94e6-1cf72c1d38eb
description: 'Сводка: Узнайте, как приглашение пользователей принять телефонных конференций в Скайп для Business Server.'
ms.openlocfilehash: 51c4dbc04b44cb33e27cbe09f22608836485e9ad
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898496"
---
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="c290c-103">Отправка приветственного сообщения для звонков в пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c290c-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="c290c-104">**Сводка:** Узнайте, как приглашение пользователей принять телефонных конференций в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c290c-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="c290c-105">После настройки конференц-связи с телефонным подключением и проверки правильности ее работы следует назначить пользователям личные идентификационные номера (ПИН‑коды) и сообщить им о доступности этой функции.</span><span class="sxs-lookup"><span data-stu-id="c290c-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="c290c-106">Можно также предоставить вводные инструкции, например, первоначальный PIN‑код и ссылку на веб-страницу параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="c290c-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="c290c-107">Как правило командлет **Set-CsClientPin** используется для сброса ПИН-коды, но можно использовать процедуру в этом разделе, если вы хотите отправить вводные приветственное сообщение со сведениями ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="c290c-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="c290c-108">Если в таком сообщении нет необходимости, следует выполнить командлет **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="c290c-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="c290c-p103">Сценарий **Set-CsPinSendCAWelcomeMail** позволяет задать ПИН‑код и отправить приветственное сообщение электронной почты одному пользователю. При выполнении этого сценария ПИН‑код не изменяется, если он назначен ранее, но с помощью параметра Force можно задать принудительное изменение ПИН‑кода. Сообщение передается по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="c290c-p103">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user. By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN. The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="c290c-p104">Можно создать сценарий, предусматривающий многократное выполнение сценариев **Set-CsPinSendCAWelcomeMail** для задания ПИН‑кодов и передачи сообщения электронной почты группе пользователей. Можно изменить шаблон сообщения (то есть файл CAWelcomeEmailTemplate.html), добавив дополнительные ссылки на страницы интрасети или задав другой текст сообщения.</span><span class="sxs-lookup"><span data-stu-id="c290c-p104">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users. You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="c290c-114">Задание начального ПИН‑кода и отправка приветственного сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="c290c-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="c290c-115">Войдите в систему как участник группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c290c-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="c290c-116">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c290c-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c290c-117">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="c290c-117">Run the following at the command prompt:</span></span>
    
   ```
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

<span data-ttu-id="c290c-118">**SmtpServer** По умолчанию сценарий использует значение переменной среды зарезервированные **$PSEmailServer** для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="c290c-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="c290c-119">Если переменной **$PSEmailServer** не назначено значение, необходимо задать этот параметр вручную.</span><span class="sxs-lookup"><span data-stu-id="c290c-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="c290c-120">**Учетные данные** По умолчанию сценарий использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c290c-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="c290c-121">Если текущему пользователю не предоставлено разрешение на передачу сообщений электронной почты с адреса, указанного в поле "От", необходимо задать этот параметр вручную.</span><span class="sxs-lookup"><span data-stu-id="c290c-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="c290c-122">Как правило, этот параметр задает пользователь, адрес которого не указан в поле "От".</span><span class="sxs-lookup"><span data-stu-id="c290c-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="c290c-p107">В следующем примере создается новый ПИН‑код, после чего отправляется приветственное сообщение электронной почты от Марко Бобу. Текст формируется на основе шаблона по умолчанию, а сообщение создается в формате HTML. По умолчанию задается тема "Добро пожаловать на конференцию с телефонным подключением".</span><span class="sxs-lookup"><span data-stu-id="c290c-p107">The following example creates a new PIN, and then sends a welcome email from Marco to Bob. It uses the email text from the default template and creates the email message in HTML format. The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="c290c-p108">В следующем примере для Боба вместо ранее назначенного ему ПИН‑кода принудительно задается новый ПИН‑код со значением "383042650", после чего отправляется приветственное сообщение электронной почты от Марко Бобу. Поскольку задан параметр Credential, пользователю, выполняющему команду, предлагается ввести пароль. Сообщение передается по протоколу SSL.</span><span class="sxs-lookup"><span data-stu-id="c290c-p108">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob. Because the Credential parameter is specified, the person running the command is prompted to enter a password. The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
