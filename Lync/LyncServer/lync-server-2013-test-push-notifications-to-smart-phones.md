---
title: 'Lync Server 2013: тестирование push-уведомлений на смарт-телефоны'
description: 'Lync Server 2013: тестирование push-уведомлений на смарт-телефоны.'
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
ms.openlocfilehash: 4b92ef444a5331c9a673fd2db506631554e96eea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550845"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="04292-103">Тестирование push-уведомлений на смарт-телефоны в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04292-103">Test push notifications to smart phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04292-104">_**Последнее изменение темы:** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="04292-104">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04292-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="04292-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="04292-106">Monthly</span><span class="sxs-lookup"><span data-stu-id="04292-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04292-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="04292-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="04292-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04292-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04292-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="04292-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="04292-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="04292-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="04292-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="04292-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="04292-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="04292-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="04292-113">Описание</span><span class="sxs-lookup"><span data-stu-id="04292-113">Description</span></span>

<span data-ttu-id="04292-114">Служба push-уведомлений (Служба push-уведомлений Apple и Служба push-уведомлений Майкрософт) может отправлять уведомления о событиях, таких как новые мгновенные сообщения или новые голосовые сообщения, на мобильные устройства, такие как iPhone и Windows phones, даже если клиент Lync на этих устройствах в данный момент приостановлен или работает в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="04292-114">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="04292-115">Служба push-уведомлений — это облачная служба, которая работает на серверах Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="04292-115">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="04292-116">Чтобы воспользоваться преимуществами push-уведомлений, необходимо иметь возможность подключения и проверки подлинности с помощью расчетной палаты push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="04292-116">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="04292-117">Командлет Test-CsMcxPushNotification позволяет администраторам проверить, могут ли запросы на push-уведомления маршрутизироваться через пограничный сервер в расчетную палату push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="04292-117">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="04292-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="04292-118">Running the test</span></span>

<span data-ttu-id="04292-119">Чтобы протестировать службу push-уведомлений, вызовите командлет Test-CsMcxPushNotification.</span><span class="sxs-lookup"><span data-stu-id="04292-119">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="04292-120">Убедитесь, что вы указали полное доменное имя пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="04292-120">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="04292-121">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .</span><span class="sxs-lookup"><span data-stu-id="04292-121">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="04292-122">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="04292-122">Determining success or failure</span></span>

<span data-ttu-id="04292-123">Если Test-CsMcxPushNotification успешно, командлет вернет результат теста Success:</span><span class="sxs-lookup"><span data-stu-id="04292-123">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="04292-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="04292-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="04292-125">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="04292-125">Result : Success</span></span>

<span data-ttu-id="04292-126">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="04292-126">Latency : 00:00:00</span></span>

<span data-ttu-id="04292-127">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="04292-127">Error :</span></span>

<span data-ttu-id="04292-128">Диагност</span><span class="sxs-lookup"><span data-stu-id="04292-128">Diagnosis :</span></span>

<span data-ttu-id="04292-129">Если Test-CsMcxPushNotification не удается подключиться к расчетной палате push-уведомлений, командлет не будет возвращать тестовый результат сбоя.</span><span class="sxs-lookup"><span data-stu-id="04292-129">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="04292-130">Вместо этого команда обычно завершается с ошибками полностью.</span><span class="sxs-lookup"><span data-stu-id="04292-130">Instead the command will usually fail completely.</span></span> <span data-ttu-id="04292-131">Например:</span><span class="sxs-lookup"><span data-stu-id="04292-131">For example:</span></span>

<span data-ttu-id="04292-132">Test-CsMcxPushNotification: ответ 504 (время ожидания сервера) получен от сети; операция завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="04292-132">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="04292-133">Для получения дополнительных сведений см. сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="04292-133">See the exception details for more information.</span></span>

<span data-ttu-id="04292-134">В строке: 1 символ: 27</span><span class="sxs-lookup"><span data-stu-id="04292-134">At line:1 char:27</span></span>

