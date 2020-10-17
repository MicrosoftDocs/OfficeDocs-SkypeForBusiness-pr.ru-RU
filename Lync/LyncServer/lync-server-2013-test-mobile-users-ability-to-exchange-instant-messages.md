---
title: 'Lync Server 2013: Протестируйте мобильные пользователи возможность обмениваться мгновенными сообщениями'
description: 'Lync Server 2013: Протестируйте мобильные пользователи возможность обмениваться мгновенными сообщениями.'
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
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558295"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a><span data-ttu-id="5c693-103">Проверка возможности мобильных пользователей обмениваться мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c693-103">Test mobile users' ability to exchange instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c693-104">_**Последнее изменение темы:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="5c693-104">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c693-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5c693-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5c693-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="5c693-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c693-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5c693-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5c693-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5c693-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c693-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5c693-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5c693-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5c693-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5c693-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxP2PIM.</span><span class="sxs-lookup"><span data-stu-id="5c693-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxP2PIM cmdlet.</span></span> <span data-ttu-id="5c693-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5c693-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5c693-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5c693-113">Description</span></span>

<span data-ttu-id="5c693-114">Служба Mobility Service позволяет пользователям мобильных устройств выполнять такие действия, как:</span><span class="sxs-lookup"><span data-stu-id="5c693-114">The Mobility Service enables mobile device users to do such things as:</span></span>

1.  <span data-ttu-id="5c693-115">Обмен мгновенными сообщениями и сведениями о присутствии Exchange.</span><span class="sxs-lookup"><span data-stu-id="5c693-115">Exchange instant messages and presence information.</span></span>

2.  <span data-ttu-id="5c693-116">Храните и извлекать голосовую почту внутренне, а не со своего поставщика услуг беспроводной связи.</span><span class="sxs-lookup"><span data-stu-id="5c693-116">Store and retrieve voice mail internally instead of with their wireless provider.</span></span>

3.  <span data-ttu-id="5c693-117">Используйте возможности Lync Server, такие как вызов с помощью конференц-связи по работе и удаленному доступу.</span><span class="sxs-lookup"><span data-stu-id="5c693-117">Take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing.</span></span>

<span data-ttu-id="5c693-118">Командлет Test-CsMxcP2PIM обеспечивает быстрый и простой способ проверки того, что пользователи могут использовать службу Mobility Service для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="5c693-118">The Test-CsMxcP2PIM cmdlet provides a quick and easy way to verify that users can use the Mobility Service to exchange instant messages.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5c693-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5c693-119">Running the test</span></span>

