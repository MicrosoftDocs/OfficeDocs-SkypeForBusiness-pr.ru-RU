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
ms.openlocfilehash: 6234ca4a8a0e7f6edc2069b7bb42f0bae545713b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="12e62-102">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e62-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e62-103">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="12e62-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="12e62-104">Развертывание Lync Server 2013, сервер сохраняемого чата необходимо развернуть в правильной последовательности и выполнить все необходимые действия по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="12e62-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="12e62-105">Порядок развертывания</span><span class="sxs-lookup"><span data-stu-id="12e62-105">Deployment Sequence</span></span>

<span data-ttu-id="12e62-106">Сервер сохраняемого чата можно развернуть после развертывания начальной топологии, в том числе по крайней мере один сервер Lync Server 2013, пул переднего плана или один сервер Lync Server 2013, Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="12e62-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="12e62-107">В этом разделе описывается, как развернуть сервер сохраняемого чата, добавив его в существующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="12e62-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="12e62-108">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="12e62-108">Deployment Process</span></span>

<span data-ttu-id="12e62-109">В следующей таблице приведены основные действия по развертыванию сервера сохраняемого чата и приведены ссылки на дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="12e62-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="12e62-110">Процесс развертывания сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e62-111">Задача</span><span class="sxs-lookup"><span data-stu-id="12e62-111">Task</span></span></th>
<th><span data-ttu-id="12e62-112">Шаги</span><span class="sxs-lookup"><span data-stu-id="12e62-112">Steps</span></span></th>
<th><span data-ttu-id="12e62-113">Требуемые роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="12e62-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="12e62-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="12e62-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e62-115"><strong>Установка необходимого оборудования и программного обеспечения</strong></span><span class="sxs-lookup"><span data-stu-id="12e62-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="12e62-116">На оборудовании, удовлетворяющем требованиям, установите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="12e62-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="12e62-117">На серверах переднего плана сервера сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="12e62-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="12e62-118">Операционная система, соответствующая требованиям</span><span class="sxs-lookup"><span data-stu-id="12e62-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="12e62-119">Необходимое программное обеспечение для компьютеров, на которых работает Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e62-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="12e62-120">SQL Server на сервере, на котором будет размещаться база данных сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="12e62-121">Если необходимо соответствие серверу сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="12e62-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="12e62-122">SQL Server на сервере, на котором будет размещаться база данных соответствия сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="12e62-123">Любой пользователь, являющийся членом локальной группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="12e62-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="12e62-124"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="12e62-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="12e62-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</span><span class="sxs-lookup"><span data-stu-id="12e62-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="12e62-126"><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="12e62-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="12e62-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Технические требования для сервера сохраняемого чата в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="12e62-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e62-128"><strong>Создание подходящей внутренней топологии для поддержки сервера сохраняемого чата (при необходимости — для обеспечения соответствия сохраняемого чата)</strong></span><span class="sxs-lookup"><span data-stu-id="12e62-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="12e62-129">Запустите построитель топологий, чтобы добавить в топологию пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="12e62-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="12e62-130">Добавление компонентов сервера сохраняемого чата в топологию</span><span class="sxs-lookup"><span data-stu-id="12e62-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="12e62-131">Создание базы данных SQL Server для хранилища сервера сохраняемого чата (и резервного сервера SQL Server для аварийного восстановления)</span><span class="sxs-lookup"><span data-stu-id="12e62-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="12e62-132">Определение нового хранилища файлов Lync или использование существующего хранилища файлов Lync для файлов сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="12e62-133">Связывание пула Lync Server 2013, который может маршрутизировать запросы к этому пулу серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="12e62-134">Если необходимо обеспечить соответствие требованиям сохраняемого чата:</span><span class="sxs-lookup"><span data-stu-id="12e62-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="12e62-135">Добавление хранилища соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="12e62-136">Установите флажок определение пула серверов сохраняемого чата, чтобы обеспечить соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="12e62-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="12e62-137">Опубликуйте топологию</span><span class="sxs-lookup"><span data-stu-id="12e62-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="12e62-138">Если сервер сохраняемого чата устанавливается на выпуск Standard Edition, полное доменное имя пула сервера сохраняемого чата должно отличаться от сервера Standard Edition, а базы данных SQL Server размещены в экземпляре SQL Server Express в стандартном Выпуск Server Edition</span><span class="sxs-lookup"><span data-stu-id="12e62-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="12e62-139">Для определения топологии требуется учетная запись члена локальной группы "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="12e62-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="12e62-140">Чтобы опубликовать топологию, учетная запись, которая является членом группы администраторов домена и группы RTCUniversalServerAdmins, также должна иметь разрешения на полный доступ (чтение/запись/изменение) в хранилище файлов Lync для файлов сервера сохраняемого чата (чтобы построитель топологии мог настроить требуемые списки DACL).</span><span class="sxs-lookup"><span data-stu-id="12e62-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="12e62-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="12e62-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e62-142"><strong>Развертывание сервера сохраняемого чата</strong></span><span class="sxs-lookup"><span data-stu-id="12e62-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="12e62-143">Запустите программу установки Lync Server на всех компьютерах, на которых работает сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="12e62-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="12e62-144">Установка сервера сохраняемого чата встроена в мастер развертывания Lync Server 2013, который предоставляет следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="12e62-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="12e62-145">Развертывание локального хранилища управления</span><span class="sxs-lookup"><span data-stu-id="12e62-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="12e62-146">Установка служб сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="12e62-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="12e62-147">Запрос и назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="12e62-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="12e62-148">Запуск и выполнение служб</span><span class="sxs-lookup"><span data-stu-id="12e62-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="12e62-149">Любой пользователь, являющийся членом локальной группы "Администраторы"</span><span class="sxs-lookup"><span data-stu-id="12e62-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="12e62-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Развертывание сервера сохраняемого чата в Lync server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="12e62-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e62-151"><strong>Создание администратора сохраняемого чата</strong></span><span class="sxs-lookup"><span data-stu-id="12e62-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="12e62-152">Добавьте пользователей в группу безопасности CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="12e62-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="12e62-153">Любой пользователь, являющийся членом группы "Администраторы домена"</span><span class="sxs-lookup"><span data-stu-id="12e62-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="12e62-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Добавление администратора сохраняемого чата в Lync Server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="12e62-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e62-155"><strong>Настройка сервера сохраняемого сеанса беседы</strong></span><span class="sxs-lookup"><span data-stu-id="12e62-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="12e62-156">Настройте пользователей:</span><span class="sxs-lookup"><span data-stu-id="12e62-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="12e62-157">Для доступа к серверу сохраняемого чата пользователь должен включить политику.</span><span class="sxs-lookup"><span data-stu-id="12e62-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="12e62-158">По умолчанию политика отключена для всех пользователей и может быть определена в области Global/site/Pool/User.</span><span class="sxs-lookup"><span data-stu-id="12e62-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="12e62-159">Настройка параметров</span><span class="sxs-lookup"><span data-stu-id="12e62-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="12e62-p104">Пользователь должен быть членом группы CsPersistentChatAdministrator. Для изменения политики пользователь должен быть членом группы CsUserAdministrator (или группы с более высоким уровнем прав).</span><span class="sxs-lookup"><span data-stu-id="12e62-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="12e62-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Настройка сервера сохраняемого чата в Lync server 2013</a> в документации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="12e62-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="12e62-163">Можно развернуть один или несколько пулов серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="12e62-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="12e62-164">Мы поддерживаем несколько пулов серверов сохраняемого чата в соответствии с нормативными соображениями, для которых требуется, чтобы данные, созданные в данной области, оставались в этой области.</span><span class="sxs-lookup"><span data-stu-id="12e62-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="12e62-165">Например, если вы разворачиваете пул серверов сохраняемого чата в Чикаго, а другой в Цюрихе для обеспечения соответствия нормативным требованиям для данных в Швейцарии, пользователи могут подключаться к комнатам в обоих пулах серверов сохраняемого чата, если они имеют доступ.</span><span class="sxs-lookup"><span data-stu-id="12e62-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

