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
ms.openlocfilehash: 06684665819e14540628e5cd45309ef2c920b227
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Тестирование push-уведомлений на смарт-телефоны в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-03-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Расписание проверки</p></td>
<td><p>Monthly Channel</p></td>
</tr>
<tr class="even">
<td><p>Средство тестирования</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Необходимые разрешения</p></td>
<td><p>При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</p>
<p>При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsMcxPushNotification. Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Описание

Служба push-уведомлений (Служба push-уведомлений Apple и Служба push-уведомлений Майкрософт) может отправлять уведомления о событиях, таких как новые мгновенные сообщения или новые голосовые сообщения, на мобильные устройства, такие как iPhone и Windows phones, даже если клиент Lync на этих устройствах в данный момент приостановлен или работает в фоновом режиме. Служба push-уведомлений — это облачная служба, которая работает на серверах Майкрософт. Чтобы воспользоваться преимуществами push-уведомлений, необходимо иметь возможность подключения и проверки подлинности с помощью расчетной палаты push-уведомлений. Командлет Test-CsMcxPushNotification позволяет администраторам проверять, могут ли запросы на push-уведомления маршрутизироваться через пограничный сервер в расчетную палату push-уведомлений.

</div>

<div>

## <a name="running-the-test"></a>Выполнение теста

Чтобы протестировать службу push-уведомлений, вызовите командлет Test-CsMcxPushNotification. Убедитесь, что вы указали полное доменное имя пограничного сервера:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Определение успешности или сбоя

Если командлет Test-CsMcxPushNotification успешно выполнен, командлет вернет результат теста Success:

TargetFqdn: atl-cs-001.litwareinc.com

Результат: успешное выполнение

Задержка: 00:00:00

Ошибкой

Диагност

Если Test-CsMcxPushNotification не удается подключиться к расчетной палате push-уведомлений, командлет не возвращает тестовый результат сбоя. Вместо этого команда обычно завершается с ошибками полностью. Например:

Test-CsMcxPushNotification: ответ 504 (время ожидания сервера) получен от сети; операция завершилась неудачно. Для получения дополнительных сведений см. сведения об исключении.

В строке: 1 символ: 27

\+Test-CsMcxPushNotification \< \< \< \< -акцесседжефкдн lyncedge.mydomain.com

\+Категоринфо: Оператионстоппед: (:) \[Test-CsMcxPushNotification\], фаилуререспонсиксцептион

\+Фулликуалифиедеррорид: Воркфловноткомплетед, Microsoft. RTC. Management. SyntheticTransactions. Тестмккспушнотификатионкмдлет

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Причины, по которым может произойти сбой теста

Если происходит сбой службы push-уведомлений, которая обычно указывает на наличие проблем связи с пограничным сервером или проблем связи с клиринговой очисткой push-уведомлений. Если при выполнении командлета Test-CsMcxPushNotification возникли проблемы, необходимо убедиться, что пограничный сервер работает правильно. Один из способов сделать это — использовать командлет Test-CsAVEdgeConnectivity:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Эта проверка проверяет, может ли указанный пользователь подключаться к пограничному серверу.

Если пограничный сервер работает правильно, это часто означает, что вы не можете подключиться к расчетной палате push-уведомлений. В свою очередь, обычно это означает, что вы неправильно настроили URI расчетной палаты или у вас нет записи SRV SRV, указывающей на этот URL-адрес. Можно проверить правильность значения параметра URI (sip:push@push.lync.com), выполнив следующую команду:

    Get-CsMcxConfiguration

Если свойство Пушнотификатионпроксюри имеет значение, отличное от sip:push@push.lync.com, то эту проблему можно устранить с помощью командлета Set-McxConfiguration. Например, эта команда правильно задает универсальный код ресурса (URI) для всей Организации:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Если универсальный код ресурса (URI) настроен правильно, необходимо убедиться, что у вас есть запись DNS SRV, которая разрешается в ваш домен SIP и пограничный сервер. Дополнительные сведения о том, как настроить эти записи, можно найти в разделе Справка DNS требования для мобильных устройств. Обратите внимание, что следующее сообщение об ошибке обычно свидетельствует о проблеме с записями DNS:

От сети получен ответ 504 (время ожидания сервера), и операция завершилась неудачно. Для получения дополнительных сведений см. сведения об исключении.

Кроме того, возможно, что Test-CsMcxConfiguration завершится со следующим сообщением об ошибке:

Test-CsMcxPushNotification: запрос на push-уведомление отклонен.

В строке: 1 символ: 27

\+Test-CsMcxPushNotification\<\<\<\<

\+Категоринфо: Оператионстоппед: (:) \[Test-CsMcxPushNotification\], синсетиктрансактионексцептион

\+Фулликуалифиедеррорид: Воркфловноткомплетед, Microsoft. RTC. Management. SyntheticTransactions. Тестмккспушнотификатионкмдлет

Сообщение "запрос на push-уведомление отклонено" обычно возникает, если включена фильтрация URL-адресов и блокируются префиксы http: и HTTPS:. Определить, какие префиксы блокируются, можно с помощью команды, аналогичной следующей:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Если в результатах отображаются http: или HTTPS:, необходимо удалить их из списка заблокированных префиксов для работы push-уведомлений. Для этого можно использовать команды, аналогичные следующим:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – ксимфилтерконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