<span data-ttu-id="5c693-120">Чтобы выполнить этот тест, необходимо создать два объекта учетных данных Windows PowerShell (объекты, содержащие имя и пароль учетной записи) для каждой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="5c693-120">To run this test, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="5c693-121">Затем необходимо включить эти объекты учетных данных и SIP-адреса для двух учетных записей при вызове Test-CsMcxP2PIM:</span><span class="sxs-lookup"><span data-stu-id="5c693-121">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsMcxP2PIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="5c693-122">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .</span><span class="sxs-lookup"><span data-stu-id="5c693-122">For more information, see the help topic for the [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5c693-123">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="5c693-123">Determining success or failure</span></span>

<span data-ttu-id="5c693-124">Если два тестовых пользователя могут обмениваться мгновенными сообщениями с помощью службы Mobility Service, то Test-CsMcxP2PIM будет возвращать результат теста Success:</span><span class="sxs-lookup"><span data-stu-id="5c693-124">If the two test users can exchange instant messages by using the mobility service then Test-CsMcxP2PIM will return test result Success:</span></span>

<span data-ttu-id="5c693-125">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5c693-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5c693-126">Целевой URI: http://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="5c693-126">Target Uri : http://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="5c693-127">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="5c693-127">Result : Success</span></span>

<span data-ttu-id="5c693-128">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5c693-128">Latency : 00:00:00</span></span>

<span data-ttu-id="5c693-129">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="5c693-129">Error Message :</span></span>

<span data-ttu-id="5c693-130">Диагност</span><span class="sxs-lookup"><span data-stu-id="5c693-130">Diagnosis :</span></span>

<span data-ttu-id="5c693-131">В противном случае результат будет настроен на сбой, и будет выведено подробное сообщение об ошибке и диагностика:</span><span class="sxs-lookup"><span data-stu-id="5c693-131">If the test fails then the Result will be set to Failure and a detailed error message and diagnosis will be displayed:</span></span>

<span data-ttu-id="5c693-132">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5c693-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5c693-133">Целевой URI: https://atl-cs-001.litwareinc.com:443/mcx</span><span class="sxs-lookup"><span data-stu-id="5c693-133">Target Uri : https://atl-cs-001.litwareinc.com:443/mcx</span></span>

<span data-ttu-id="5c693-134">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="5c693-134">Result : Failure</span></span>

<span data-ttu-id="5c693-135">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5c693-135">Latency : 00:00:00</span></span>

<span data-ttu-id="5c693-136">Сообщение об ошибке: нет ответа, полученного для службы Web-Ticket.</span><span class="sxs-lookup"><span data-stu-id="5c693-136">Error Message : No response received for Web-Ticket service.</span></span>

<span data-ttu-id="5c693-137">Внутреннее исключение: запрос ХХТП не авторизован для</span><span class="sxs-lookup"><span data-stu-id="5c693-137">Inner Exception:The HHTP request is unauthorized with</span></span>

<span data-ttu-id="5c693-138">Схема согласования клиента "NTLM".</span><span class="sxs-lookup"><span data-stu-id="5c693-138">client negotiation scheme 'Ntlm'.</span></span> <span data-ttu-id="5c693-139">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="5c693-139">The authentication</span></span>

<span data-ttu-id="5c693-140">заголовку, полученному от сервера, является "Negotiate, NTLM".</span><span class="sxs-lookup"><span data-stu-id="5c693-140">header received from the server was 'Negotiate,NTLM'.</span></span>

<span data-ttu-id="5c693-141">Внутреннее исключение: удаленный сервер вернул ошибку:</span><span class="sxs-lookup"><span data-stu-id="5c693-141">Inner Exception:The remote server returned an error:</span></span>

<span data-ttu-id="5c693-142">(401) авторизация недоступна.</span><span class="sxs-lookup"><span data-stu-id="5c693-142">(401) Unauthorized.</span></span>

<span data-ttu-id="5c693-143">Диагност</span><span class="sxs-lookup"><span data-stu-id="5c693-143">Diagnosis :</span></span>

<span data-ttu-id="5c693-144">Внутренняя диагностика: X – MS $ Server – Фкдб: ATL – CS —</span><span class="sxs-lookup"><span data-stu-id="5c693-144">Inner Diagnosis:X-MS-server-Fqdb : atl-cs-</span></span>

<span data-ttu-id="5c693-145">001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5c693-145">001.litwareinc.com</span></span>

<span data-ttu-id="5c693-146">Cache-Control: Private</span><span class="sxs-lookup"><span data-stu-id="5c693-146">Cache-Control : private</span></span>

<span data-ttu-id="5c693-147">Content-Type: Text/HTML; charset = UTF – 8.</span><span class="sxs-lookup"><span data-stu-id="5c693-147">Content-Type : text/html; charset=utf-8.</span></span>

<span data-ttu-id="5c693-148">Сервер: Microsoft-IIS/8.5</span><span class="sxs-lookup"><span data-stu-id="5c693-148">Server : Microsoft-IIS/8.5</span></span>

<span data-ttu-id="5c693-149">WWW-Authenticate: Negotiate, NTLM</span><span class="sxs-lookup"><span data-stu-id="5c693-149">WWW-Authenticate : Negotiate,NTLM</span></span>

<span data-ttu-id="5c693-150">Питание от X: ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c693-150">X-Powered-By : ASP.NET</span></span>

<span data-ttu-id="5c693-151">X — Content – Type — параметры: параметр "пассивный прослушивание"</span><span class="sxs-lookup"><span data-stu-id="5c693-151">X-Content-Type-Options : nosniff</span></span>

<span data-ttu-id="5c693-152">Дата: среда, 28 мая 2014 19:16:05 GMT</span><span class="sxs-lookup"><span data-stu-id="5c693-152">Date : Wed, 28 May 2014 19:16:05 GMT</span></span>

<span data-ttu-id="5c693-153">Content — Length: 6305</span><span class="sxs-lookup"><span data-stu-id="5c693-153">Content-Length : 6305</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5c693-154">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5c693-154">Reasons why the test might have failed</span></span>

<span data-ttu-id="5c693-155">Если Test-CsMcxP2PIM не удается выполнить первый шаг, необходимо убедиться, что служба Mobility Service работает и работает.</span><span class="sxs-lookup"><span data-stu-id="5c693-155">If Test-CsMcxP2PIM fails your first step should be to verify that the mobility service is up and running.</span></span> <span data-ttu-id="5c693-156">Это можно сделать с помощью веб-браузера, чтобы проверить, что можно получить доступ к URL-адресу службы Mobility пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c693-156">That can be done by using a web browser to verify that the mobility service URL for your Lync Server pool can be accessed.</span></span> <span data-ttu-id="5c693-157">Например, эта команда проверяет URL-адрес пула atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="5c693-157">For example, this command verifies the URL for the pool atl-cs-001.litwareinc.com:</span></span>

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

<span data-ttu-id="5c693-158">Если служба Mobility Service работает, убедитесь, что у двух тестовых пользователей есть действительные учетные записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c693-158">If the mobility service seems to be running then verify that your two test users have valid Lync Server accounts.</span></span> <span data-ttu-id="5c693-159">Вы можете получить сведения об учетной записи с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5c693-159">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="5c693-160">Если свойство Enabled имеет значение, не равное true, или если команда завершается с ошибкой, то это означает, что у пользователя нет допустимой учетной записи Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5c693-160">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.</span></span>

<span data-ttu-id="5c693-161">Кроме того, необходимо убедиться, что для пользователя включена поддержка мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="5c693-161">You should also verify that the user is enabled for mobility.</span></span> <span data-ttu-id="5c693-162">Для этого сначала определите политику мобильности, назначенную учетной записи:</span><span class="sxs-lookup"><span data-stu-id="5c693-162">To do that, first determine the mobility policy that is assigned to the account:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

<span data-ttu-id="5c693-163">Зная имя политики, используйте командлет Get-CsMobilityPolicy, чтобы убедиться в том, что в рассматриваемой политике (например, Редмондмобилитиполици) свойство Енаблемобилити имеет значение true:</span><span class="sxs-lookup"><span data-stu-id="5c693-163">After you know the policy name, use the Get-CsMobilityPolicy cmdlet to verify that the policy in question (for example, RedmondMobilityPolicy) has the EnableMobility property set to True:</span></span>

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

<span data-ttu-id="5c693-164">Если отображается сообщение об ошибке с заголовками проверки подлинности, это часто означает, что вы не указали допустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c693-164">If you receive an error message with authentication headers, that often means that you have not specified a valid user account.</span></span> <span data-ttu-id="5c693-165">Проверьте имя пользователя и пароль, а затем повторите проверку.</span><span class="sxs-lookup"><span data-stu-id="5c693-165">Verify the user name and password and then try the test again.</span></span> <span data-ttu-id="5c693-166">Если вы убеждены, что учетная запись пользователя действительна, используйте командлет Get-CsWebServiceConfiguration и проверьте значение свойства Усевиндовсаус.</span><span class="sxs-lookup"><span data-stu-id="5c693-166">If you are convinced that the user account is valid, then use the Get-CsWebServiceConfiguration cmdlet and check the value of the UseWindowsAuth property.</span></span> <span data-ttu-id="5c693-167">, Покажет, какие методы проверки подлинности включены в вашей организации. Дополнительные советы по устранению неполадок в службе Mobility Service можно найти в статье блог [Устранение неполадок, связанных с подключением внешних мобильных устройств Lync, с](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)пошаговым выполнением.</span><span class="sxs-lookup"><span data-stu-id="5c693-167">That will tell you which authentication methods are enabled in your organization.For more tips about how to troubleshoot the mobility service, see the blog post [Troubleshooting External Lync Mobility Connectivity Issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

