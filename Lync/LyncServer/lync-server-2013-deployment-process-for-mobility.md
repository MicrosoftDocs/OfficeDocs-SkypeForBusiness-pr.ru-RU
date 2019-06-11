---
title: 'Lync Server 2013: процесс развертывания для организации мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec6f1e089a9418db3d8ece1f390615226687cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Процесс развертывания для организации мобильной работы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

В этом разделе описывается последовательность действий, необходимых для развертывания функции Lync Server 2013 Mobility.

### <a name="mobility-deployment-process"></a>Процесс развертывания для мобильных устройств

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
<th>Шаги</th>
<th>Разрешения</th>
<th>Документация по развертыванию</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Создание записей DNS (Domain Name System)</p></td>
<td><ul>
<li><p>Создайте внутреннюю запись DNS CNAME или A (Host, если IPv6, AAAA) для разрешения URL-адреса внутренней службы автообнаружения.</p></li>
<li><p>Создайте внешнюю запись DNS CNAME или (Host, если IPv6, AAAA) для разрешения внешнего URL-адреса службы автообнаружения.</p></li>
</ul></td>
<td><p>Администраторы домена</p>
<p>Днсадминс</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Создание DNS-записей для службы автообнаружения в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Изменение сертификатов</p></td>
<td><p>Добавьте записи альтернативного имени субъекта в следующие сертификаты для поддержки безопасных подключений для мобильных пользователей:</p>
<ul>
<li><p>Сертификат директора</p></li>
<li><p>Сертификат пула на стороне переднего плана</p></li>
<li><p>Обратный сертификат прокси-сервера</p></li>
</ul></td>
<td><p>Локальный администратор</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Изменение сертификатов для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка обратного прокси-сервера</p></td>
<td><ul>
<li><p>Назначьте сертификаты, обновленные с помощью альтернативных имен субъектов, в прослушиватель SSL (Secure Sockets Layer).</p></li>
<li><p>Измените параметры правила веб-публикации для внешнего URL-адреса службы автообнаружения.</p></li>
<li><p>Убедитесь, что для внешнего URL-адреса служб Lync Server 2013 в пуле переднего плана существует правило веб-публикации.</p></li>
</ul>
<p>Или</p>
<ul>
<li><p>Если вы решили использовать HTTP для начального запроса автообнаружения и не обновили списки альтернативных имен субъектов в сертификатах, настройте новое правило публикации веб-публикации или перенастройте существующее правило для порта 80 HTTP.</p></li>
</ul></td>
<td><p>Локальный администратор</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Проверка развертывания Mobility Service для Lync 2010 Mobile с помощью службы Mobility МККС</p></td>
<td><p>Запустите <strong>Test-CsMcxP2PIM</strong> , чтобы протестировать отправку мгновенного сообщения от одного пользователя другому.</p>
<p>Ознакомьтесь с документацией по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> , чтобы просмотреть полный список вариантов.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания среды для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Проверка развертывания Mobility Service для мобильных клиентов Lync 2013 с помощью веб-компонентов УКВА</p></td>
<td><p>С помощью командлета <strong>Test-ксукваконференце</strong> вы можете протестировать и проверить, что предварительно определенные пользователи теста и пользователи могут использовать Уква для создания Конференции и участия в ней.</p>
<p>Ознакомьтесь с документацией по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-ксукваконференце</a> , чтобы просмотреть полный список вариантов.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания среды для мобильной работы в Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Настройка для использования push-уведомлений</p></td>
<td><ul>
<li><p>На серверах пограничного сервера Lync Server 2013 добавьте поставщик услуг размещения Lync Server Online и настройте Федерацию поставщика услуг размещения.</p></li>
<li><p>На серверах пограничного сервера Lync Server 2010 добавьте поставщик услуг размещения Lync Server Online и настройте Федерацию поставщика услуг размещения.</p></li>
<li><p>Для пограничного сервера Office Communications Server 2007 R2 добавьте федеративного партнера.</p></li>
<li><p>Если вы хотите, чтобы в сети Wi-Fi поддерживались извещающие уведомления, настройте исходящие правила брандмауэра для порта TCP 5223.</p></li>
<li><p>Используйте командлет <strong>Set-кспушнотификатионконфигуратион</strong> , чтобы включить извещающие уведомления в службу push-уведомлений Apple (APNs) и службу push-уведомлений Майкрософт (MPNS). Эта функция отключена по умолчанию.</p></li>
<li><p>С помощью командлета <strong>Test-ксфедератедпартнер</strong> можно протестировать конфигурацию Федерации и командлет <strong>Test-ксмккспушнотификатион</strong> для проверки извещающих уведомлений.</p>
<div>

> [!NOTE]  
> Push-уведомления используются для мобильных клиентов Lync 2010 на устройствах Apple и Windows Phone<BR>Push-уведомление требуется для мобильных клиентов Lync 2013 только на Windows Phone


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Настройка для использования push-уведомлений в Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Настройка политики мобильности</p></td>
<td><p>Используйте командлет <strong>Set-ксмобилитиполици</strong> , чтобы разрешить или запретить.</p>
<ul>
<li><p>Вызов с рабочего телефона</p></li>
<li><p>Включение IP-звука и IP-видео</p></li>
<li><p>Требуется WiFi для IP и/или IP-видео</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Настройка политики мобильных устройств в Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

