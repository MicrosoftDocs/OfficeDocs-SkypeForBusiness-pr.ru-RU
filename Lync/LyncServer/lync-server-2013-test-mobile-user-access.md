---
title: 'Lync Server 2013: Проверка доступа мобильных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8afea8450df1533928a0407fb81866351705186e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="9f890-102">Проверка доступа пользователей мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f890-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f890-103">_**Последнее изменение темы:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="9f890-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f890-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="9f890-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="9f890-105">Monthly Channel</span><span class="sxs-lookup"><span data-stu-id="9f890-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f890-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="9f890-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="9f890-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f890-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f890-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="9f890-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="9f890-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9f890-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="9f890-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxConference.</span><span class="sxs-lookup"><span data-stu-id="9f890-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="9f890-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f890-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="9f890-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9f890-112">Description</span></span>

<span data-ttu-id="9f890-113">Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:</span><span class="sxs-lookup"><span data-stu-id="9f890-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="9f890-114">Обмен мгновенными сообщениями и сведениями о присутствии Exchange.</span><span class="sxs-lookup"><span data-stu-id="9f890-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="9f890-115">Храните и извлекать голосовую почту внутренне, а не со своего поставщика услуг беспроводной связи.</span><span class="sxs-lookup"><span data-stu-id="9f890-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="9f890-116">Используйте возможности Lync Server, такие как вызов с помощью конференц-связи по работе и удаленному доступу.</span><span class="sxs-lookup"><span data-stu-id="9f890-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="9f890-117">Командлет Test-CsMcxConference обеспечивает быстрый и простой способ проверки того, что пользователи могут присоединяться к конференциям Lync Server и участвовать в них с помощью мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="9f890-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="9f890-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="9f890-118">Running the test</span></span>

<span data-ttu-id="9f890-119">Чтобы выполнить эту проверку, необходимо создать три объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9f890-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="9f890-120">Затем необходимо включить эти объекты учетных данных и SIP-адреса этих учетных записей при вызове Test-CsMcxConference, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9f890-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="9f890-121">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="9f890-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="9f890-122">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="9f890-122">Determining success or failure</span></span>

<span data-ttu-id="9f890-123">Если проверка прошла успешно, Test-CsMcxConference сообщит результат теста Success:</span><span class="sxs-lookup"><span data-stu-id="9f890-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="9f890-124">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f890-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f890-125">Целевой URI:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="9f890-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="9f890-126">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="9f890-126">Result : Success</span></span>

<span data-ttu-id="9f890-127">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f890-127">Latency : 00:00:00</span></span>

<span data-ttu-id="9f890-128">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="9f890-128">Error Message :</span></span>

<span data-ttu-id="9f890-129">Диагност</span><span class="sxs-lookup"><span data-stu-id="9f890-129">Diagnosis :</span></span>

<span data-ttu-id="9f890-130">Если проверка не удалась, тест-CsMcxConference сообщит результат теста "сбой".</span><span class="sxs-lookup"><span data-stu-id="9f890-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="9f890-131">Этот результат проверки обычно сопровождается подробным сообщением об ошибке и диагностикой.</span><span class="sxs-lookup"><span data-stu-id="9f890-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="9f890-132">Например:</span><span class="sxs-lookup"><span data-stu-id="9f890-132">For example:</span></span>

<span data-ttu-id="9f890-133">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f890-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f890-134">Целевой URI:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="9f890-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="9f890-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="9f890-135">Result : Failure</span></span>

<span data-ttu-id="9f890-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="9f890-136">Latency : 00:00:00</span></span>

<span data-ttu-id="9f890-137">Сообщение об ошибке: нет ответа, полученного для службы веб-билета.</span><span class="sxs-lookup"><span data-stu-id="9f890-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="9f890-138">Внутреннее исключение: запрос ХХТП не авторизован для клиента</span><span class="sxs-lookup"><span data-stu-id="9f890-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="9f890-139">Схема согласования "NTLM".</span><span class="sxs-lookup"><span data-stu-id="9f890-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="9f890-140">Полученный заголовок проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="9f890-140">The authentication header received</span></span>

