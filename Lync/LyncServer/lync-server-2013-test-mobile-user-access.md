---
title: 'Lync Server 2013: Проверка доступа пользователей мобильных устройств'
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
ms.openlocfilehash: 628fd3aae4f66316627176c3af025eb63202bafb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a><span data-ttu-id="b4f29-102">Проверка доступа пользователей мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4f29-102">Test mobile user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4f29-103">_**Тема последнего изменения:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="b4f29-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4f29-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b4f29-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b4f29-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="b4f29-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4f29-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="b4f29-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b4f29-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4f29-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4f29-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="b4f29-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b4f29-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="b4f29-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b4f29-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксмкксконференце.</span><span class="sxs-lookup"><span data-stu-id="b4f29-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxConference cmdlet.</span></span> <span data-ttu-id="b4f29-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4f29-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b4f29-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b4f29-112">Description</span></span>

<span data-ttu-id="b4f29-113">Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:</span><span class="sxs-lookup"><span data-stu-id="b4f29-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="b4f29-114">Обмен мгновенными сообщениями и сведениями о присутствии.</span><span class="sxs-lookup"><span data-stu-id="b4f29-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="b4f29-115">Храните и изменяйте голосовую почту внутренне, а не с поставщиком услуг беспроводной связи.</span><span class="sxs-lookup"><span data-stu-id="b4f29-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="b4f29-116">Пользуйтесь возможностями Lync Server, такими как звонки через Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="b4f29-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span> <span data-ttu-id="b4f29-117">Командлет Test-Ксмкксконференце предоставляет быстрый и простой способ убедиться, что пользователи могут присоединяться к конференции Lync Server и принимать участие в них, используя мобильное устройство.</span><span class="sxs-lookup"><span data-stu-id="b4f29-117">The Test-CsMcxConference cmdlet provides a quick and easy way to verify that users can join and participate in Lync Server conferences by using a mobile device.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b4f29-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="b4f29-118">Running the test</span></span>

<span data-ttu-id="b4f29-119">Для выполнения этой проверки необходимо создать три объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b4f29-119">To run this check, you must create three Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="b4f29-120">При вызове теста-Ксмкксконференце, как показано в следующем примере, необходимо добавить эти объекты учетных данных и адреса SIP для двух учетных записей.</span><span class="sxs-lookup"><span data-stu-id="b4f29-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxConference as shown in the following example:</span></span>

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