<span data-ttu-id="04292-135">\+Test-CsMcxPushNotification \< \< \< \< акцесседжефкдн lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="04292-135">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="04292-136">\+ Категоринфо: Оператионстоппед: (:) \[ Test-CsMcxPushNotification \] , фаилуререспонсиксцептион</span><span class="sxs-lookup"><span data-stu-id="04292-136">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="04292-137">\+ Фулликуалифиедеррорид: Воркфловноткомплетед, Microsoft. RTC. Management. SyntheticTransactions. Тестмккспушнотификатионкмдлет</span><span class="sxs-lookup"><span data-stu-id="04292-137">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="04292-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="04292-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="04292-139">Если происходит сбой службы push-уведомлений, которая обычно указывает на наличие проблем связи с пограничным сервером или проблем связи с клиринговой очисткой push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="04292-139">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="04292-140">Если при выполнении командлета Test-CsMcxPushNotification возникли проблемы, необходимо убедиться, что пограничный сервер работает правильно.</span><span class="sxs-lookup"><span data-stu-id="04292-140">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="04292-141">Один из способов сделать это — использовать командлет Test-CsAVEdgeConnectivity:</span><span class="sxs-lookup"><span data-stu-id="04292-141">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="04292-142">Эта проверка проверяет, может ли указанный пользователь подключаться к пограничному серверу.</span><span class="sxs-lookup"><span data-stu-id="04292-142">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="04292-143">Если пограничный сервер работает правильно, это часто означает, что вы не можете подключиться к расчетной палате push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="04292-143">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="04292-144">В свою очередь, обычно это означает, что вы неправильно настроили URI расчетной палаты или у вас нет записи SRV SRV, указывающей на этот URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="04292-144">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="04292-145">Можно проверить правильность значения параметра URI (sip:push@push.lync.com), выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="04292-145">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="04292-146">Если свойство Пушнотификатионпроксюри имеет значение, отличное от sip:push@push.lync.com, то эту проблему можно устранить с помощью командлета Set-McxConfiguration.</span><span class="sxs-lookup"><span data-stu-id="04292-146">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="04292-147">Например, эта команда правильно задает универсальный код ресурса (URI) для всей Организации:</span><span class="sxs-lookup"><span data-stu-id="04292-147">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="04292-148">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="04292-148">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="04292-149">Если универсальный код ресурса (URI) настроен правильно, необходимо убедиться, что у вас есть запись DNS SRV, которая разрешается в ваш домен SIP и пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="04292-149">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="04292-150">Дополнительные сведения о том, как настроить эти записи, можно найти в разделе Справка DNS требования для мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="04292-150">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="04292-151">Обратите внимание, что следующее сообщение об ошибке обычно свидетельствует о проблеме с записями DNS:</span><span class="sxs-lookup"><span data-stu-id="04292-151">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="04292-152">От сети получен ответ 504 (время ожидания сервера), и операция завершилась неудачно.</span><span class="sxs-lookup"><span data-stu-id="04292-152">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="04292-153">Для получения дополнительных сведений см. сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="04292-153">See the exception details for more information.</span></span>

<span data-ttu-id="04292-154">Кроме того, может произойти сбой Test-CsMcxConfiguration с указанным сообщением об ошибке:</span><span class="sxs-lookup"><span data-stu-id="04292-154">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="04292-155">Test-CsMcxPushNotification: запрос на push-уведомление отклонен.</span><span class="sxs-lookup"><span data-stu-id="04292-155">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="04292-156">В строке: 1 символ: 27</span><span class="sxs-lookup"><span data-stu-id="04292-156">At line:1 char:27</span></span>

<span data-ttu-id="04292-157">\+ Test-CsMcxPushNotification \<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="04292-157">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="04292-158">\+ Категоринфо: Оператионстоппед: (:) \[ Test-CsMcxPushNotification \] , синсетиктрансактионексцептион</span><span class="sxs-lookup"><span data-stu-id="04292-158">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="04292-159">\+ Фулликуалифиедеррорид: Воркфловноткомплетед, Microsoft. RTC. Management. SyntheticTransactions. Тестмккспушнотификатионкмдлет</span><span class="sxs-lookup"><span data-stu-id="04292-159">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="04292-160">Сообщение "запрос на push-уведомление отклонено" обычно возникает, если включена фильтрация URL-адресов и блокируются префиксы http: и HTTPS:.</span><span class="sxs-lookup"><span data-stu-id="04292-160">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="04292-161">Определить, какие префиксы блокируются, можно с помощью команды, аналогичной следующей:</span><span class="sxs-lookup"><span data-stu-id="04292-161">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="04292-162">Если в результатах отображаются http: или HTTPS:, необходимо удалить их из списка заблокированных префиксов для работы push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="04292-162">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="04292-163">Для этого можно использовать команды, аналогичные следующим:</span><span class="sxs-lookup"><span data-stu-id="04292-163">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="04292-164">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – ксимфилтерконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).</span><span class="sxs-lookup"><span data-stu-id="04292-164">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

