---
title: 'Lync Server 2013: (необязательно) Добро пожаловать пользователи в Конференц-связь с телефонным подключением'
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
ms.openlocfilehash: 4698484c240322623760f1fd308398192bfb928f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-welcome-users-to-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="30c78-102">Необязательно Добро пожаловать в Конференц-связь с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30c78-102">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30c78-103">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="30c78-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="30c78-104">После настройки конференц-связи с телефонным подключением и проверки правильности ее работы необходимо задать исходные персональные идентификационные номера (ПИН-коды) для пользователей и уведомить пользователей о доступности функции, в том числе вводные инструкции, такие в качестве начального ПИН-кода и ссылки на веб-страницу параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="30c78-104">After you configure dial-in conferencing and test to verify that it is functioning properly, you should set initial personal identification numbers (PINs) for users and notify users about the availability of the feature, including introductory instructions such as the initial PIN and the link to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="30c78-105">Это действие необязательно.</span><span class="sxs-lookup"><span data-stu-id="30c78-105">This step is optional.</span></span> <span data-ttu-id="30c78-106">Как правило, командлет **Set-CsClientPin** используется для сброса ПИН-кодов, но вы можете использовать процедуру, описанную в этом разделе, в первый раз, если вы хотите отправить приветственное сообщение с информацией.</span><span class="sxs-lookup"><span data-stu-id="30c78-106">Typically, you use the **Set-CsClientPin** cmdlet to reset PINs, but you can use the procedure in this topic the first time if you want to send a welcome email with the information.</span></span> <span data-ttu-id="30c78-107">Если вы не хотите отправлять электронную почту, вместо этого можно использовать **Set – CsClientPin** .</span><span class="sxs-lookup"><span data-stu-id="30c78-107">If you do not want to send the email, you can use **Set-CsClientPin** instead.</span></span>

<span data-ttu-id="30c78-108">С помощью скрипта **Set-CsPinSendCAWelcomeMail** можно задать ПИН-код и отправить приветственное сообщение одному пользователю.</span><span class="sxs-lookup"><span data-stu-id="30c78-108">You can use the **Set-CsPinSendCAWelcomeMail** script to set the PIN and send a welcome email to a single user.</span></span> <span data-ttu-id="30c78-109">По умолчанию этот параметр не сбрасывает ПИН-код, если он уже задан, но вы можете использовать параметр **Force** для принудительного сброса ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="30c78-109">By default, the script does not reset a PIN if it is already set, but you can use the **Force** parameter to force reset a PIN.</span></span> <span data-ttu-id="30c78-110">Сообщение электронной почты отправляется с помощью протокола SMTP.</span><span class="sxs-lookup"><span data-stu-id="30c78-110">The email message is sent using Simple Mail Transfer Protocol (SMTP).</span></span>

<span data-ttu-id="30c78-111">Вы можете создать скрипт, выполняющий скрипт **Set-CsPinSendCAWelcomeMail** для последовательного задания ПИН-кодов и отправки электронной почты группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="30c78-111">You can create a script that runs the **Set-CsPinSendCAWelcomeMail** script iteratively to set PINs and send email to a group of users.</span></span> <span data-ttu-id="30c78-112">Вы можете изменить шаблон электронной почты (то есть, файл **кавелкомимаилтемплате. HTML** ), чтобы добавить дополнительные ссылки на страницы интрасети или изменить текст сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="30c78-112">You can modify the email template (that is, the **CAWelcomeEmailTemplate.html** file) to add more links to intranet pages or modify the email text.</span></span>

<div>

## <a name="to-set-an-initial-pin-and-send-welcome-email"></a><span data-ttu-id="30c78-113">Установка начального ПИН-кода и отправка приветственного сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="30c78-113">To set an initial PIN and send welcome email</span></span>

1.  <span data-ttu-id="30c78-114">Войдите в систему с учетной записью члена группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="30c78-114">Log on as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="30c78-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="30c78-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="30c78-116">Выполните в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="30c78-116">Run the following at the command prompt:</span></span>
    
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
    
    <span data-ttu-id="30c78-117">**Смтпсервер**   по умолчанию в сценарии используется значение зарезервированной переменной среды **$PSEmailServer** для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="30c78-117">**SmtpServer**   By default, the script uses the value of the reserved environment variable **$PSEmailServer** for this parameter.</span></span> <span data-ttu-id="30c78-118">Если переменная **$PSEmailServer** не задана, необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="30c78-118">If the **$PSEmailServer** variable is not set, you must specify this parameter.</span></span>
    
    <span data-ttu-id="30c78-119">**Учетные данные**   по умолчанию скрипт использует учетные данные текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="30c78-119">**Credential**   By default, the script uses the credentials of the current user.</span></span> <span data-ttu-id="30c78-120">Если текущий пользователь не имеет разрешения на отправку почты от имени указанного адреса отправителя, необходимо указать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="30c78-120">If the current user does not have permission to send email on behalf of the specified From address, you must specify this parameter.</span></span> <span data-ttu-id="30c78-121">В качестве общего правила укажите этот параметр, если вы не укажете адрес электронной почты в качестве адреса отправителя.</span><span class="sxs-lookup"><span data-stu-id="30c78-121">As a general rule, specify this parameter if you do not specify your email address as the From address.</span></span>
    
    <span data-ttu-id="30c78-122">Например:</span><span class="sxs-lookup"><span data-stu-id="30c78-122">For example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com"
    
    <span data-ttu-id="30c78-123">В этом примере создается новый ПИН-код, а затем отправляется приветственное сообщение от Марко Бобу.</span><span class="sxs-lookup"><span data-stu-id="30c78-123">This example creates a new PIN and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="30c78-124">Он использует текст сообщения электронной почты из шаблона по умолчанию и создает сообщение электронной почты в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="30c78-124">It uses the email text from the default template and creates the email message in HTML format.</span></span> <span data-ttu-id="30c78-125">По умолчанию темой является "Добро пожаловать в Конференц-связь".</span><span class="sxs-lookup"><span data-stu-id="30c78-125">The default Subject is "Welcome to Dial In Conferencing".</span></span>
    
    <span data-ttu-id="30c78-126">Другой пример:</span><span class="sxs-lookup"><span data-stu-id="30c78-126">Another example:</span></span>
    
        Set-CsPinSendCAWelcomeMail -UserUri "bob@contoso.com"
        -From "marco@contoso.com" -Subject "Your new dial-in conferencing PIN"
        -Pin "383042650" -Force
        -Credential Admin@contoso.com -UseSsl
    
    <span data-ttu-id="30c78-127">В этом примере задается новый ПИН-код со значением "383042650" для Боба, несмотря на то, что Боб имел существующий ПИН-код, а затем отправляет приветственное сообщение от Марко Бобу.</span><span class="sxs-lookup"><span data-stu-id="30c78-127">This example forces a new PIN with a value of "383042650" for Bob, even though Bob had an existing PIN, and then sends a welcome email from Marco to Bob.</span></span> <span data-ttu-id="30c78-128">Так как указан параметр Credential, пользователю, выполняющему команду, предлагается ввести пароль.</span><span class="sxs-lookup"><span data-stu-id="30c78-128">Because the Credential parameter is specified, the person running the command is prompted to enter a password.</span></span> <span data-ttu-id="30c78-129">Сообщение отправляется с помощью протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="30c78-129">The email is sent by using the Secure Sockets Layer (SSL).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

