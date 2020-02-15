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
ms.openlocfilehash: 337e85520cb2a285f4e4743837aafa4136c89f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="148c9-102">Процесс развертывания для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148c9-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="148c9-103">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="148c9-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="148c9-104">В этом разделе описывается последовательность действий, необходимых для развертывания функции мобильной работы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="148c9-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="148c9-105">Процесс развертывания мобильности</span><span class="sxs-lookup"><span data-stu-id="148c9-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="148c9-106">Этап</span><span class="sxs-lookup"><span data-stu-id="148c9-106">Phase</span></span></th>
<th><span data-ttu-id="148c9-107">Шаги</span><span class="sxs-lookup"><span data-stu-id="148c9-107">Steps</span></span></th>
<th><span data-ttu-id="148c9-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="148c9-108">Permissions</span></span></th>
<th><span data-ttu-id="148c9-109">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="148c9-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="148c9-110">Создание записей службы доменных имен (DNS)</span><span class="sxs-lookup"><span data-stu-id="148c9-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="148c9-111">Создайте внутреннюю DNS-запись CNAME или A (узел, для IPv6 — AAAA) для разрешения внутреннего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="148c9-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="148c9-112">Создайте внешнюю DNS-запись CNAME или A (узел, для IPv6 — AAAA) для разрешения внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="148c9-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="148c9-113">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="148c9-113">Domain Admins</span></span></p>
<p><span data-ttu-id="148c9-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="148c9-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="148c9-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Создание DNS-записей для службы автообнаружения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="148c9-116">Изменение сертификатов</span><span class="sxs-lookup"><span data-stu-id="148c9-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="148c9-117">Добавьте записи альтернативных имен субъектов в следующие сертификаты, чтобы обеспечить поддержку безопасных подключений для мобильных пользователей:</span><span class="sxs-lookup"><span data-stu-id="148c9-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="148c9-118">Сертификат директора</span><span class="sxs-lookup"><span data-stu-id="148c9-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="148c9-119">Сертификат пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="148c9-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="148c9-120">Сертификат обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="148c9-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="148c9-121">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="148c9-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="148c9-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Изменение сертификатов для мобильных устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="148c9-123">Настройка обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="148c9-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="148c9-124">Назначьте сертификаты, обновленные с помощью альтернативных имен субъектов, в прослушиватель SSL.</span><span class="sxs-lookup"><span data-stu-id="148c9-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="148c9-125">Перенастройте правило веб-публикации для внешнего URL-адреса службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="148c9-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="148c9-126">Убедитесь, что для внешнего URL-адреса веб-служб Lync Server 2013 в интерфейсном пуле существует правило веб-публикации.</span><span class="sxs-lookup"><span data-stu-id="148c9-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="148c9-127">или</span><span class="sxs-lookup"><span data-stu-id="148c9-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="148c9-128">Если вы решили использовать HTTP для начального запроса автообнаружения и не обновлять списки альтернативных имен субъектов в сертификатах, настройте новое правило веб-публикации или перенастройте существующее правило публикации для порта 80 HTTP.</span><span class="sxs-lookup"><span data-stu-id="148c9-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="148c9-129">Локальный администратор</span><span class="sxs-lookup"><span data-stu-id="148c9-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="148c9-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="148c9-131">Тестирование развертывания Mobility Service для Lync 2010 Mobile с помощью службы Mobility MCX</span><span class="sxs-lookup"><span data-stu-id="148c9-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="148c9-132">Запустите <strong>Test-CsMcxP2PIM</strong>, чтобы протестировать отправку мгновенного сообщения от одного пользователя другому.</span><span class="sxs-lookup"><span data-stu-id="148c9-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="148c9-133">В документации по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> представлен полный список вариантов.</span><span class="sxs-lookup"><span data-stu-id="148c9-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="148c9-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="148c9-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="148c9-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания мобильных устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="148c9-136">Тестирование развертывания мобильности для мобильных клиентов Lync 2013 с помощью веб-компонентов UCWA</span><span class="sxs-lookup"><span data-stu-id="148c9-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="148c9-137">Используйте командлет <strong>Test-CsUcwaConference</strong> для тестирования и проверки того, что предварительно определенные тестовые пользователи или пользователи могут использовать UCWA для создания и участия в Конференции.</span><span class="sxs-lookup"><span data-stu-id="148c9-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="148c9-138">В документации по командлету командной консоли Lync Server для <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> представлен полный список вариантов.</span><span class="sxs-lookup"><span data-stu-id="148c9-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="148c9-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="148c9-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="148c9-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Проверка развертывания мобильных устройств в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="148c9-141">Настройка для использования push-уведомлений</span><span class="sxs-lookup"><span data-stu-id="148c9-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="148c9-142">Для пограничных серверов Lync Server 2013 добавьте поставщик услуг хостинга Lync Server Online и настройте Федерацию поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="148c9-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="148c9-143">Для пограничных серверов Lync Server 2010 добавьте поставщик услуг хостинга Lync Server Online и настройте Федерацию поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="148c9-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="148c9-144">Для пограничных серверов Office Communications Server 2007 R2 добавьте федеративный партнер.</span><span class="sxs-lookup"><span data-stu-id="148c9-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="148c9-145">Если вы хотите обеспечить поддержку push-уведомлений через сеть Wi-Fi, настройте правило исходящего трафика в брандмауэре для порта TCP 5223.</span><span class="sxs-lookup"><span data-stu-id="148c9-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="148c9-146">Используйте командлет <strong>Set-CsPushNotificationConfiguration</strong>, чтобы разрешить push-уведомления для Apple Push Notification Service (APNS) и Microsoft Push Notification Service (MPNS).</span><span class="sxs-lookup"><span data-stu-id="148c9-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="148c9-147">Эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="148c9-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="148c9-148">Используйте командлет <strong>Test-CsFederatedPartner</strong> для тестирования конфигурации федерации и командлет <strong>Test-CsMCXPushNotification</strong> для тестирования push-уведомлений.</span><span class="sxs-lookup"><span data-stu-id="148c9-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="148c9-149">Push-уведомления используются для мобильных клиентов Lync 2010 на устройствах Apple и Windows Phone</span><span class="sxs-lookup"><span data-stu-id="148c9-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="148c9-150">Push-уведомления необходимо указывать для мобильных клиентов Lync 2013 только на Windows Phone</span><span class="sxs-lookup"><span data-stu-id="148c9-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="148c9-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="148c9-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="148c9-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Настройка для push-уведомлений в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="148c9-153">Настройка политики мобильности</span><span class="sxs-lookup"><span data-stu-id="148c9-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="148c9-154">Используйте командлет <strong>Set – CsMobilityPolicy</strong> , чтобы разрешить или запретить:</span><span class="sxs-lookup"><span data-stu-id="148c9-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="148c9-155">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="148c9-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="148c9-156">Включение IP-аудио-и видеоролика IP</span><span class="sxs-lookup"><span data-stu-id="148c9-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="148c9-157">Требовать WiFi для IP аудио и/или IP-видео</span><span class="sxs-lookup"><span data-stu-id="148c9-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="148c9-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="148c9-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="148c9-159"><a href="lync-server-2013-configuring-mobility-policy.md">Настройка политики мобильности в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="148c9-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

