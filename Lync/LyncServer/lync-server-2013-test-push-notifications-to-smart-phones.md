---
title: 'Lync Server 2013: тестирование push-уведомлений на смарт-телефоны'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 858c1ad3ad5776453a4a48505672c69083de1cc2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="7b549-102">Тестирование push-уведомлений на смарт-телефоны в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b549-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b549-103">_**Последнее изменение темы:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="7b549-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b549-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="7b549-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7b549-105">Monthly Channel</span><span class="sxs-lookup"><span data-stu-id="7b549-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b549-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="7b549-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7b549-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b549-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b549-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="7b549-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7b549-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7b549-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7b549-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="7b549-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="7b549-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b549-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7b549-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7b549-112">Description</span></span>

<span data-ttu-id="7b549-113">Служба push-уведомлений (Служба push-уведомлений Apple и Служба push-уведомлений Майкрософт) может отправлять уведомления о событиях, таких как новые мгновенные сообщения или новые голосовые сообщения, на мобильные устройства, такие как iPhone и Windows phones, даже если клиент Lync на этих устройствах в данный момент приостановлен или работает в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="7b549-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="7b549-114">Служба push-уведомлений — это облачная служба, которая работает на серверах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7b549-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="7b549-115">Чтобы воспользоваться преимуществами push-уведомлений, необходимо иметь возможность подключения и проверки подлинности с помощью расчетной палаты push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7b549-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="7b549-116">Командлет Test-CsMcxPushNotification позволяет администраторам проверять, могут ли запросы на push-уведомления маршрутизироваться через пограничный сервер в расчетную палату push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7b549-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7b549-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="7b549-117">Running the test</span></span>

<span data-ttu-id="7b549-118">Чтобы протестировать службу push-уведомлений, вызовите командлет Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="7b549-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="7b549-119">Убедитесь, что вы указали полное доменное имя пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="7b549-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="7b549-120">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="7b549-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7b549-121">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="7b549-121">Determining success or failure</span></span>

<span data-ttu-id="7b549-122">Если командлет Test-CsMcxPushNotification успешно выполнен, командлет вернет результат теста Success:</span><span class="sxs-lookup"><span data-stu-id="7b549-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="7b549-123">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7b549-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7b549-124">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="7b549-124">Result : Success</span></span>

<span data-ttu-id="7b549-125">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="7b549-125">Latency : 00:00:00</span></span>

<span data-ttu-id="7b549-126">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="7b549-126">Error :</span></span>

<span data-ttu-id="7b549-127">Диагност</span><span class="sxs-lookup"><span data-stu-id="7b549-127">Diagnosis :</span></span>

<span data-ttu-id="7b549-128">Если Test-CsMcxPushNotification не удается подключиться к расчетной палате push-уведомлений, командлет не возвращает тестовый результат сбоя.</span><span class="sxs-lookup"><span data-stu-id="7b549-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="7b549-129">Вместо этого команда обычно завершается с ошибками полностью.</span><span class="sxs-lookup"><span data-stu-id="7b549-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="7b549-130">Пример:</span><span class="sxs-lookup"><span data-stu-id="7b549-130">For example:</span></span>

<span data-ttu-id="7b549-131">Test-CsMcxPushNotification: ответ 504 (время ожидания сервера) получен от сети; операция завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="7b549-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="7b549-132">Для получения дополнительных сведений см. сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="7b549-132">See the exception details for more information.</span></span>

<span data-ttu-id="7b549-133">В строке: 1 символ: 27</span><span class="sxs-lookup"><span data-stu-id="7b549-133">At line:1 char:27</span></span>