<span data-ttu-id="b4f29-121">Дополнительные сведения можно найти в разделе справки по командлету [Test-ксмкксконференце](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .</span><span class="sxs-lookup"><span data-stu-id="b4f29-121">For more information, see the help topic for the [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b4f29-122">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="b4f29-122">Determining success or failure</span></span>

<span data-ttu-id="b4f29-123">Если проверка пройдет успешно, тест-Ксмкксконференце сообщит результат теста "успешно".</span><span class="sxs-lookup"><span data-stu-id="b4f29-123">If the check succeeds, Test-CsMcxConference will report a test result of Success:</span></span>

<span data-ttu-id="b4f29-124">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b4f29-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b4f29-125">Конечный URI:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="b4f29-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="b4f29-126">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="b4f29-126">Result : Success</span></span>

<span data-ttu-id="b4f29-127">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b4f29-127">Latency : 00:00:00</span></span>

<span data-ttu-id="b4f29-128">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="b4f29-128">Error Message :</span></span>

<span data-ttu-id="b4f29-129">Диагностик</span><span class="sxs-lookup"><span data-stu-id="b4f29-129">Diagnosis :</span></span>

<span data-ttu-id="b4f29-130">Если проверка не пройдет успешно, Ксмкксконференце сообщит результаты теста о сбое.</span><span class="sxs-lookup"><span data-stu-id="b4f29-130">If the check is unsuccessful Test-CsMcxConference will report a test result of Failure.</span></span> <span data-ttu-id="b4f29-131">Этот результат проверки обычно сопровождается подробным сообщением об ошибке и диагностикой.</span><span class="sxs-lookup"><span data-stu-id="b4f29-131">This test result will typically be accompanied by a detailed error message and diagnosis.</span></span> <span data-ttu-id="b4f29-132">Например:</span><span class="sxs-lookup"><span data-stu-id="b4f29-132">For example:</span></span>

<span data-ttu-id="b4f29-133">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b4f29-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b4f29-134">Конечный URI:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="b4f29-134">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="b4f29-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="b4f29-135">Result : Failure</span></span>

<span data-ttu-id="b4f29-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b4f29-136">Latency : 00:00:00</span></span>

<span data-ttu-id="b4f29-137">Сообщение об ошибке: ни одного ответа не получено для службы веб-билета.</span><span class="sxs-lookup"><span data-stu-id="b4f29-137">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="b4f29-138">Внутреннее исключение: запрос ХХТП не разрешен клиентом</span><span class="sxs-lookup"><span data-stu-id="b4f29-138">Inner Exception:The HHTP request is unauthorized with client</span></span>

<span data-ttu-id="b4f29-139">Схема согласования "NTLM".</span><span class="sxs-lookup"><span data-stu-id="b4f29-139">negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="b4f29-140">Полученный заголовок проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b4f29-140">The authentication header received</span></span>

<span data-ttu-id="b4f29-141">с сервера: "согласование".</span><span class="sxs-lookup"><span data-stu-id="b4f29-141">from the server was 'Negotiate'.</span></span>

<span data-ttu-id="b4f29-142">Внутреннее исключение: удаленный сервер вернул ошибку (401).</span><span class="sxs-lookup"><span data-stu-id="b4f29-142">Inner Exception:The remote server returned an error: (401)</span></span>

<span data-ttu-id="b4f29-143">Прошедшим.</span><span class="sxs-lookup"><span data-stu-id="b4f29-143">Unauthorized.</span></span>

<span data-ttu-id="b4f29-144">Диагностик</span><span class="sxs-lookup"><span data-stu-id="b4f29-144">Diagnosis :</span></span>

<span data-ttu-id="b4f29-145">Внутренняя диагностика: X-MS-Server-Фкдб: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b4f29-145">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b4f29-146">Cache-Control: Private</span><span class="sxs-lookup"><span data-stu-id="b4f29-146">Cache-Control : private</span></span>

<span data-ttu-id="b4f29-147">Content-Type: Text/HTML; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b4f29-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="b4f29-148">Сервер: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="b4f29-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="b4f29-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="b4f29-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="b4f29-150">X — с питанием от: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b4f29-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="b4f29-151">X-Content-Types-параметры: onпрослушивание</span><span class="sxs-lookup"><span data-stu-id="b4f29-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="b4f29-152">Дата: СР. 28 мая 2014 19:22:19 GMT</span><span class="sxs-lookup"><span data-stu-id="b4f29-152">Date : Wed, 28 May 2014 19:22:19 GMT</span></span>

<span data-ttu-id="b4f29-153">Content-Length: 6305</span><span class="sxs-lookup"><span data-stu-id="b4f29-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b4f29-154">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="b4f29-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="b4f29-155">Если при выполнении теста-Ксмкксконференце возникла ошибка, убедитесь в том, что служба Mobility Service запущена и доступ к ней возможен.</span><span class="sxs-lookup"><span data-stu-id="b4f29-155">If Test-CsMcxConference fails you should begin by verifying that the mobility service is running and can be accessed.</span></span> <span data-ttu-id="b4f29-156">Это можно сделать с помощью веб-браузера, чтобы убедиться, что вы можете получить доступ к URL-адресу службы Mobility Service для пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4f29-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="b4f29-157">Например, эта команда проверяет URL-адрес для пула atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b4f29-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

<span data-ttu-id="b4f29-158">Если вы можете получить доступ к службе Mobility Service, вы должны убедиться, что у ваших тестовых пользователей есть действительные учетные записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4f29-158">If the mobility service can be accessed you should then verify that your test users have valid Lync Server accounts.</span></span> <span data-ttu-id="b4f29-159">Вы можете получить сведения об учетной записи с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b4f29-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="b4f29-160">Если свойство Enabled не равно true или если команда не выполнена, это означает, что у пользователя нет действительной учетной записи Lync Server. Кроме того, необходимо убедиться в том, что для каждой учетной записи пользователя включена поддержка мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="b4f29-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that each user account is enabled for mobility.</span></span> <span data-ttu-id="b4f29-161">Для этого сначала определите политику мобильности, назначенную учетной записи:</span><span class="sxs-lookup"><span data-stu-id="b4f29-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="b4f29-162">После того как вы узнаете имя политики, используйте командлет Get-Ксмобилитиполици, чтобы убедиться, что для политики (например, Редмондмобилитиполици) задано значение true для свойства Енаблемобилити.</span><span class="sxs-lookup"><span data-stu-id="b4f29-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="b4f29-163">Если при запуске test-Ксмкксконференце появляется сообщение об ошибке "заголовок для проверки подлинности", которое часто означает, что вы не указали действительную учетную запись пользователя, проверьте имя пользователя и пароль, а затем повторите проверку.</span><span class="sxs-lookup"><span data-stu-id="b4f29-163">If you receive an “authentication header” error message when you run Test-CsMcxConference that often means that you have not specified a valid user account, Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="b4f29-164">Если вы убедились в том, что учетная запись пользователя верна, используйте командлет Get-Ксвебсервицеконфигуратион и проверьте значение свойства Усевиндовсаус.</span><span class="sxs-lookup"><span data-stu-id="b4f29-164">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="b4f29-165">С помощью которого вы узнаете, какие методы проверки подлинности включены в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b4f29-165">That will tell you which authentication methods are enabled in your organization.</span></span>

<span data-ttu-id="b4f29-166">Дополнительные советы по устранению неполадок со службой Mobility Service можно найти в [статье пошаговые инструкции по устранению неполадок, связанных с подключением к блогу внешних мобильных устройств Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4f29-166">For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

