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

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="1aad8-102">Процесс развертывания для организации мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aad8-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aad8-103">_**Тема последнего изменения:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="1aad8-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="1aad8-104">В этом разделе описывается последовательность действий, необходимых для развертывания функции Lync Server 2013 Mobility.</span><span class="sxs-lookup"><span data-stu-id="1aad8-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="1aad8-105">Процесс развертывания для мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="1aad8-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1aad8-106">Этап</span><span class="sxs-lookup"><span data-stu-id="1aad8-106">Phase</span></span></th>
<th><span data-ttu-id="1aad8-107">Шаги</span><span class="sxs-lookup"><span data-stu-id="1aad8-107">Steps</span></span></th>
<th><span data-ttu-id="1aad8-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1aad8-108">Permissions</span></span></th>
<th><span data-ttu-id="1aad8-109">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="1aad8-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1aad8-110">Создание записей DNS (Domain Name System)</span><span class="sxs-lookup"><span data-stu-id="1aad8-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1aad8-111">Создайте внутреннюю запись DNS CNAME или A (Host, если IPv6, AAAA) для разрешения URL-адреса внутренней службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="1aad8-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-112">Создайте внешнюю запись DNS CNAME или (Host, если IPv6, AAAA) для разрешения внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="1aad8-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1aad8-113">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="1aad8-113">Domain Admins</span></span></p>
<p><span data-ttu-id="1aad8-114">Днсадминс</span><span class="sxs-lookup"><span data-stu-id="1aad8-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="1aad8-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Создание DNS-записей для службы автообнаружения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1aad8-116">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="1aad8-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="1aad8-117">Добавьте записи альтернативного имени субъекта в следующие сертификаты для поддержки безопасных подключений для мобильных пользователей:</span><span class="sxs-lookup"><span data-stu-id="1aad8-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="1aad8-118">Сертификат директора</span><span class="sxs-lookup"><span data-stu-id="1aad8-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="1aad8-119">Сертификат пула на стороне переднего плана</span><span class="sxs-lookup"><span data-stu-id="1aad8-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="1aad8-120">Обратный сертификат прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="1aad8-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1aad8-121">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="1aad8-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="1aad8-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Изменение сертификатов для мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1aad8-123">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="1aad8-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1aad8-124">Назначьте сертификаты, обновленные с помощью альтернативных имен субъектов, в прослушиватель SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="1aad8-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-125">Измените параметры правила веб-публикации для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="1aad8-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-126">Убедитесь, что для внешнего URL-адреса служб Lync Server 2013 в пуле переднего плана существует правило веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="1aad8-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="1aad8-127">Или</span><span class="sxs-lookup"><span data-stu-id="1aad8-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="1aad8-128">Если вы решили использовать HTTP для начального запроса автообнаружения и не обновили списки альтернативных имен субъектов в сертификатах, настройте новое правило публикации веб-публикации или перенастройте существующее правило для порта 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="1aad8-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1aad8-129">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="1aad8-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="1aad8-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1aad8-131">Проверка развертывания Mobility Service для Lync 2010 Mobile с помощью службы Mobility МККС</span><span class="sxs-lookup"><span data-stu-id="1aad8-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="1aad8-132">Запустите <strong>Test-CsMcxP2PIM</strong> , чтобы протестировать отправку мгновенного сообщения от одного пользователя другому.</span><span class="sxs-lookup"><span data-stu-id="1aad8-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="1aad8-133">Ознакомьтесь с документацией по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> , чтобы просмотреть полный список вариантов.</span><span class="sxs-lookup"><span data-stu-id="1aad8-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="1aad8-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1aad8-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1aad8-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания среды для мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1aad8-136">Проверка развертывания Mobility Service для мобильных клиентов Lync 2013 с помощью веб-компонентов УКВА</span><span class="sxs-lookup"><span data-stu-id="1aad8-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="1aad8-137">С помощью командлета <strong>Test-ксукваконференце</strong> вы можете протестировать и проверить, что предварительно определенные пользователи теста и пользователи могут использовать Уква для создания Конференции и участия в ней.</span><span class="sxs-lookup"><span data-stu-id="1aad8-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="1aad8-138">Ознакомьтесь с документацией по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-ксукваконференце</a> , чтобы просмотреть полный список вариантов.</span><span class="sxs-lookup"><span data-stu-id="1aad8-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="1aad8-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1aad8-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1aad8-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания среды для мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1aad8-141">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="1aad8-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1aad8-142">На серверах пограничного сервера Lync Server 2013 добавьте поставщик услуг размещения Lync Server Online и настройте Федерацию поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="1aad8-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-143">На серверах пограничного сервера Lync Server 2010 добавьте поставщик услуг размещения Lync Server Online и настройте Федерацию поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="1aad8-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-144">Для пограничного сервера Office Communications Server 2007 R2 добавьте федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="1aad8-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-145">Если вы хотите, чтобы в сети Wi-Fi поддерживались извещающие уведомления, настройте исходящие правила брандмауэра для порта TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="1aad8-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-146">Используйте командлет <strong>Set-кспушнотификатионконфигуратион</strong> , чтобы включить извещающие уведомления в службу push-уведомлений Apple (APNs) и службу push-уведомлений Майкрософт (MPNS).</span><span class="sxs-lookup"><span data-stu-id="1aad8-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="1aad8-147">Эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1aad8-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="1aad8-148">С помощью командлета <strong>Test-ксфедератедпартнер</strong> можно протестировать конфигурацию Федерации и командлет <strong>Test-ксмккспушнотификатион</strong> для проверки извещающих уведомлений.</span><span class="sxs-lookup"><span data-stu-id="1aad8-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1aad8-149">Push-уведомления используются для мобильных клиентов Lync 2010 на устройствах Apple и Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1aad8-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="1aad8-150">Push-уведомление требуется для мобильных клиентов Lync 2013 только на Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1aad8-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="1aad8-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1aad8-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1aad8-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Настройка для использования push-уведомлений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1aad8-153">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="1aad8-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="1aad8-154">Используйте командлет <strong>Set-ксмобилитиполици</strong> , чтобы разрешить или запретить.</span><span class="sxs-lookup"><span data-stu-id="1aad8-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="1aad8-155">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="1aad8-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="1aad8-156">Включение IP-звука и IP-видео</span><span class="sxs-lookup"><span data-stu-id="1aad8-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="1aad8-157">Требуется WiFi для IP и/или IP-видео</span><span class="sxs-lookup"><span data-stu-id="1aad8-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1aad8-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1aad8-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1aad8-159"><a href="lync-server-2013-configuring-mobility-policy.md">Настройка политики мобильных устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1aad8-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

