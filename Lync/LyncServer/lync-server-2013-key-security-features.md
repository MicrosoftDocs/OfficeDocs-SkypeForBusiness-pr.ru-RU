---
title: 'Lync Server 2013: ключевые возможности безопасности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="e0ffd-102">Основные функции безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0ffd-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0ffd-103">_**Тема последнего изменения:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="e0ffd-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="e0ffd-104">Lync Server 2013 содержит несколько функций безопасности, включая проверку подлинности серверов, управление доступом на основе ролей и централизованное хранение данных конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="e0ffd-105">В этой статье содержится краткий обзор системы безопасности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="e0ffd-106">Основные функции безопасности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0ffd-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="e0ffd-107">Безопасность — чрезвычайно обширная тема.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-107">Security is a very broad topic.</span></span> <span data-ttu-id="e0ffd-108">Безопасность достигается во всех компонентах Lync Server 2013, а также баз данных, служб и оборудования, образующих экосистему Lync.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="e0ffd-109">В этой статье описаны некоторые возможности Lync Server 2013 в частности, разработанные для обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="e0ffd-110">Средства планирования и проектирования</span><span class="sxs-lookup"><span data-stu-id="e0ffd-110">Planning and Design Tools</span></span>

<span data-ttu-id="e0ffd-111">Lync Server 2013 предоставляет два средства для упрощения планирования и проектирования, а также для уменьшения вероятности ненужной настройки серверных компонентов Lync.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="e0ffd-112">**Средство планирования топологии** автоматизирует многие процессы разработки топологии.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="e0ffd-113">Вы можете экспортировать результаты из средства планирование в построитель топологии, который требуется для установки каждого сервера, на котором запущен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="e0ffd-114">**Построитель топологий** хранит все сведения о конфигурации в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="e0ffd-115">Подробнее об этих средствах можно найти в разделе [планирование для Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="e0ffd-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="e0ffd-116">Центральное хранилище управления</span><span class="sxs-lookup"><span data-stu-id="e0ffd-116">Central Management Store</span></span>

<span data-ttu-id="e0ffd-117">В Lync Server 2013 данные конфигурации серверов и служб входят в состав хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="e0ffd-118">Централизованное управление хранилищем обеспечивает устойчивое хранилище счематизед данных, необходимых для определения, настройки, обслуживания, администрирования, описания и работы с развертыванием Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="e0ffd-119">Кроме того, оно обеспечивает проверку этих данных на предмет внутренней согласованности.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="e0ffd-120">Все изменения данных конфигурации вносятся через центральное хранилище управления, что избавляет от проблем рассинхронизации.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="e0ffd-p104">Копии данных, доступные только для чтения, реплицируются на всех серверах топологии, включая пограничные серверы и устройства для обеспечения связи в филиалах. Репликацией управляет служба, которая по умолчанию работает в контексте сетевой службы с ограниченными правами и разрешениями, как у обычного пользователя компьютера.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-p104">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances. Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="e0ffd-123">Проверка подлинности "сервер-сервер"</span><span class="sxs-lookup"><span data-stu-id="e0ffd-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="e0ffd-124">В Lync Server 2013 можно настроить проверку подлинности между серверами с помощью протокола Open Authorization (OAuth).</span><span class="sxs-lookup"><span data-stu-id="e0ffd-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="e0ffd-125">Например, можно настроить сервер Lync Server 2013 для проверки подлинности на сервере, на котором запущен Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="e0ffd-126">С помощью протокола OAuth сервер Lync Server и Exchange Server могут доверять друг другу.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="e0ffd-127">Это обеспечивает прямой способ интеграции продуктов.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="e0ffd-128">Дополнительные сведения можно найти [в разделе Управление проверкой подлинности серверов (OAuth) и партнерским приложениям в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e0ffd-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="e0ffd-129">Управление с помощью Windows PowerShell и веб-интерфейс управления</span><span class="sxs-lookup"><span data-stu-id="e0ffd-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="e0ffd-130">Lync Server 2013 предоставляет мощный интерфейс управления, созданный в интерфейсе командной строки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="e0ffd-131">Он включает в себя командлеты для управления безопасностью, причем функции безопасности Windows PowerShell по умолчанию включены, чтобы пользователи не могли случайно или без усилий запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="e0ffd-132">То есть настройки программ по умолчанию помогают обеспечить максимальную безопасность и уменьшают число механизмов атаки.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="e0ffd-133">Подробные сведения о поддержке управления Windows PowerShell в Lync Server 2013 можно найти в [командной консоли Lync server 2013](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e0ffd-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="e0ffd-134">Управление доступом на основе ролей (RBAC)</span><span class="sxs-lookup"><span data-stu-id="e0ffd-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="e0ffd-135">Microsoft Lync Server 2013 предоставляет ролевые элементы управления доступом (RBAC), позволяющие делегировать задачи администрирования, обеспечивая высокий стандарт безопасности.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="e0ffd-136">С помощью RBAC можно реализовать принцип наименьших привилегий, при котором пользователям даются только те административные права, которые необходимы им для выполнения своих задач.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="e0ffd-137">Lync Server 2013 предоставляет возможность создавать новую роль, а также изменять существующую роль.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="e0ffd-138">Подробности можно найти [в разделе Планирование управления доступом на основе ролей в Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="e0ffd-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="e0ffd-139">Преобразование сетевых адресов (NAT)</span><span class="sxs-lookup"><span data-stu-id="e0ffd-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="e0ffd-140">Lync Server 2013 не поддерживает использование преобразования сетевых адресов (NAT) на внутреннем интерфейсе пограничного сервера, но оно поддерживает внешний интерфейс службы пограничного доступа, службы EDGE и службы EDGE на фоне маршрутизатор или брандмауэр, выполняющий трансляцию сетевых адресов (NAT) для одномерной и масштабируемой топологии пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="e0ffd-141">Несколько пограничных серверов, находящиеся за устройством балансировки нагрузки, не могут использовать NAT.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="e0ffd-142">Если NAT используется на внешних интерфейсах нескольких пограничных серверов, требуется балансировка нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="e0ffd-143">В свою очередь, балансировка нагрузки на DNS позволяет уменьшить число общедоступных IP-адресов, приходящихся на каждый пограничный сервер из пула пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="e0ffd-144">Подробности можно найти[в разделе Планирование доступа внешних пользователей в Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e0ffd-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0ffd-145">Если вы входите в федерацию с предприятиями, на которых развернут сервер Microsoft Office Communications Server 2007, и хотите использовать аудио- и видеосвязь между вашим и федеративным предприятием, требования к портам будут такими же, как и для развернутых старых версий пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="e0ffd-146">Например, диапазоны портов, необходимые для более ранних версий, должны быть открыты для обоих компаний, пока он не будет обновлен до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="e0ffd-147">После этого требования к портам можно будет пересмотреть и сократить в соответствии с новой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="e0ffd-148">Упрощенные сертификаты для пограничных серверов</span><span class="sxs-lookup"><span data-stu-id="e0ffd-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="e0ffd-149">Мастер развертывания может автоматически подставлять имена субъектов (SN) и альтернативные имена субъектов (SAN), уменьшая риск внесения ненужных и потенциально опасных записей.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="e0ffd-150">Жизненный цикл разработки безопасного ПО (SDL) защищенных информационных систем</span><span class="sxs-lookup"><span data-stu-id="e0ffd-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="e0ffd-151">Lync Server 2013 разработан и разработан в соответствии с требованиями жизненного цикла разработки системы безопасности (SDL), описанным в этой веб <http://go.microsoft.com/fwlink/?linkid=68761>-странице.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="e0ffd-152">**Заслуживает доверия**   . чтобы создать более безопасную объединенную систему обмена мгновенными сообщениями, необходимо разработать модели угроз и протестировать каждую функциональную возможность.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="e0ffd-153">Кроме того, Microsoft выполняет тестирование в нештатных ситуациях для поиска уязвимостей, обусловленных необычным поведением продукта.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="e0ffd-154">В процесс и практику программирования был внесен ряд усовершенствований, связанных с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="e0ffd-155">Переполнения буфера и другие угрозы безопасности обнаруживаются средствами разработки на этапе сборки, прежде чем код будет внесен в окончательную версию продукта.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="e0ffd-156">Разумеется, невозможно на стадии проектирования предотвратить все неизвестные угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="e0ffd-157">Никакая система не может гарантировать полной защиты.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-157">No system can guarantee complete security.</span></span> <span data-ttu-id="e0ffd-158">Однако благодаря тому, что разработка продуктов применяет принципы безопасного проектирования с начала, Lync Server 2013 включает в себя стандартные технологии безопасности, как фундаментальную часть ее архитектуры.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="e0ffd-159">**Заслуживает доверия**   по умолчанию, сетевая связь в Lync Server 2013 зашифрована.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="e0ffd-160">Поскольку все серверы используют сертификаты и проверки подлинности Kerberos, TLS, защищенный транспортный протокол в реальном времени (SRTP), а также другие отраслевые алгоритмы шифрования (в том числе 128-разрядное шифрование AES), практически все Lync Данные сервера защищены в сети.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="e0ffd-161">Кроме того, управление доступом на основе ролей делает возможным развертывание серверов с Lync Server 2013, так что каждая роль сервера запускает только службы и имеет только те разрешения, которые относятся к этим службам, которые подходят для роли сервера.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="e0ffd-162">**Надежная развертывание**   всех документов Lync Server 2013, в том числе рекомендации и рекомендации, которые помогут вам определить и настроить оптимальные уровни безопасности для развертывания и оценить риски, связанные с нестандартной активацией системы безопасности. Параметры.</span><span class="sxs-lookup"><span data-stu-id="e0ffd-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

