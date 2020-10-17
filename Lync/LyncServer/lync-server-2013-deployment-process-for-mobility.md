---
title: 'Lync Server 2013: процесс развертывания для мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7d0e78cd4a8705178b3704a716846755d5c46f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514486"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Процесс развертывания для мобильной работы в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

В этом разделе описывается последовательность действий, необходимых для развертывания функции мобильной работы Lync Server 2013.

### <a name="mobility-deployment-process"></a>Процесс развертывания мобильности

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Действия</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Создание записей службы доменных имен (DNS)</p></td>
<td><ul>
<li><p>Создайте внутреннюю DNS-запись CNAME или A (узел, для IPv6 — AAAA) для разрешения внутреннего URL-адреса службы автообнаружения.</p></li>
<li><p>Создайте внешнюю DNS-запись CNAME или A (узел, для IPv6 — AAAA) для разрешения внешнего URL-адреса службы автообнаружения.</p></li>
</ul></td>
<td><p>Администраторы домена</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Создание DNS-записей для службы автообнаружения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Изменение сертификатов</p></td>
<td><p>Добавьте записи альтернативных имен субъектов в следующие сертификаты, чтобы обеспечить поддержку безопасных подключений для мобильных пользователей:</p>
<ul>
<li><p>Сертификат директора</p></li>
<li><p>Сертификат пула переднего плана</p></li>
<li><p>Сертификат обратного прокси-сервера</p></li>
</ul></td>
<td><p>Локальный администратор</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Изменение сертификатов для мобильных устройств в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка обратного прокси-сервера</p></td>
<td><ul>
<li><p>Назначьте сертификаты, обновленные с помощью альтернативных имен субъектов, в прослушиватель SSL.</p></li>
<li><p>Перенастройте правило веб-публикации для внешнего URL-адреса службы автообнаружения.</p></li>
<li><p>Убедитесь, что для внешнего URL-адреса веб-служб Lync Server 2013 в интерфейсном пуле существует правило веб-публикации.</p></li>
</ul>
<p>ИЛИ</p>
<ul>
<li><p>Если вы решили использовать HTTP для начального запроса автообнаружения и не обновлять списки альтернативных имен субъектов в сертификатах, настройте новое правило веб-публикации или перенастройте существующее правило публикации для порта 80 HTTP.</p></li>
</ul></td>
<td><p>Локальный администратор</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Тестирование развертывания Mobility Service для Lync 2010 Mobile с помощью службы Mobility MCX</p></td>
<td><p>Запустите <strong>Test-CsMcxP2PIM</strong>, чтобы протестировать отправку мгновенного сообщения от одного пользователя другому.</p>
<p>В документации по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> представлен полный список вариантов.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания мобильных устройств в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Тестирование развертывания мобильности для мобильных клиентов Lync 2013 с помощью веб-компонентов UCWA</p></td>
<td><p>Используйте командлет <strong>Test-CsUcwaConference</strong> для тестирования и проверки того, что предварительно определенные тестовые пользователи или пользователи могут использовать UCWA для создания и участия в Конференции.</p>
<p>В документации по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> представлен полный список вариантов.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания мобильных устройств в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка для использования push-уведомлений</p></td>
<td><ul>
<li><p>Для пограничных серверов Lync Server 2013 добавьте поставщик услуг хостинга Lync Server Online и настройте Федерацию поставщика услуг хостинга.</p></li>
<li><p>Для пограничных серверов Lync Server 2010 добавьте поставщик услуг хостинга Lync Server Online и настройте Федерацию поставщика услуг хостинга.</p></li>
<li><p>Для пограничных серверов Office Communications Server 2007 R2 добавьте федеративный партнер.</p></li>
<li><p>Если вы хотите обеспечить поддержку push-уведомлений через сеть Wi-Fi, настройте правило исходящего трафика в брандмауэре для порта TCP 5223.</p></li>
<li><p>Используйте командлет <strong>Set-CsPushNotificationConfiguration</strong>, чтобы разрешить push-уведомления для Apple Push Notification Service (APNS) и Microsoft Push Notification Service (MPNS). Эта функция отключена по умолчанию.</p></li>
<li><p>Используйте командлет <strong>Test-CsFederatedPartner</strong> для тестирования конфигурации федерации и командлет <strong>Test-CsMCXPushNotification</strong> для тестирования push-уведомлений.</p>
<div>

> [!NOTE]  
> Push-уведомления используются для мобильных клиентов Lync 2010 на устройствах Apple и Windows Phone<BR>Push-уведомления необходимо указывать для мобильных клиентов Lync 2013 только на Windows Phone


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Настройка для push-уведомлений в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка политики мобильности</p></td>
<td><p>Используйте командлет <strong>Set – CsMobilityPolicy</strong> , чтобы разрешить или запретить:</p>
<ul>
<li><p>Вызов с рабочего телефона</p></li>
<li><p>Включение IP-аудио-и видеоролика IP</p></li>
<li><p>Требовать WiFi для IP аудио и/или IP-видео</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Настройка политики мобильности в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

