---
title: 'Lync Server 2013: Проверка анонимного доступа к веб-приложению'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 701954a872645e80d6aac82cab1fbf5745ad6984
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a><span data-ttu-id="ad436-102">Проверка доступа анонимного веб-приложения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad436-102">Test anonymous Web App access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad436-103">_**Тема последнего изменения:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="ad436-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad436-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="ad436-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ad436-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="ad436-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad436-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="ad436-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ad436-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad436-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad436-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="ad436-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ad436-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="ad436-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ad436-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксвебаппанонимаус.</span><span class="sxs-lookup"><span data-stu-id="ad436-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="ad436-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad436-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ad436-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ad436-112">Description</span></span>

<span data-ttu-id="ad436-113">Командлет Test-Ксвебаппанонимаус подтверждает, что анонимный пользователь может присоединиться к конференциям Lync Server с помощью Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="ad436-113">The Test-CsWebAppAnonymous cmdlet verifies that an anonymous user can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="ad436-114">При выполнении командлета Test-Ксвебаппанонимаус обращается к службе веб-билета, чтобы получить веб-билет для анонимного пользователя.</span><span class="sxs-lookup"><span data-stu-id="ad436-114">When you run the cmdlet, Test-CsWebAppAnonymous contacts the Web Ticket service to obtain a web ticket for the anonymous user.</span></span> <span data-ttu-id="ad436-115">Если командлету удалось получить этот билет, функция Test-Ксвебаппанонимаус будет обращаться к Lync Server и попытаться установить отдельные конференции для обмена мгновенными сообщениями, общего обмена приложениями и совместной работы с данными.</span><span class="sxs-lookup"><span data-stu-id="ad436-115">If the cmdlet succeeds in obtaining this ticket, Test-CsWebAppAnonymous will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="ad436-116">Обратите внимание, что Test-Ксвебаппанонимаус только проверяет интерфейсы API и соединения, используемые для создания этих конференций.</span><span class="sxs-lookup"><span data-stu-id="ad436-116">Note that Test-CsWebAppAnonymous only verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="ad436-117">На самом деле командлеты не создают и не выполняют никакие Конференции.</span><span class="sxs-lookup"><span data-stu-id="ad436-117">The cmdlet does not actually create and conduct any conferences.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ad436-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="ad436-118">Running the test</span></span>

