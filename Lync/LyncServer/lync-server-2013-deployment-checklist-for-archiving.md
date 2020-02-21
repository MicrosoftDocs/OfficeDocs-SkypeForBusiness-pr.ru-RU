---
title: 'Lync Server 2013: контрольный список развертывания для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2df74bda74f1b9af01e1c4e73fa2f21b7119363f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b5bdd-102">Контрольный список развертывания для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5bdd-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5bdd-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b5bdd-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b5bdd-104">Архивация автоматически устанавливается на каждом сервере переднего плана в развертывании Lync Server 2013, но его необходимо настроить, прежде чем его можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="b5bdd-105">Приведенные в этом разделе действия по настройке составляют процесс развертывания функции архивации.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="b5bdd-106">Порядок развертывания</span><span class="sxs-lookup"><span data-stu-id="b5bdd-106">Deployment Sequence</span></span>

<span data-ttu-id="b5bdd-107">Настройка архивации зависит от выбранного параметра хранилища.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="b5bdd-108">Если вы используете интеграцию Microsoft Exchange для всех пользователей в развертывании, вам не нужно настраивать политики архивации Lync Server 2013 для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="b5bdd-109">Вместо этого настройте политики хранения на месте Exchange для поддержки архивации для пользователей, размещенных в Exchange 2013, с почтовыми ящиками, которые помещаются на удержание на месте.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b5bdd-110">Для получения дополнительных сведений о настройке этих политик обратитесь к документации по продукту Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="b5bdd-111">Если вы не используете интеграцию Microsoft Exchange для всех пользователей в развертывании, необходимо добавить базы данных архивации Lync Server (базы данных SQL Server) в топологию, а затем опубликовать ее, а также настроить политики и параметры для пользователей, прежде чем можно будет архивные данные для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="b5bdd-112">Базы данных архивации можно разворачивать одновременно с первоначальной топологией или после развертывания хотя бы одного пула переднего плана или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="b5bdd-113">В этом документе описывается порядок развертывания баз данных архивации путем добавления их в существующее развертывание.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="b5bdd-p104">При включении архивации в одном пуле переднего плана или сервере Standard Edition следует включить ее для всех других пулов переднего плана и серверов Standard Edition вашего развертывания. Это следует сделать, поскольку пользователи, чьи коммуникации требуется архивировать, могут быть приглашены в текстовую беседу или на собрания, размещаемые в другом пуле. Если там архивирование не включено, то сеанс может быть архивирован не полностью. В этих случаях мгновенные сообщения пользователей с включенной архивацией могут быть архивированы, но не для файлов содержимого конференций, а также событий присоединения и выхода из конференций.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b5bdd-118">Если в организации важна архивация в целях соответствия требованиям, не забудьте развернуть архивацию, настроить политики и другие параметры на соответствующем уровне и включить ее для всех соответствующих пользователей, прежде чем включать этих пользователей для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="b5bdd-119">Процесс развертывания архивации</span><span class="sxs-lookup"><span data-stu-id="b5bdd-119">Archiving Deployment Process</span></span>

