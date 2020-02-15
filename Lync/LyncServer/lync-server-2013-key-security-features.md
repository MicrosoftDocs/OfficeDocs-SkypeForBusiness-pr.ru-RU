---
title: 'Lync Server 2013: ключевые функции безопасности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2662225ac8aa00383b38deec3825a6f26b9dd9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="20fe4-102">Ключевые функции безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20fe4-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20fe4-103">_**Последнее изменение темы:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="20fe4-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="20fe4-104">Lync Server 2013 включает несколько функций безопасности, включая проверку подлинности между серверами, управление доступом на основе ролей и централизованное хранение данных конфигурации.</span><span class="sxs-lookup"><span data-stu-id="20fe4-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="20fe4-105">В этой статье представлен высокоуровневый обзор системы безопасности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20fe4-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="20fe4-106">Ключевые функции безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20fe4-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="20fe4-107">Безопасность это очень широкий раздел.</span><span class="sxs-lookup"><span data-stu-id="20fe4-107">Security is a very broad topic.</span></span> <span data-ttu-id="20fe4-108">Безопасность достигает всех функций Lync Server 2013, а также баз данных, служб и оборудования, которые составляют экосистему Lync.</span><span class="sxs-lookup"><span data-stu-id="20fe4-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="20fe4-109">В этой статье описываются некоторые функции Lync Server 2013, предназначенные для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="20fe4-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="20fe4-110">Средства планирования и создания</span><span class="sxs-lookup"><span data-stu-id="20fe4-110">Planning and Design Tools</span></span>

