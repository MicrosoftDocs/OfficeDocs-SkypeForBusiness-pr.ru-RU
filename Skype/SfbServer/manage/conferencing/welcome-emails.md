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
# <a name="send-welcome-email-to-dial-in-users-in-skype-for-business-server"></a><span data-ttu-id="87377-103">Отправка приветствия по электронной почте пользователям с телефонным номером в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="87377-103">Send welcome email to dial-in users in Skype for Business Server</span></span>
 
<span data-ttu-id="87377-104">**Сводка:** Узнайте, как поприветствовать пользователей в skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="87377-104">**Summary:** Learn how to welcome users to dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="87377-105">После настройки функции телефонного доступа и проверки ее правильной работы необходимо установить для пользователей начальные пин-коды и уведомить пользователей о доступности функции.</span><span class="sxs-lookup"><span data-stu-id="87377-105">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature.</span></span> <span data-ttu-id="87377-106">Можно включить вводные инструкции, например исходный ПИН-код и ссылку на веб-страницу параметров телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="87377-106">You can include introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings web page.</span></span> 
  
<span data-ttu-id="87377-107">Как правило, для сброса ПИН-кодов используется cmdlet **Set-CsClientPin,** но вы можете использовать процедуру, используемую в этом разделе, если вы хотите отправить приветствие с информацией о ПИН-коде.</span><span class="sxs-lookup"><span data-stu-id="87377-107">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic if you want to send an introductory welcome email with the PIN information.</span></span> <span data-ttu-id="87377-108">Если вы не хотите отправлять сообщение электронной почты, используйте **set-CsClientPin.**</span><span class="sxs-lookup"><span data-stu-id="87377-108">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>
  
<span data-ttu-id="87377-109">С помощью скрипта **Set-CsPinSendCAWelcomeMail** можно установить ПИН-код и отправить приветствие одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="87377-109">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="87377-110">По умолчанию сценарий не сбрасывает ПИН-код, если он уже задан, но для принудительного сброса ПИН-кода можно использовать параметр Force.</span><span class="sxs-lookup"><span data-stu-id="87377-110">By default, the script does not reset a PIN if it is already set, but you can use the Force parameter to force reset a PIN.</span></span> <span data-ttu-id="87377-111">Сообщение электронной почты отправляется по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="87377-111">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>
  
<span data-ttu-id="87377-112">Можно создать сценарий, который запускает сценарий **Set-CsPinSendCAWelcomeMail** итеративным образом, чтобы установить ПИН-адреса и отправлять сообщения электронной почты группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="87377-112">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="87377-113">Вы можете изменить шаблон электронной почты (то есть файл CAWelcomeEmailTemplate.html), чтобы добавить дополнительные ссылки на страницы интрасети или изменить текст электронной почты.</span><span class="sxs-lookup"><span data-stu-id="87377-113">You can modify the email template (that is, the CAWelcomeEmailTemplate.html file) to add more links to intranet pages or modify the email text.</span></span>
  


## <a name="set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="87377-114">Настройка начального ПИН-кода и отправка приветствия по электронной почте</span><span class="sxs-lookup"><span data-stu-id="87377-114">Set an initial PIN and send welcome email</span></span>

1. <span data-ttu-id="87377-115">Войдите как член группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="87377-115">Log on as a member of the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="87377-116">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="87377-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="87377-117">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="87377-117">Run the following at the command prompt:</span></span>
    
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

<span data-ttu-id="87377-118">**SmtpServer** По умолчанию сценарий использует значение зарезервированной переменной **среды** $PSEmailServer для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="87377-118">**SmtpServer** By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="87377-119">Если **переменная $PSEmailServer** не задана, необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="87377-119">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
<span data-ttu-id="87377-120">**Учетные данные** По умолчанию сценарий использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="87377-120">**Credential** By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="87377-121">Если у текущего пользователя нет разрешения на отправку электронной почты от имени указанного адреса отправитель, необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="87377-121">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="87377-122">Как правило, укажите этот параметр, если адрес электронной почты не указан в качестве адреса "От".</span><span class="sxs-lookup"><span data-stu-id="87377-122">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
<span data-ttu-id="87377-123">В следующем примере создается новый ПИН-код, а затем отправляется приветствие электронной почты от Боба от Боба.</span><span class="sxs-lookup"><span data-stu-id="87377-123">The following example creates a new PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="87377-124">Он использует текст электронной почты из шаблона по умолчанию и создает сообщение электронной почты в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="87377-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="87377-125">Тема по умолчанию — "Добро пожаловать в conferencing с номером":</span><span class="sxs-lookup"><span data-stu-id="87377-125">The default Subject is "Welcome to Dial In Conferencing":</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com"
```

<span data-ttu-id="87377-126">В следующем примере новый ПИН-код со значением "383042650" для Боба, несмотря на то что у Боба был существующий ПИН-код, отправляет приветствие электронной почты от Бобу.</span><span class="sxs-lookup"><span data-stu-id="87377-126">The next example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="87377-127">Так как указан параметр Credential, для пользователя, запускаемого командой, будет предложено ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="87377-127">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="87377-128">Сообщение отправляется с помощью SSL:</span><span class="sxs-lookup"><span data-stu-id="87377-128">The email is sent by using the Secure Sockets Layer (SSL):</span></span>
  
```PowerShell
Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
-From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
-Pin "383042650" -Force
-Credential Admin@contoso.com -UseSsl
```
