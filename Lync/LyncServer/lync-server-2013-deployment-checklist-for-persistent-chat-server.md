---
title: 'Lync Server 2013: контрольный список развертывания для сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f0f3a-102">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0f3a-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0f3a-103">_**Тема последнего изменения:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f0f3a-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f0f3a-104">Развертывание Lync Server 2013, сервер сохраняемого чата требует его развертывания в правильной последовательности, и вы закончите все необходимые шаги по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="f0f3a-105">Последовательность развертывания</span><span class="sxs-lookup"><span data-stu-id="f0f3a-105">Deployment Sequence</span></span>

<span data-ttu-id="f0f3a-106">Вы можете развернуть сохраняемый сервер чата после развертывания начальной топологии, включая хотя бы один сервер Lync Server 2013, пул переднего плана или один сервер Lync Server 2013, Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="f0f3a-107">В этой статье описано, как развернуть сервер сохраняемого чата, добавив его в существующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="f0f3a-108">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="f0f3a-108">Deployment Process</span></span>

<span data-ttu-id="f0f3a-109">В следующей таблице перечислены основные шаги по развертыванию сервера сохраняемого чата и приведены ссылки на дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="f0f3a-110">Процесс развертывания сервера "сохраняемый чат"</span><span class="sxs-lookup"><span data-stu-id="f0f3a-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0f3a-111">Задача</span><span class="sxs-lookup"><span data-stu-id="f0f3a-111">Task</span></span></th>
<th><span data-ttu-id="f0f3a-112">Шаги</span><span class="sxs-lookup"><span data-stu-id="f0f3a-112">Steps</span></span></th>
<th><span data-ttu-id="f0f3a-113">Требуемые роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="f0f3a-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="f0f3a-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f0f3a-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0f3a-115"><strong>Установка необходимого оборудования и программного обеспечения</strong></span><span class="sxs-lookup"><span data-stu-id="f0f3a-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f3a-116">На оборудовании, удовлетворяющем требованиям, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="f0f3a-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0f3a-117">На серверах клиентского доступа на постоянной стороне сервера:</span><span class="sxs-lookup"><span data-stu-id="f0f3a-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="f0f3a-118">Операционная система, соответствующая требованиям</span><span class="sxs-lookup"><span data-stu-id="f0f3a-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-119">Требования к программному обеспечению для компьютеров с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0f3a-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-120">Сервер SQL Server, на котором будет размещаться база данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f0f3a-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="f0f3a-121">Если требуется соответствие требованиям сервера сохраняемого чата, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0f3a-122">Сервер SQL Server, на котором будет размещаться база данных соответствия требованиям сервера для обеспечения постоянной связи</span><span class="sxs-lookup"><span data-stu-id="f0f3a-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f0f3a-123">Любой пользователь, являющийся членом локальной группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="f0f3a-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-124"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="f0f3a-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="f0f3a-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="f0f3a-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="f0f3a-126"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0f3a-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f0f3a-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Технические требования для постоянного сервера чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f0f3a-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f3a-128"><strong>Создание соответствующей внутренней топологии для поддержки сохраняемого сервера чатов (и, при необходимости, сохранение соответствия в сохраняемом чате)</strong></span><span class="sxs-lookup"><span data-stu-id="f0f3a-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f3a-129">Запустите построитель топологии, чтобы добавить в топологию пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0f3a-130">Добавление серверных компонентов для временного чата в топологию</span><span class="sxs-lookup"><span data-stu-id="f0f3a-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-131">Создание базы данных SQL Server для сохраняемого хранилища сервера чатов (и резервного сервера SQL Server для восстановления с аварийным восстановлением)</span><span class="sxs-lookup"><span data-stu-id="f0f3a-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-132">Определение нового хранилища файлов Lync или использование существующего хранилища файлов Lync для файлов сервера чатов</span><span class="sxs-lookup"><span data-stu-id="f0f3a-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-133">Свяжите пул Lync Server 2013, который может перенаправлять запросы на этот пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="f0f3a-134">Если требуется соответствие с сохраняемым чатом:</span><span class="sxs-lookup"><span data-stu-id="f0f3a-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0f3a-135">Добавление магазина "соответствие требованиям" для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f0f3a-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-136">Чтобы включить соответствие требованиям, установите флажок "Определение пула серверов для постоянного чата".</span><span class="sxs-lookup"><span data-stu-id="f0f3a-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-137">Публикация топологии</span><span class="sxs-lookup"><span data-stu-id="f0f3a-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="f0f3a-138">Если вы установили сервер сохраняемого чата в стандартном выпуске, полное доменное имя (FQDN) пула сервера сохраняемого чата должно соответствовать стандартному серверу выпуска, а базы данных SQL Server — в экземпляре SQL Server Express на стандартном Выиздание сервера</span><span class="sxs-lookup"><span data-stu-id="f0f3a-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-139">Для определения топологии требуется учетная запись члена локальной группы "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="f0f3a-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="f0f3a-140">Чтобы опубликовать топологию, учетную запись, которая входит в группу "Администраторы домена" и группу Рткуниверсалсерверадминс, и пользователю также будут доступны разрешения на полный доступ (чтение/запись и изменение) в хранилище файлов Lync для файлов сервера чатов (чтобы Topology Builder мог настроить нужные DACL).</span><span class="sxs-lookup"><span data-stu-id="f0f3a-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление постоянного сервера чата в развертывание в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="f0f3a-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0f3a-142"><strong>Развертывание сервера сохраняемого чата</strong></span><span class="sxs-lookup"><span data-stu-id="f0f3a-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f3a-143">Запустите настройку Lync Server на всех компьютерах, на которых запущен сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="f0f3a-144">Настройка сервера "сохраняемый чат" интегрирована в мастер развертывания Lync Server 2013, который содержит указанные ниже инструкции.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0f3a-145">Развертывание локального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="f0f3a-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-146">Установка серверных служб сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f0f3a-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-147">Запрос и назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="f0f3a-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-148">Запуск и выполнение служб</span><span class="sxs-lookup"><span data-stu-id="f0f3a-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f0f3a-149">Любой пользователь, являющийся членом локальной группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="f0f3a-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Развертывание постоянного сервера чата в Lync server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="f0f3a-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f3a-151"><strong>Создание администратора сохраняемого чата</strong></span><span class="sxs-lookup"><span data-stu-id="f0f3a-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f3a-152">Добавьте пользователей в группу безопасности CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-153">Любой пользователь, являющийся членом группы "Администраторы домена"</span><span class="sxs-lookup"><span data-stu-id="f0f3a-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Добавление постоянного администратора чата в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="f0f3a-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0f3a-155"><strong>Настройка сервера сохраняемого сеанса беседы</strong></span><span class="sxs-lookup"><span data-stu-id="f0f3a-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f3a-156">Настройте пользователей:</span><span class="sxs-lookup"><span data-stu-id="f0f3a-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0f3a-157">Для доступа к сохраняемому серверу чата политика должна быть включена пользователем.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="f0f3a-158">По умолчанию политика отключена для всех пользователей и может быть определена в области Global/site/Pool/User.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="f0f3a-159">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="f0f3a-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f0f3a-p104">Пользователь должен быть членом группы CsPersistentChatAdministrator. Для изменения политики пользователь должен быть членом группы CsUserAdministrator (или группы с более высоким уровнем прав).</span><span class="sxs-lookup"><span data-stu-id="f0f3a-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="f0f3a-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Настройка сервера сохраняемого чата в Lync server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="f0f3a-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="f0f3a-163">Вы можете развернуть один или несколько пулов серверов для постоянного чата.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="f0f3a-164">Для обеспечения соответствия нормативным требованиям Корпорация Майкрософт поддерживает несколько пулов серверов постоянного чата, поскольку данные, созданные в данной стране, должны оставаться в этом регионе.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="f0f3a-165">Например, если вы разворачиваете пул серверов сохраняемого чата в Чикаго, а другой в Зурич для обеспечения соответствия требованиям к данным в Швейцарии, пользователи могут подключаться к комнатам как в случае, так и в пулах сервера сохраняемого чата, при условии, что они имеют доступ.</span><span class="sxs-lookup"><span data-stu-id="f0f3a-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

