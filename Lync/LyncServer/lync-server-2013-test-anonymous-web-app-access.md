---
title: 'Lync Server 2013: Проверка анонимного доступа веб-приложения'
description: 'Lync Server 2013: Протестируйте анонимный доступ к веб-приложению.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c33840912fefcaeef069e14773cfefd0834a8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547475"
---
# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="d70e9-103">Проверка анонимного доступа веб-приложения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d70e9-103">Test anonymous Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d70e9-104">_**Последнее изменение темы:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="d70e9-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d70e9-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="d70e9-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d70e9-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="d70e9-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d70e9-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="d70e9-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d70e9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d70e9-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d70e9-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="d70e9-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d70e9-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d70e9-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d70e9-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="d70e9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="d70e9-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d70e9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d70e9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d70e9-113">Description</span></span>

<span data-ttu-id="d70e9-114">Командлет Test-CsWebAppAnonymous проверяет, что анонимный пользователь может присоединиться к конференциям Lync Server с помощью веб-приложения Lync.</span><span class="sxs-lookup"><span data-stu-id="d70e9-114">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="d70e9-115">При запуске командлета Test-CsWebAppAnonymous связывается со службой веб-билета для получения веб-билета анонимного пользователя.</span><span class="sxs-lookup"><span data-stu-id="d70e9-115">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="d70e9-116">Если командлету удалось получить этот билет, Test-CsWebAppAnonymous будет обращаться к Lync Server и пытаться установить отдельные конференции для обмена мгновенными сообщениями, общего доступа к приложениям и совместной работы с данными.</span><span class="sxs-lookup"><span data-stu-id="d70e9-116">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="d70e9-117">Обратите внимание, что Test-CsWebAppAnonymous только проверяет интерфейсы API и подключения, используемые для создания этих конференций.</span><span class="sxs-lookup"><span data-stu-id="d70e9-117">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="d70e9-118">В действительности командлет не создает и не проводит никакие Конференции.</span><span class="sxs-lookup"><span data-stu-id="d70e9-118">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d70e9-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="d70e9-119">Running the test</span></span>

<span data-ttu-id="d70e9-120">Командлет Test-CsWebAppAnonymous можно выполнить с помощью одной из предварительно настроенных тестовых учетных записей или учетных записей двух пользователей, для которых включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d70e9-120">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d70e9-121">Чтобы выполнить эту проверку с помощью тестовых учетных записей, достаточно указать полное доменное имя тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d70e9-121">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="d70e9-122">Например:</span><span class="sxs-lookup"><span data-stu-id="d70e9-122">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="d70e9-123">Чтобы выполнить эту проверку с использованием фактических учетных записей пользователей, необходимо создать два объекта учетных данных командной консоли Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d70e9-123">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d70e9-124">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-Ксвебаппанонимаус:</span><span class="sxs-lookup"><span data-stu-id="d70e9-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="d70e9-125">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета Test-CsWebAppAnonymous.</span><span class="sxs-lookup"><span data-stu-id="d70e9-125">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="d70e9-126">Обратите внимание, что Test-CsWebAppAnonymous не рекомендуется использовать в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d70e9-126">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d70e9-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="d70e9-127">Determining success or failure</span></span>

<span data-ttu-id="d70e9-128">Если Test-CsWebAppAnonymous может присоединиться к конференциям для анонимного пользователя, командлет вернет результат теста Success:</span><span class="sxs-lookup"><span data-stu-id="d70e9-128">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="d70e9-129">Целевое полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="d70e9-129">Target Fqdn :</span></span>

<span data-ttu-id="d70e9-130">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="d70e9-130">Result : Success</span></span>

<span data-ttu-id="d70e9-131">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d70e9-131">Latency : 00:00:00</span></span>

<span data-ttu-id="d70e9-132">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="d70e9-132">Error Message :</span></span>

<span data-ttu-id="d70e9-133">Диагност</span><span class="sxs-lookup"><span data-stu-id="d70e9-133">Diagnosis :</span></span>

<span data-ttu-id="d70e9-134">Если анонимный пользователь не может присоединиться к необходимым конференциям, результат теста будет помечен как сбой.</span><span class="sxs-lookup"><span data-stu-id="d70e9-134">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="d70e9-135">Как правило, Test-CsWebAppAnonymous также будет сообщать о подробном сообщении об ошибке и диагностике:</span><span class="sxs-lookup"><span data-stu-id="d70e9-135">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="d70e9-136">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d70e9-136">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d70e9-137">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="d70e9-137">Result : Failure</span></span>

<span data-ttu-id="d70e9-138">Задержка: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="d70e9-138">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="d70e9-139">Сообщение об ошибке: нет ответа, полученного для службы Web-Ticket</span><span class="sxs-lookup"><span data-stu-id="d70e9-139">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="d70e9-140">Диагностика: несанкционированный HTTP-запрос для клиента</span><span class="sxs-lookup"><span data-stu-id="d70e9-140">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="d70e9-141">Схема проверки подлинности "NTLM".</span><span class="sxs-lookup"><span data-stu-id="d70e9-141">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="d70e9-142">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="d70e9-142">The authentication</span></span>

<span data-ttu-id="d70e9-143">заголовку, полученному от сервера, является "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="d70e9-143">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d70e9-144">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="d70e9-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="d70e9-145">Test-CsWebAppAnonymous ошибки обычно связаны с ошибками проверки подлинности пользователей: необходимо выполнить тест с использованием действительной учетной записи пользователя, несмотря на то, что командлет проверяет возможность подключения анонимного пользователя к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d70e9-145">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="d70e9-146">В случае сбоя Test-CsWebAppAnonymous необходимо убедиться, что указанный пользователь имеет действительную учетную запись пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d70e9-146">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="d70e9-147">Вы можете получить сведения об учетной записи Lync Server с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="d70e9-147">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="d70e9-148">Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d70e9-148">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="d70e9-149">Кроме того, необходимо убедиться, что пароль, который вы задали при выполнении командлета, является допустимым паролем.</span><span class="sxs-lookup"><span data-stu-id="d70e9-149">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="d70e9-150">Проблемы с конфигурацией сервера Office Web Apps также могут привести к сбою Test-CsWebAppAnonymous; Это часто случается, если вы получаете следующую диагностику:</span><span class="sxs-lookup"><span data-stu-id="d70e9-150">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="d70e9-151">HTTP-запрос не авторизован с помощью схемы проверки подлинности клиента "NTLM".</span><span class="sxs-lookup"><span data-stu-id="d70e9-151">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="d70e9-152">В заголовке проверки подлинности, полученной от сервера, получено значение "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="d70e9-152">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="d70e9-153">Дополнительные сведения об устранении неполадок сервера Office Web Apps и их устранении см. в статье блог [Office Web Apps server 2013-Machines posts (сведения о неисправности)](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span><span class="sxs-lookup"><span data-stu-id="d70e9-153">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