<span data-ttu-id="ad436-119">Командлет Test-Ксвебаппанонимаус можно выполнить с помощью пары предварительно настроенных тестовых учетных записей или учетных записей двух пользователей, которые включены в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad436-119">The Test-CsWebAppAnonymous cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="ad436-120">Для выполнения этой проверки с помощью тестовых учетных записей нужно просто указать полное доменное имя для тестируемого пула сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad436-120">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="ad436-121">Например:</span><span class="sxs-lookup"><span data-stu-id="ad436-121">For example:</span></span>

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="ad436-122">Для выполнения этой проверки с использованием фактических учетных записей пользователей необходимо создать два объекта учетных данных командной консоли Lync Server (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ad436-122">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="ad436-123">После вызова Test-Ксвебаппанонимаус вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей.</span><span class="sxs-lookup"><span data-stu-id="ad436-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebAppAnonymous:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

<span data-ttu-id="ad436-124">Дополнительные сведения можно найти в разделе справки по командлету Test-Ксвебаппанонимаус.</span><span class="sxs-lookup"><span data-stu-id="ad436-124">For more information, see the help topic for the Test-CsWebAppAnonymous cmdlet.</span></span> <span data-ttu-id="ad436-125">Обратите внимание, что функция Test-Ксвебаппанонимаус является устаревшей для использования в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad436-125">Note that Test-CsWebAppAnonymous is deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ad436-126">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="ad436-126">Determining success or failure</span></span>

<span data-ttu-id="ad436-127">Если с помощью командлета Test-Ксвебаппанонимаус можно присоединиться к своим собраниям для анонимного пользователя, он вернет результат теста успешно.</span><span class="sxs-lookup"><span data-stu-id="ad436-127">If Test-CsWebAppAnonymous can join the anonymous user to his or her conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="ad436-128">Целевое полное доменное имя:</span><span class="sxs-lookup"><span data-stu-id="ad436-128">Target Fqdn :</span></span>

<span data-ttu-id="ad436-129">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="ad436-129">Result : Success</span></span>

<span data-ttu-id="ad436-130">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ad436-130">Latency : 00:00:00</span></span>

<span data-ttu-id="ad436-131">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="ad436-131">Error Message :</span></span>

<span data-ttu-id="ad436-132">Диагностик</span><span class="sxs-lookup"><span data-stu-id="ad436-132">Diagnosis :</span></span>

<span data-ttu-id="ad436-133">Если анонимный пользователь не может присоединиться к необходимым конференциям, результат теста будет помечен как сбой.</span><span class="sxs-lookup"><span data-stu-id="ad436-133">If the anonymous user can't join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="ad436-134">Обычно Test-Ксвебаппанонимаус также будет сообщать о подробном сообщении об ошибке и диагностике:</span><span class="sxs-lookup"><span data-stu-id="ad436-134">Typically Test-CsWebAppAnonymous will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="ad436-135">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ad436-135">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ad436-136">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="ad436-136">Result : Failure</span></span>

<span data-ttu-id="ad436-137">Задержка: 00:00:05.9746266</span><span class="sxs-lookup"><span data-stu-id="ad436-137">Latency : 00:00:05.9746266</span></span>

<span data-ttu-id="ad436-138">Сообщение об ошибке: ни одного ответа не получено для службы веб-билета</span><span class="sxs-lookup"><span data-stu-id="ad436-138">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="ad436-139">Диагностика: запрос HTTP-запроса не разрешен клиентом</span><span class="sxs-lookup"><span data-stu-id="ad436-139">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="ad436-140">Схема проверки подлинности "NTLM".</span><span class="sxs-lookup"><span data-stu-id="ad436-140">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="ad436-141">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ad436-141">The authentication</span></span>

<span data-ttu-id="ad436-142">заголовку, полученному от сервера, является "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="ad436-142">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ad436-143">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="ad436-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="ad436-144">Ошибки при тестировании-Ксвебаппанонимаус обычно связаны с ошибками проверки подлинности пользователя: необходимо выполнить тест с помощью действительной учетной записи пользователя, несмотря на то, что командлет проверяет возможность подключения анонимного пользователя к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad436-144">Test-CsWebAppAnonymous failures usually revolve around user authentication errors: you must run the test using a valid user account even though the cmdlet is checking the ability of an anonymous user to connect to Lync Server.</span></span> <span data-ttu-id="ad436-145">Если при выполнении теста-Ксвебаппанонимаус возникает ошибка, убедитесь в том, что указанный пользователь действительно является учетной записью пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad436-145">If Test-CsWebAppAnonymous fails, you should verify that the specified user has valid a Lync Server user account.</span></span> <span data-ttu-id="ad436-146">Вы можете получить сведения об учетной записи Lync Server с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="ad436-146">You can retrieve Lync Server account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="ad436-147">Если свойство Enabled не равно true или если команда не выполнена, это означает, что у пользователя нет действительной учетной записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad436-147">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="ad436-148">Кроме того, необходимо убедиться, что пароль, предоставленный при запуске командлета, является действительным паролем.</span><span class="sxs-lookup"><span data-stu-id="ad436-148">You should also verify that the password that you supplied when you run the cmdlet is a valid password.</span></span>

<span data-ttu-id="ad436-149">Проблемы с конфигурацией на сервере Office Web Apps также могут привести к сбою теста-Ксвебаппанонимаус; Это часто может возникнуть, если вы получаете следующую диагностику:</span><span class="sxs-lookup"><span data-stu-id="ad436-149">Configuration problems with Office Web Apps Server can also cause Test-CsWebAppAnonymous to fail; that will often be the case if you receive the following diagnosis:</span></span>

<span data-ttu-id="ad436-150">Запрос HTTP не разрешен в схеме проверки подлинности клиента "NTLM".</span><span class="sxs-lookup"><span data-stu-id="ad436-150">The HTTP request is unauthorized with client authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="ad436-151">Заголовок проверки подлинности, полученный от сервера, — "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="ad436-151">The authentication header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="ad436-152">Дополнительные сведения о диагностике и устранении проблем с сервером Office Web Apps см. в блоге [сервер Office Web apps 2013 — компьютеры,](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)на которых выводится сообщение о неработоспособности.</span><span class="sxs-lookup"><span data-stu-id="ad436-152">For more information on diagnosing and resolving Office Web Apps Server problems see the blog post [Office Web Apps Server 2013 - machines are always reported as Unhealthy](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