<span data-ttu-id="9f890-141">с сервера было "согласование".</span><span class="sxs-lookup"><span data-stu-id="9f890-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="9f890-142">Внутреннее исключение: удаленный сервер вернул ошибку: (401)</span><span class="sxs-lookup"><span data-stu-id="9f890-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="9f890-143">Доступ.</span><span class="sxs-lookup"><span data-stu-id="9f890-143">Unauthorized.</span></span>

<span data-ttu-id="9f890-144">Диагност</span><span class="sxs-lookup"><span data-stu-id="9f890-144">Diagnosis :</span></span>

<span data-ttu-id="9f890-145">Внутренняя диагностика: X — MS $ Server – Фкдб: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="9f890-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="9f890-146">Cache — Control: Private</span><span class="sxs-lookup"><span data-stu-id="9f890-146">Cache-Control : private</span></span>

<span data-ttu-id="9f890-147">Content-Type: Text/HTML; charset = UTF – 8.</span><span class="sxs-lookup"><span data-stu-id="9f890-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="9f890-148">Сервер: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="9f890-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="9f890-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="9f890-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="9f890-150">Питание от X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9f890-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="9f890-151">X — Content – Type — параметры: параметр "пассивный прослушивание"</span><span class="sxs-lookup"><span data-stu-id="9f890-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="9f890-152">Дата: среда, 28 мая 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="9f890-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="9f890-153">Content — Length: 6305</span><span class="sxs-lookup"><span data-stu-id="9f890-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="9f890-154">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="9f890-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="9f890-155">Если не удается выполнить Test-CsMcxConference, следует начать с проверки того, запущена ли служба Mobility Service и доступна ли она.</span><span class="sxs-lookup"><span data-stu-id="9f890-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="9f890-156">Это можно сделать с помощью веб-браузера, чтобы проверить, что можно получить доступ к URL-адресу службы Mobility пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f890-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="9f890-157">Например, эта команда проверяет URL-адрес пула atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="9f890-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="9f890-158">Если вы можете получить доступ к службе Mobility Service, убедитесь, что тестовые пользователи имеют действительные учетные записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f890-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="9f890-159">Вы можете получить сведения об учетной записи с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9f890-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="9f890-160">Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server. Кроме того, необходимо убедиться, что для каждой учетной записи пользователя включена поддержка мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="9f890-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="9f890-161">Для этого сначала определите политику мобильности, назначенную учетной записи:</span><span class="sxs-lookup"><span data-stu-id="9f890-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="9f890-162">Зная имя политики, используйте командлет Get-CsMobilityPolicy, чтобы убедиться, что рассматриваемая политика (например, Редмондмобилитиполици) имеет свойство Енаблемобилити со значением true:</span><span class="sxs-lookup"><span data-stu-id="9f890-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="9f890-163">Если при выполнении командлета Test-CsMcxConference появляется сообщение об ошибке "заголовок проверки подлинности", которое часто означает, что вы не указали допустимую учетную запись пользователя, проверьте имя пользователя и пароль, а затем повторите проверку.</span><span class="sxs-lookup"><span data-stu-id="9f890-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="9f890-164">Если вы убеждены, что учетная запись пользователя действительна, используйте командлет Get-CsWebServiceConfiguration и проверьте значение свойства Усевиндовсаус.</span><span class="sxs-lookup"><span data-stu-id="9f890-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="9f890-165">, Покажет, какие методы проверки подлинности включены в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9f890-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="9f890-166">Дополнительные советы по устранению неполадок в службе Mobility Service можно найти в статье блог [Устранение неполадок, связанных с подключением внешних мобильных устройств Lync, с](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)пошаговым выполнением.</span><span class="sxs-lookup"><span data-stu-id="9f890-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

