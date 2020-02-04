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

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="d6181-102">Приветствие пользователей в конференции с телефонным подключением Lync Server 2013 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d6181-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6181-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="d6181-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="d6181-104">После настройки конференц-связи с телефонным подключением и проверки правильности ее функционирования вы должны задать начальные личные коды (PIN) для пользователей и уведомлять пользователей о доступности функции, включая вводные инструкции, такие в качестве первоначального PIN-кода и ссылки на веб-страницу параметров конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d6181-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="d6181-105">Этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="d6181-105">This step is optional.</span></span> <span data-ttu-id="d6181-106">Как правило, вы можете сбросить контакты с помощью командлета **Set-ксклиентпин** , но если вы хотите отправить приветственное сообщение электронной почты с данными, воспользуйтесь процедурой, описанной в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d6181-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="d6181-107">Если в таком сообщении нет необходимости, следует выполнить командлет **Set-CsClientPin**.</span><span class="sxs-lookup"><span data-stu-id="d6181-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="d6181-108">Сценарий **Set-CsPinSendCAWelcomeMail** позволяет задать ПИН‑код и отправить приветственное сообщение электронной почты одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="d6181-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="d6181-109">По умолчанию этот сценарий не сбрасывает ПИН-код, если он уже установлен, но вы можете использовать параметр **Force** для принудительного сброса ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="d6181-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="d6181-110">Сообщение передается по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="d6181-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="d6181-111">Можно создать сценарий, предусматривающий многократное выполнение сценариев **Set-CsPinSendCAWelcomeMail** для задания ПИН‑кодов и передачи сообщения электронной почты группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="d6181-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="d6181-112">Вы можете изменить шаблон электронной почты (файл **кавелкомимаилтемплате. HTML** ), чтобы добавить дополнительные ссылки на страницы интрасети или изменить текст сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d6181-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="d6181-113">Настройка начального ПИН-кода и отправка приветственного сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="d6181-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="d6181-114">Войдите в систему как участник группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d6181-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d6181-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d6181-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d6181-116">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="d6181-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="d6181-117">**Смтпсервер**   по умолчанию в сценарии используется значение зарезервированной переменной среды **$PSEmailServer** для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="d6181-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="d6181-118">Если переменной **$PSEmailServer** не назначено значение, необходимо задать этот параметр вручную.</span><span class="sxs-lookup"><span data-stu-id="d6181-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="d6181-119">**Учетные данные**   по умолчанию сценарий использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d6181-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="d6181-120">Если текущему пользователю не предоставлено разрешение на передачу сообщений электронной почты с адреса, указанного в поле "От", необходимо задать этот параметр вручную.</span><span class="sxs-lookup"><span data-stu-id="d6181-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="d6181-121">Как правило, этот параметр задает пользователь, адрес которого не указан в поле "От".</span><span class="sxs-lookup"><span data-stu-id="d6181-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="d6181-122">Например:</span><span class="sxs-lookup"><span data-stu-id="d6181-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="d6181-123">В этом примере создается новый ПИН-код, а затем отправляется приветственное сообщение от Марко на Боба.</span><span class="sxs-lookup"><span data-stu-id="d6181-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="d6181-124">Текст формируется на основе шаблона по умолчанию, а сообщение создается в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="d6181-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="d6181-125">По умолчанию используется тема "Добро пожаловать в Конференц-связь".</span><span class="sxs-lookup"><span data-stu-id="d6181-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="d6181-126">Еще один пример:</span><span class="sxs-lookup"><span data-stu-id="d6181-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="d6181-127">В этом примере в качестве нового ПИН-кода принудительно задается значение "383042650" для Боба, несмотря на то, что Боб имел существующий ПИН-код, а затем отправляет приветственное сообщение от Марко на Боба.</span><span class="sxs-lookup"><span data-stu-id="d6181-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="d6181-128">Поскольку задан параметр Credential, пользователю, выполняющему команду, предлагается ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="d6181-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="d6181-129">Сообщение электронной почты отправляется с использованием протокола SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="d6181-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