<span data-ttu-id="b5bdd-120">В следующей таблице дается обзор действий, необходимых для развертывания архивации в существующей топологии.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5bdd-121">Этап</span><span class="sxs-lookup"><span data-stu-id="b5bdd-121">Phase</span></span></th>
<th><span data-ttu-id="b5bdd-122">Шаги</span><span class="sxs-lookup"><span data-stu-id="b5bdd-122">Steps</span></span></th>
<th><span data-ttu-id="b5bdd-123">Роли и членство в группах</span><span class="sxs-lookup"><span data-stu-id="b5bdd-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="b5bdd-124">Документация</span><span class="sxs-lookup"><span data-stu-id="b5bdd-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5bdd-125"><strong>Установка обязательного оборудования и программного обеспечения.</strong></span><span class="sxs-lookup"><span data-stu-id="b5bdd-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b5bdd-126">Чтобы использовать интеграцию с Microsoft Exchange (с помощью Exchange 2013 для хранения архивов для некоторых или всех пользователей), вам потребуется существующее развертывание Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="b5bdd-127">Чтобы использовать отдельные базы данных архивации (с применением баз данных SQL Server) для архивации хранилища, используемого частью пользователей или всеми пользователями, требуется SQL Server на сервере, на котором будут храниться данные архивации.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="b5bdd-p105">Архивация работает на серверах переднего плана корпоративного пула и на серверах Standard Edition. Для нее не существуют дополнительные требования к оборудованию или программному обеспечению помимо требований для установки этих серверов.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="b5bdd-130">Пользователь домена, являющийся членом локальной группы администраторов.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-131"><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="b5bdd-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="b5bdd-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="b5bdd-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Настройка систем и инфраструктуры для архивации в Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="b5bdd-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Поддержка интеграции Exchange Server и SharePoint в Lync server 2013</a> в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5bdd-136"><strong>Создание соответствующей внутренней топологии для поддержки архивации (только в том случае, если не используется интеграция Microsoft Exchange для всех пользователей в развертывании)</strong></span><span class="sxs-lookup"><span data-stu-id="b5bdd-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="b5bdd-137">Запустите построитель топологий, чтобы добавить базы данных архивации Lync Server 2013 (базы данных SQL Server) в топологию, а затем опубликуйте топологию.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-138">Чтобы определить топологию для включения баз данных архивации, требуется учетная запись члена локальной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="b5bdd-139">Чтобы опубликовать топологию, учетная запись, которая является членом группы администраторов домена и группы RTCUniversalServerAdmins, обладает разрешениями на полный доступ (чтение/запись/изменение) для общего файлового ресурса, который будет использоваться для хранилища файлов Lync Server 2013 (чтобы построитель топологии мог настроить требуемые списки DACL).</span><span class="sxs-lookup"><span data-stu-id="b5bdd-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Добавление баз данных архивации к существующему развертыванию Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5bdd-141"><strong>Настройка проверки подлинности "сервер-сервер" (только при использовании интеграции с Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="b5bdd-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="b5bdd-142">Настройка серверов для включения проверки подлинности между Lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="b5bdd-143">Рекомендуется запустить <strong>Test-ксексчанжесторажеконнективити testuser_sipUri – папка</strong> для проверки подключения к хранилищу архивации Exchange перед включением архивации.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-144">Учетная запись с соответствующими разрешениями для управления сертификатами на серверах.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync server 2013</a> в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5bdd-146"><strong>Настройка политик и конфигураций архивации</strong></span><span class="sxs-lookup"><span data-stu-id="b5bdd-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="b5bdd-147">Настройка архивации, в том числе сведения о том, следует ли использовать интеграцию с Microsoft Exchange, глобальную политику и политики сайтов и пользователей (при отсутствии интеграции с Microsoft Exchange для хранения данных) и определенных параметрах архивации, таких как критический режим и данные. экспорт и очистка.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="b5bdd-148">Если используется интеграция с Microsoft Exchange, настройте политики хранения на месте Exchange в соответствии с требованиями.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-149">Группа RTCUniversalServerAdmins (только Windows PowerShell) или назначение пользователям роли CSArchivingAdministrator или CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="b5bdd-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Настройка поддержки архивации в Lync Server 2013</a> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="b5bdd-151">Документация по продукту Exchange (при использовании интеграции с Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="b5bdd-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="b5bdd-152">Развертывание Lync Server и Microsoft Exchange в разных лесах</span><span class="sxs-lookup"><span data-stu-id="b5bdd-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="b5bdd-153">Если сервер Microsoft Exchange Server не развернут в том же лесу, что и Lync Server, необходимо убедиться, что следующие атрибуты Exchange Active Directory синхронизированы с лесом, в котором развернут сервер Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b5bdd-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="b5bdd-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b5bdd-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="b5bdd-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b5bdd-155">proxyAddresses</span></span>

<span data-ttu-id="b5bdd-p107">Это атрибут со множеством значений. При его синхронизации необходимо объединить значения, а не заменить их, чтобы текущие значения не были потеряны.</span><span class="sxs-lookup"><span data-stu-id="b5bdd-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