<span data-ttu-id="20fe4-111">Lync Server 2013 предоставляет два средства для упрощения планирования и оформления, а также для снижения вероятности ненужной настройки компонентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20fe4-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="20fe4-112">**Средство планирования топологии** автоматизирует значительную часть процесса создания топологии.</span><span class="sxs-lookup"><span data-stu-id="20fe4-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="20fe4-113">Вы можете экспортировать результаты из средства планирования в построитель топологий, который является средством, необходимым для установки каждого сервера, на котором работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20fe4-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="20fe4-114">В **построителе топологий** хранятся все сведения о конфигурации в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="20fe4-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="20fe4-115">Подробнее об этих средствах можно узнать в статье [планирование для Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="20fe4-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="20fe4-116">Центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="20fe4-116">Central Management Store</span></span>

<span data-ttu-id="20fe4-117">В Lync Server 2013 данные конфигурации о серверах и службах являются частью центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="20fe4-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="20fe4-118">Центральное хранилище управления предоставляет надежное хранилище схематизированные данных, необходимое для определения, настройки, обслуживания, администрирования, описания и работы с развертыванием Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20fe4-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="20fe4-119">Оно также проверяет данные, чтобы обеспечить согласованность конфигурации.</span><span class="sxs-lookup"><span data-stu-id="20fe4-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="20fe4-120">Все изменения данных конфигурации происходят в центральном хранилище управления, устраняя проблемы, связанные с несинхронизированными.</span><span class="sxs-lookup"><span data-stu-id="20fe4-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="20fe4-121">Копии данных, доступные только для чтения, реплицируются на все серверы в топологии, включая пограничные серверы и устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="20fe4-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="20fe4-122">Репликация управляется службой, которая по умолчанию работает в контексте сетевой службы, уменьшая права и разрешения для простого пользователя на компьютере.</span><span class="sxs-lookup"><span data-stu-id="20fe4-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="20fe4-123">Проверка подлинности между серверами</span><span class="sxs-lookup"><span data-stu-id="20fe4-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="20fe4-124">В Lync Server 2013 можно настроить проверку подлинности между серверами с помощью протокола Open Authorization (OAuth).</span><span class="sxs-lookup"><span data-stu-id="20fe4-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="20fe4-125">Например, можно настроить Lync Server 2013 для проверки подлинности на сервере под управлением Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20fe4-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="20fe4-126">С помощью протокола OAuth сервер Lync Server и сервер Exchange Server могут доверять друг другу.</span><span class="sxs-lookup"><span data-stu-id="20fe4-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="20fe4-127">Это дает возможность беспрепятственно интегрировать продукты.</span><span class="sxs-lookup"><span data-stu-id="20fe4-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="20fe4-128">Дополнительные сведения см [в статье Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="20fe4-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="20fe4-129">Веб-интерфейс управления и управления на основе Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20fe4-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="20fe4-130">Lync Server 2013 предоставляет мощный интерфейс управления, основанный на интерфейсе командной строки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20fe4-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="20fe4-131">Он включает в себя командлеты для управления безопасностью, а функции безопасности Windows PowerShell включены по умолчанию, чтобы пользователи не могли легко или непреднамеренно запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="20fe4-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="20fe4-132">Это означает, что по умолчанию для программ установки по умолчанию автоматически обеспечивается максимальная безопасность и снижается вероятность атаки.</span><span class="sxs-lookup"><span data-stu-id="20fe4-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="20fe4-133">Подробные сведения о поддержке управления Windows PowerShell в Lync Server 2013 приведены в статье [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="20fe4-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="20fe4-134">Управление доступом на основе ролей (RBAC)</span><span class="sxs-lookup"><span data-stu-id="20fe4-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="20fe4-135">Microsoft Lync Server 2013 предоставляет управление доступом на основе ролей (RBAC), чтобы можно было делегировать административные задачи, сохраняя при этом высокие стандарты безопасности.</span><span class="sxs-lookup"><span data-stu-id="20fe4-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="20fe4-136">С помощью RBAC можно придерживаться принципа "минимальных прав", в котором пользователям предоставляются только административные права, необходимые для их работы.</span><span class="sxs-lookup"><span data-stu-id="20fe4-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="20fe4-137">Lync Server 2013 содержит возможность создания новой роли, а также возможность изменения существующей роли.</span><span class="sxs-lookup"><span data-stu-id="20fe4-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="20fe4-138">Подробные сведения см. [в статье Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="20fe4-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="20fe4-139">Преобразование сетевых адресов (NAT)</span><span class="sxs-lookup"><span data-stu-id="20fe4-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="20fe4-140">Lync Server 2013 не поддерживает использование преобразования сетевых адресов (NAT) на внутреннем интерфейсе пограничного сервера, но он поддерживает размещение внешнего интерфейса пограничной службы доступа, пограничной службы веб-конференций и пограничной службы аудио-и видеоданных на маршрутизаторе или брандмауэре, который выполняет преобразование сетевых адресов (NAT) как для одной, так и для масштабируемой консолидированной пограничной серверной топологии.</span><span class="sxs-lookup"><span data-stu-id="20fe4-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="20fe4-141">Несколько пограничных серверов под аппаратным подсистемой балансировки нагрузки не могут использовать NAT.</span><span class="sxs-lookup"><span data-stu-id="20fe4-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="20fe4-142">Если несколько пограничных серверов используют NAT на внешних интерфейсах, балансировка нагрузки для системы доменных имен (DNS) необходима.</span><span class="sxs-lookup"><span data-stu-id="20fe4-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="20fe4-143">В свою очередь, использование балансировки нагрузки на DNS позволяет сократить количество общедоступных IP-адресов на пограничный сервер в пуле пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="20fe4-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="20fe4-144">Дополнительные сведения см[в разделе Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="20fe4-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20fe4-145">Если вы участвуете в работе с предприятиями с развертыванием Microsoft Office Communications Server 2007 и вам нужно использовать аудио/видео между предприятием и федеративным предприятием, то требования к портам будут такими, как для более ранней версии развернутых пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="20fe4-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="20fe4-146">Например, диапазоны портов, необходимые для этих более ранних версий, должны быть открыты для обоих компаний, пока федеративный партнер не обновит пограничные серверы до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20fe4-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="20fe4-147">В это время требования к портам можно просматривать и сокращать в соответствии с новой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="20fe4-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="20fe4-148">Упрощенные сертификаты для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="20fe4-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="20fe4-149">Мастер развертывания может автоматически заполнять имена субъектов (Sn) и альтернативные имена субъектов (SAN), уменьшая возможность включения ненужных и потенциально небезопасных записей.</span><span class="sxs-lookup"><span data-stu-id="20fe4-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="20fe4-150">Жизненный цикл разработки безопасности для защищенных информационных компьютеров (SDL)</span><span class="sxs-lookup"><span data-stu-id="20fe4-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="20fe4-151">Lync Server 2013 разработан и разрабатывался в соответствии с жизненным циклом разработки безопасности (SDL), который описан в статье <http://go.microsoft.com/fwlink/?linkid=68761>.</span><span class="sxs-lookup"><span data-stu-id="20fe4-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="20fe4-152">**Заслуживает доверия**. для создания более безопасной единой системы обмена мгновенными сообщениями необходимо разработать модели угроз и проверить каждую функциональную возможность.   </span><span class="sxs-lookup"><span data-stu-id="20fe4-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="20fe4-153">Кроме того, корпорация Майкрософт выполняет тестирование вне разработанного поведения для обнаружения уязвимостей системы безопасности, вызванных непредвиденным поведением продукта.</span><span class="sxs-lookup"><span data-stu-id="20fe4-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="20fe4-154">Различные улучшения, связанные с обеспечением безопасности, были включены в технологический процесс разработки исходного кода.</span><span class="sxs-lookup"><span data-stu-id="20fe4-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="20fe4-155">Средства времени сборки обнаруживают переполнения буфера и другие потенциальные угрозы безопасности до возврата кода в конечный продукт.</span><span class="sxs-lookup"><span data-stu-id="20fe4-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="20fe4-156">Разумеется, невозможно разработать все неизвестные угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="20fe4-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="20fe4-157">Ни одна система не может гарантировать полную безопасность.</span><span class="sxs-lookup"><span data-stu-id="20fe4-157">No system can guarantee complete security.</span></span> <span data-ttu-id="20fe4-158">Тем не менее, так как разработка продуктов применяет принципы безопасного проектирования от начального, Lync Server 2013 включает в себя стандартные технологии безопасности, являющиеся основной частью архитектуры.</span><span class="sxs-lookup"><span data-stu-id="20fe4-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="20fe4-159">**Заслуживает доверия по умолчанию**   при шифровании сетевых коммуникаций в Lync Server 2013 шифруются.</span><span class="sxs-lookup"><span data-stu-id="20fe4-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="20fe4-160">Так как все серверы используют сертификаты и проверку подлинности Kerberos, TLS, защищенный транспортный протокол реального времени (SRTP), а также другие отраслевые методы шифрования, в том числе 128-разрядное шифрование AES, практически все Lync Данные сервера защищены в сети.</span><span class="sxs-lookup"><span data-stu-id="20fe4-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="20fe4-161">Кроме того, управление доступом на основе ролей позволяет развернуть серверы, на которых работает Lync Server 2013, чтобы каждая роль сервера выполняла только службы, а также разрешения, связанные с этими службами, которые подходят для роли сервера.</span><span class="sxs-lookup"><span data-stu-id="20fe4-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="20fe4-162">**Заслуживает доверия**   все документация по Lync Server 2013 содержит рекомендации и рекомендации по определению и настройке оптимальных уровней безопасности для развертывания и оценивать риски безопасности при активации параметров, отличных от параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="20fe4-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

