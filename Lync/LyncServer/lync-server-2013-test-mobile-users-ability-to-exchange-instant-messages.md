---
title: 'Lync Server 2013: Проверка возможности обмена мгновенными сообщениями с пользователями мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="b622a-102">Тестирование возможности мобильных пользователей обмениваться мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b622a-102">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b622a-103">_**Тема последнего изменения:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="b622a-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b622a-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b622a-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b622a-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="b622a-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b622a-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="b622a-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b622a-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b622a-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b622a-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="b622a-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b622a-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="b622a-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b622a-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="b622a-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="b622a-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b622a-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b622a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b622a-112">Description</span></span>

<span data-ttu-id="b622a-113">Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:</span><span class="sxs-lookup"><span data-stu-id="b622a-113">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="b622a-114">Обмен мгновенными сообщениями и сведениями о присутствии.</span><span class="sxs-lookup"><span data-stu-id="b622a-114">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="b622a-115">Храните и изменяйте голосовую почту внутренне, а не с поставщиком услуг беспроводной связи.</span><span class="sxs-lookup"><span data-stu-id="b622a-115">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="b622a-116">Пользуйтесь возможностями Lync Server, такими как звонки через Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="b622a-116">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="b622a-117">Командлет Test-CsMxcP2PIM предоставляет быстрый и простой способ проверки того, что пользователи могут использовать службу Mobility Service для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b622a-117">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b622a-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="b622a-118">Running the test</span></span>

<span data-ttu-id="b622a-119">Чтобы выполнить этот тест, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b622a-119">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="b622a-120">После вызова Test-CsMcxP2PIM вы должны добавить эти объекты учетных данных и адреса SIP для двух учетных записей.</span><span class="sxs-lookup"><span data-stu-id="b622a-120">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="b622a-121">Дополнительные сведения можно найти в разделе справки по командлету [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="b622a-121">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b622a-122">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="b622a-122">Determining success or failure</span></span>

<span data-ttu-id="b622a-123">Если два тестовых пользователя могут обмениваться мгновенными сообщениями с помощью службы Mobility Service, при использовании команды Test-CsMcxP2PIM будут возвращены результаты проверки.</span><span class="sxs-lookup"><span data-stu-id="b622a-123">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="b622a-124">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b622a-124">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b622a-125">Конечный URI:http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="b622a-125">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="b622a-126">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="b622a-126">Result : Success</span></span>

<span data-ttu-id="b622a-127">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b622a-127">Latency : 00:00:00</span></span>

<span data-ttu-id="b622a-128">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="b622a-128">Error Message :</span></span>

<span data-ttu-id="b622a-129">Диагностик</span><span class="sxs-lookup"><span data-stu-id="b622a-129">Diagnosis :</span></span>

<span data-ttu-id="b622a-130">В противном случае результат будет настроен на сбой, и на экране появится подробное сообщение об ошибке и диагностика.</span><span class="sxs-lookup"><span data-stu-id="b622a-130">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="b622a-131">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b622a-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b622a-132">Конечный URI:https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="b622a-132">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="b622a-133">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="b622a-133">Result : Failure</span></span>

<span data-ttu-id="b622a-134">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b622a-134">Latency : 00:00:00</span></span>

<span data-ttu-id="b622a-135">Сообщение об ошибке: ни одного ответа не получено для службы веб-билета.</span><span class="sxs-lookup"><span data-stu-id="b622a-135">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="b622a-136">Внутреннее исключение: запрос ХХТП не разрешен</span><span class="sxs-lookup"><span data-stu-id="b622a-136">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="b622a-137">Клиентская схема согласования "NTLM".</span><span class="sxs-lookup"><span data-stu-id="b622a-137">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="b622a-138">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="b622a-138">The authentication</span></span>

<span data-ttu-id="b622a-139">заголовку, полученному от сервера, является "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="b622a-139">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="b622a-140">Внутреннее исключение: удаленный сервер вернул ошибку:</span><span class="sxs-lookup"><span data-stu-id="b622a-140">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="b622a-141">(401) от несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="b622a-141">(401) Unauthorized.</span></span>

<span data-ttu-id="b622a-142">Диагностик</span><span class="sxs-lookup"><span data-stu-id="b622a-142">Diagnosis :</span></span>

<span data-ttu-id="b622a-143">Внутренняя диагностика: X-MS-Server-Фкдб: ATL-CS-</span><span class="sxs-lookup"><span data-stu-id="b622a-143">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="b622a-144">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b622a-144">001.litwareinc.com</span></span>

<span data-ttu-id="b622a-145">Cache-Control: Private</span><span class="sxs-lookup"><span data-stu-id="b622a-145">Cache-Control : private</span></span>

<span data-ttu-id="b622a-146">Content-Type: Text/HTML; charset = UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b622a-146">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="b622a-147">Сервер: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="b622a-147">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="b622a-148">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="b622a-148">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="b622a-149">X — с питанием от: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b622a-149">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="b622a-150">X-Content-Types-параметры: onпрослушивание</span><span class="sxs-lookup"><span data-stu-id="b622a-150">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="b622a-151">Дата: СР. 28 мая 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="b622a-151">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="b622a-152">Content-Length: 6305</span><span class="sxs-lookup"><span data-stu-id="b622a-152">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b622a-153">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="b622a-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="b622a-154">Если при использовании команды Test-CsMcxP2PIM происходит сбой, необходимо убедиться в том, что служба Mobility Service работает.</span><span class="sxs-lookup"><span data-stu-id="b622a-154">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="b622a-155">Это можно сделать с помощью веб-браузера, чтобы убедиться, что вы можете получить доступ к URL-адресу службы Mobility Service для пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b622a-155">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="b622a-156">Например, эта команда проверяет URL-адрес для пула atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b622a-156">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="b622a-157">Если служба Mobility Service работает, убедитесь в том, что у ваших двух тестовых пользователей есть действительные учетные записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b622a-157">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="b622a-158">Вы можете получить сведения об учетной записи с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b622a-158">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="b622a-159">Если свойство Enabled не равно true или если команда не выполнена, это означает, что у пользователя нет действительной учетной записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b622a-159">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="b622a-160">Кроме того, необходимо убедиться, что у пользователя включена поддержка мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="b622a-160">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="b622a-161">Для этого сначала определите политику мобильности, назначенную учетной записи:</span><span class="sxs-lookup"><span data-stu-id="b622a-161">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="b622a-162">После того как вы узнаете имя политики, используйте командлет Get-Ксмобилитиполици, чтобы убедиться, что для политики (например, Редмондмобилитиполици) задано значение true для свойства Енаблемобилити.</span><span class="sxs-lookup"><span data-stu-id="b622a-162">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="b622a-163">Если появляется сообщение об ошибке с заголовком проверки подлинности, это часто означает, что вы не указали действительной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b622a-163">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="b622a-164">Проверьте имя пользователя и пароль, а затем повторите проверку.</span><span class="sxs-lookup"><span data-stu-id="b622a-164">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="b622a-165">Если вы убедились в том, что учетная запись пользователя верна, используйте командлет Get-Ксвебсервицеконфигуратион и проверьте значение свойства Усевиндовсаус.</span><span class="sxs-lookup"><span data-stu-id="b622a-165">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="b622a-166">С помощью которого вы узнаете, какие методы проверки подлинности включены в вашей организации. Дополнительные советы по устранению неполадок со службой Mobility Service можно найти в [статье пошаговые инструкции по устранению неполадок, связанных с подключением к блогу внешних мобильных устройств Lync](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span><span class="sxs-lookup"><span data-stu-id="b622a-166">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

