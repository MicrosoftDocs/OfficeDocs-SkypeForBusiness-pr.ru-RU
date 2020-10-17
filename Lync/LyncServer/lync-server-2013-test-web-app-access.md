---
title: 'Lync Server 2013: тестирование доступа веб-приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cdf0c4d974732b75a7ff83022c6bfbf1c4d8e80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532936"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="c1a5c-102">Проверка доступа веб-приложения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1a5c-102">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1a5c-103">_**Последнее изменение темы:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="c1a5c-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1a5c-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="c1a5c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c1a5c-105">Monthly</span><span class="sxs-lookup"><span data-stu-id="c1a5c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1a5c-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="c1a5c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c1a5c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1a5c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1a5c-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="c1a5c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c1a5c-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c1a5c-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsWebApp.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="c1a5c-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c1a5c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c1a5c-112">Description</span></span>

<span data-ttu-id="c1a5c-113">Командлет Test-CsWebApp проверяет, могут ли пользователи, прошедшие проверку подлинности, присоединиться к конференциям Lync Server с помощью веб-приложения Lync.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="c1a5c-114">При запуске командлета Test-CsWebApp связывается со службой веб-билета для получения веб-билетов для указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="c1a5c-115">Эти билеты эффективно действуют как "билеты на допуску" для конференции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="c1a5c-116">Если можно получить билеты и проверить подлинность пользователей, Test-CsWebApp будет обращаться к Lync Server и пытаться установить отдельные конференции для обмена мгновенными сообщениями, общего доступа к приложениям и совместной работы с данными.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="c1a5c-117">Обратите внимание, что Test-CsWebApp просто проверяет интерфейсы API и подключения, используемые для создания этих конференций.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="c1a5c-118">Командлет позволяет убедиться в том, что Lync Web App можно использовать для создания конференций и присоединения к ним.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="c1a5c-119">Однако он не создает и не проводит конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c1a5c-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="c1a5c-120">Running the test</span></span>

<span data-ttu-id="c1a5c-121">Командлет Test-CsWebApp можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей или учетных записей двух пользователей, для которых включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="c1a5c-122">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="c1a5c-123">Например:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c1a5c-124">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="c1a5c-125">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-Ксвебапп:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="c1a5c-126">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-ксвебапп](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="c1a5c-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="c1a5c-127">Обратите внимание, что Test-CsWebApp было признано нерекомендуемым для использования в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c1a5c-128">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="c1a5c-128">Determining success or failure</span></span>

<span data-ttu-id="c1a5c-129">Если Test-CsWebApp можете присоединиться к конференциям, командлет вернет результат теста Success:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="c1a5c-130">Целевое полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-130">Target Fqdn :</span></span>

<span data-ttu-id="c1a5c-131">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="c1a5c-131">Result : Success</span></span>

<span data-ttu-id="c1a5c-132">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c1a5c-132">Latency : 00:00:00</span></span>

<span data-ttu-id="c1a5c-133">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-133">Error Message :</span></span>

<span data-ttu-id="c1a5c-134">Диагност</span><span class="sxs-lookup"><span data-stu-id="c1a5c-134">Diagnosis :</span></span>

<span data-ttu-id="c1a5c-135">Если пользователи не могут присоединиться к необходимым конференциям, результат теста будет помечен как сбой.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="c1a5c-136">Как правило, Test-CsWebApp также будет сообщать о подробном сообщении об ошибке и диагностике:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="c1a5c-137">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c1a5c-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c1a5c-138">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="c1a5c-138">Result : Failure</span></span>

<span data-ttu-id="c1a5c-139">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="c1a5c-139">Latency : 00:00:00</span></span>

<span data-ttu-id="c1a5c-140">Сообщение об ошибке: нет ответа, полученного для службы Web-Ticket</span><span class="sxs-lookup"><span data-stu-id="c1a5c-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="c1a5c-141">Диагностика: несанкционированный HTTP-запрос для клиента</span><span class="sxs-lookup"><span data-stu-id="c1a5c-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="c1a5c-142">Схема проверки подлинности "NTLM".</span><span class="sxs-lookup"><span data-stu-id="c1a5c-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="c1a5c-143">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="c1a5c-143">The authentication</span></span>

<span data-ttu-id="c1a5c-144">заголовку, полученному от сервера, является "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="c1a5c-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c1a5c-145">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="c1a5c-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="c1a5c-146">Ошибки Test-CsWebApp обычно включают ошибки проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="c1a5c-147">В случае сбоя Test-CsWebApp сначала необходимо убедиться, что указанные пользователи имеют действительные учетные записи пользователей и включены для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="c1a5c-148">Вы можете получить сведения об учетной записи с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c1a5c-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="c1a5c-149">Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server. Кроме того, необходимо убедиться, что указанные в командлете пароли действительны.</span><span class="sxs-lookup"><span data-stu-id="c1a5c-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