<span data-ttu-id="7b549-134">\+Test-CsMcxPushNotification \< \< \< \< -акцесседжефкдн lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="7b549-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="7b549-135">\+Категоринфо: Оператионстоппед: (:) \[Test-CsMcxPushNotification\], фаилуререспонсиксцептион</span><span class="sxs-lookup"><span data-stu-id="7b549-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="7b549-136">\+Фулликуалифиедеррорид: Воркфловноткомплетед, Microsoft. RTC. Management. SyntheticTransactions. Тестмккспушнотификатионкмдлет</span><span class="sxs-lookup"><span data-stu-id="7b549-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7b549-137">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="7b549-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="7b549-138">Если происходит сбой службы push-уведомлений, которая обычно указывает на наличие проблем связи с пограничным сервером или проблем связи с клиринговой очисткой push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7b549-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="7b549-139">Если при выполнении командлета Test-CsMcxPushNotification возникли проблемы, необходимо убедиться, что пограничный сервер работает правильно.</span><span class="sxs-lookup"><span data-stu-id="7b549-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="7b549-140">Один из способов сделать это — использовать командлет Test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="7b549-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="7b549-141">Эта проверка проверяет, может ли указанный пользователь подключаться к пограничному серверу.</span><span class="sxs-lookup"><span data-stu-id="7b549-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="7b549-142">Если пограничный сервер работает правильно, это часто означает, что вы не можете подключиться к расчетной палате push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7b549-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="7b549-143">В свою очередь, обычно это означает, что вы неправильно настроили URI расчетной палаты или у вас нет записи SRV SRV, указывающей на этот URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="7b549-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="7b549-144">Можно проверить правильность значения параметра URI (sip:push@push.lync.com), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7b549-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="7b549-145">Если свойство Пушнотификатионпроксюри имеет значение, отличное от sip:push@push.lync.com, то эту проблему можно устранить с помощью командлета Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7b549-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="7b549-146">Например, эта команда правильно задает универсальный код ресурса (URI) для всей Организации:</span><span class="sxs-lookup"><span data-stu-id="7b549-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="7b549-147">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="7b549-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="7b549-148">Если универсальный код ресурса (URI) настроен правильно, необходимо убедиться, что у вас есть запись DNS SRV, которая разрешается в ваш домен SIP и пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="7b549-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="7b549-149">Дополнительные сведения о том, как настроить эти записи, можно найти в разделе Справка DNS требования для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="7b549-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="7b549-150">Обратите внимание, что следующее сообщение об ошибке обычно свидетельствует о проблеме с записями DNS:</span><span class="sxs-lookup"><span data-stu-id="7b549-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="7b549-151">От сети получен ответ 504 (время ожидания сервера), и операция завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="7b549-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="7b549-152">Для получения дополнительных сведений см. сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="7b549-152">See the exception details for more information.</span></span>

<span data-ttu-id="7b549-153">Кроме того, возможно, что Test-CsMcxConfiguration завершится со следующим сообщением об ошибке:</span><span class="sxs-lookup"><span data-stu-id="7b549-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="7b549-154">Test-CsMcxPushNotification: запрос на push-уведомление отклонен.</span><span class="sxs-lookup"><span data-stu-id="7b549-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="7b549-155">В строке: 1 символ: 27</span><span class="sxs-lookup"><span data-stu-id="7b549-155">At line:1 char:27</span></span>

<span data-ttu-id="7b549-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="7b549-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="7b549-157">\+Категоринфо: Оператионстоппед: (:) \[Test-CsMcxPushNotification\], синсетиктрансактионексцептион</span><span class="sxs-lookup"><span data-stu-id="7b549-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="7b549-158">\+Фулликуалифиедеррорид: Воркфловноткомплетед, Microsoft. RTC. Management. SyntheticTransactions. Тестмккспушнотификатионкмдлет</span><span class="sxs-lookup"><span data-stu-id="7b549-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="7b549-159">Сообщение "запрос на push-уведомление отклонено" обычно возникает, если включена фильтрация URL-адресов и блокируются префиксы http: и HTTPS:.</span><span class="sxs-lookup"><span data-stu-id="7b549-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="7b549-160">Определить, какие префиксы блокируются, можно с помощью команды, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="7b549-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="7b549-161">Если в результатах отображаются http: или HTTPS:, необходимо удалить их из списка заблокированных префиксов для работы push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7b549-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="7b549-162">Для этого можно использовать команды, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="7b549-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="7b549-163">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – ксимфилтерконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7b549-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

