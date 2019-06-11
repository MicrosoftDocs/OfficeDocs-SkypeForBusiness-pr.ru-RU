---
title: Процесс развертывания для интеграции локальной системы обработки сообщений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="a932c-102">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a932c-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a932c-103">_**Тема последнего изменения:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="a932c-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="a932c-104">Если вы хотите интегрировать единую систему обмена сообщениями Exchange с Lync Server 2013, необходимо выполнить задачи, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a932c-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="a932c-105">Также убедитесь в том, что вы просматриваете рекомендации по планированию и развертыванию, описанные в [руководстве по интеграции локальной системы обработки сообщений и Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="a932c-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="a932c-106">В этой статье предполагается, что вы развернули сервер Lync Server 2013 с размещенным сервером исправлений, и что вы включили пользователей для Lync Server 2013, но не обязательно выполнять все действия по развертыванию и настройке для включения корпоративной голосовой связи. описано в разделе [Развертывание корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="a932c-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="a932c-107">Процесс интеграции единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="a932c-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="a932c-108">Важно скоординировать администраторов Exchange вашей организации, чтобы подтвердить задачи, которые они будут выполнять для обеспечения успешной интеграции.</span><span class="sxs-lookup"><span data-stu-id="a932c-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a932c-109">Этап</span><span class="sxs-lookup"><span data-stu-id="a932c-109">Phase</span></span></th>
<th><span data-ttu-id="a932c-110">Шаги</span><span class="sxs-lookup"><span data-stu-id="a932c-110">Steps</span></span></th>
<th><span data-ttu-id="a932c-111">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="a932c-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="a932c-112">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="a932c-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a932c-113">Выполните развертывание одного из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="a932c-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-114">Microsoft Exchange Server 2007 с пакетом обновления 1 (SP2) или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="a932c-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="a932c-115">Microsoft Exchange Server 2010 или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="a932c-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="a932c-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="a932c-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a932c-117">Если вы используете Microsoft Exchange Server 2013, установите следующие роли Exchange Server в одном лесу или другом лесе в качестве Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a932c-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-118">клиентский доступ;</span><span class="sxs-lookup"><span data-stu-id="a932c-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="a932c-119">почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a932c-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="a932c-120">Если Microsoft Exchange Server 2013 и единая система обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange таким образом, чтобы он доверял лесу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a932c-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="a932c-121">Если вы используете Exchange 2010, установите следующие роли Exchange Server либо в том же лесе, либо в другом лесе в составе Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a932c-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-122">единая система обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="a932c-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="a932c-123">транспортный сервер-концентратор;</span><span class="sxs-lookup"><span data-stu-id="a932c-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="a932c-124">клиентский доступ;</span><span class="sxs-lookup"><span data-stu-id="a932c-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="a932c-125">почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a932c-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="a932c-126">Если в разных лесах установлено приложение Lync Server 2013 и единая система обмена сообщениями Exchange (UM), настройте каждый лес Exchange таким образом, чтобы он доверял лесу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a932c-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="a932c-127">Администраторы предприятия (если это первый сервер Exchange Server в организации)</span><span class="sxs-lookup"><span data-stu-id="a932c-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="a932c-128">-ИЛИ-</span><span class="sxs-lookup"><span data-stu-id="a932c-128">-OR-</span></span></p>
<p><span data-ttu-id="a932c-129">Администратор организации Exchange (если это не первый сервер Exchange Server в организации)</span><span class="sxs-lookup"><span data-stu-id="a932c-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="a932c-130">Изучите соответствующую документацию для своей версии Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="a932c-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="a932c-131">Документация по развертыванию Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 по адресу.</span><span class="sxs-lookup"><span data-stu-id="a932c-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="a932c-132">Документация по развертыванию пакета обновления для Exchange Server 2010 <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>или последней версии.</span><span class="sxs-lookup"><span data-stu-id="a932c-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="a932c-133">Microsoft Exchange Server 2013 <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>: планирование и развертывание.</span><span class="sxs-lookup"><span data-stu-id="a932c-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a932c-134">Установите сертификаты.</span><span class="sxs-lookup"><span data-stu-id="a932c-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="a932c-135">Скачайте и установите сертификаты для каждого сервера UM Exchange в доверенном корневом центре сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="a932c-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="a932c-136">Сертификаты необходимы для взаимной защиты на уровне транспорта (MTLS) между серверами, на которых запущены службы Exchange UM и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a932c-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="a932c-137">Администраторы</span><span class="sxs-lookup"><span data-stu-id="a932c-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="a932c-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="a932c-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a932c-139">Создайте и настройте новую абонентскую группу Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="a932c-140">На сервере Exchange UM Создайте абонентскую группу SIP, основываясь на конкретных требованиях к развертыванию вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a932c-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="a932c-141">Администратор организации Exchange</span><span class="sxs-lookup"><span data-stu-id="a932c-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="a932c-142">Для Exchange 2007 SP1 или новейшего пакета обновления ознакомьтесь &quot;со сведениями о том, как создать универсальный код&quot; ресурса <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>(URI) для единой системы обмена сообщениями в.</span><span class="sxs-lookup"><span data-stu-id="a932c-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="a932c-143">2010 или более поздней версии пакета обновления можно &quot;найти&quot; в <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>разделе Создание абонентской группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="a932c-144">Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a932c-145">Настройте параметры безопасности для абонентской группы Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="a932c-146">Чтобы зашифровать голосовой трафик для предприятия, настройте параметры безопасности в абонентской группе Exchange UM с помощью <strong>SIP Secure</strong> или <strong>Secure</strong>.</span><span class="sxs-lookup"><span data-stu-id="a932c-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="a932c-147">Это особенно важный шаг, если вы развернули или планируете развертывание устройств Lync Phone Edition в своей среде.</span><span class="sxs-lookup"><span data-stu-id="a932c-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="a932c-148">Для функционирования устройств Lync Phone Edition в среде с интегрированной функцией интегрированной системы обмена сообщениями, параметры шифрования Lync Server должны быть согласованы с параметрами безопасности для абонентской группы Exchange.</span><span class="sxs-lookup"><span data-stu-id="a932c-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="a932c-149">For details, refer to the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="a932c-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="a932c-150">Администратор организации Exchange</span><span class="sxs-lookup"><span data-stu-id="a932c-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="a932c-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a932c-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a932c-152">2007 и более поздних версий пакета обновления можно найти в статье:</span><span class="sxs-lookup"><span data-stu-id="a932c-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="a932c-153">&quot;Настройка безопасности для абонентской группы единой системы обмена&quot; сообщениями <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>по адресу.</span><span class="sxs-lookup"><span data-stu-id="a932c-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="a932c-154">Для Exchange 2010 или более поздней версии пакета обновления см. также следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="a932c-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="a932c-155">&quot;Настройте безопасность VoIP для абонентской группы&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="a932c-156">Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a932c-157">Добавьте серверы единой системы обмена сообщениями в абонентскую группу Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="a932c-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span><span class="sxs-lookup"><span data-stu-id="a932c-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="a932c-159">В этом случае добавьте сервер в абонентскую группу Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="a932c-160">Администраторы</span><span class="sxs-lookup"><span data-stu-id="a932c-160">Administrators</span></span></p>
<p><span data-ttu-id="a932c-161">Администраторы Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a932c-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="a932c-162">Инструкции по добавлению сервера единой системы обмена сообщениями &quot;в телефонную группу&quot; для Exchange 2007 SP1 или новейшего <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>пакета обновления.</span><span class="sxs-lookup"><span data-stu-id="a932c-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="a932c-163">Для Exchange 2010 или новейшего пакета обновления ознакомьтесь &quot;со сведениями Просмотр и Настройка свойств сервера&quot; UM. <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a></span><span class="sxs-lookup"><span data-stu-id="a932c-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="a932c-164">Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a932c-165">Настройте SIP-адреса для почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="a932c-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="a932c-166">Назначьте адреса SIP почтовым ящикам пользователей корпоративной голосовой связи, которые будут использовать возможности Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="a932c-167">Администратор Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a932c-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="a932c-168">Администратор получателей Exchange</span><span class="sxs-lookup"><span data-stu-id="a932c-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="a932c-169">В <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>Exchange 2007 с пакетом обновления 1 (SP1 &quot;или более поздней версии) Узнайте, как добавить, удалить или изменить адрес SIP для&quot; пользователя с поддержкой UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="a932c-170">Для Exchange 2010 или новейшего пакета обновления ознакомьтесь &quot;со сведениями в <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>разделе Изменение адреса SIP для пользователя&quot; с поддержкой UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="a932c-171">Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a932c-172">Запустите скрипт exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="a932c-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="a932c-173">На сервере с запущенными службами Exchange UM откройте командную консоль Exchange и запустите сценарий ексчукутил. ps1, который выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a932c-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-174">Предоставляет Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory для Exchange UM, а именно, абонентские группы SIP, созданные в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="a932c-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="a932c-175">Создает объект шлюза для единой системы обмена сообщениями в службе каталогов Active Directory для каждого пула Lync Server 2013 Enterprise Edition или Standard Edition Server, на котором размещаются пользователи, поддерживающие корпоративную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="a932c-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="a932c-176">Создает группу слежения UM для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="a932c-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="a932c-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span><span class="sxs-lookup"><span data-stu-id="a932c-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="a932c-178">These need to be mapped 1:1 if there is more than one dial plan.</span><span class="sxs-lookup"><span data-stu-id="a932c-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a932c-179">Администратор организации Exchange</span><span class="sxs-lookup"><span data-stu-id="a932c-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="a932c-180">Администратор получателей Exchange</span><span class="sxs-lookup"><span data-stu-id="a932c-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="a932c-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a932c-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a932c-182">Настройте абонентские группы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a932c-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="a932c-183">Если вы интегрируется с Exchange 2007 с пакетом обновления 1 (SP1) или более поздним пакетом обновления или Exchange 2010, создайте новый план голосовой коммутируемой телефонной связи с именем, совпадающим с полным доменным именем Exchange для абонентского плана.</span><span class="sxs-lookup"><span data-stu-id="a932c-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="a932c-184">Это потребуется сделать для каждой абонентской группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="a932c-185">Если вы интегрируется с Exchange 2010 с пакетом обновления 1 (SP1), убедитесь в том, что настроены подходящие планы глобальных абонентов или уровней сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="a932c-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="a932c-186">При интеграции с Exchange 2010 с пакетом обновления 1 (SP1) абонентская группа Lync Server и имена абонентских групп UM Exchange не должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="a932c-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="a932c-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a932c-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a932c-188"><a href="lync-server-2013-configuring-dial-plans.md">Настройка абонентских групп в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a932c-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a932c-189">Запустите средство интеграции единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="a932c-190">На Lync Server 2013 запустите <strong>оксумутил. exe</strong>, который:</span><span class="sxs-lookup"><span data-stu-id="a932c-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-191">создает объекты контактов абонентского доступа и автосекретаря;</span><span class="sxs-lookup"><span data-stu-id="a932c-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="a932c-192">Проверка наличия корпоративной телефонной группы с именем, совпадающим с полным доменным планом Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="a932c-193">Если вы используете Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии, имена абонентской группы не должны совпадать, и вы можете пропустить предупреждение этого средства.</span><span class="sxs-lookup"><span data-stu-id="a932c-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="a932c-194">Это средство работает, проверяя параметры службы единой системы обмена сообщениями в Active Directory и разрешая администратору Lync Server 2013 просматривать, создавать и редактировать объекты контактов.</span><span class="sxs-lookup"><span data-stu-id="a932c-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="a932c-195">RTCUniversalServerAdmins <em>и</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a932c-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="a932c-196">Для успешного выполнения ocsumutil.exe пользователь должен принадлежать обеим этим группам.</span><span class="sxs-lookup"><span data-stu-id="a932c-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="a932c-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span><span class="sxs-lookup"><span data-stu-id="a932c-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="a932c-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a932c-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="a932c-199">Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a932c-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="a932c-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="a932c-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a932c-201">При необходимости выполните другие действия по настройке голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a932c-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="a932c-202">Если вы еще не настроили параметры корпоративной голосовой связи на серверах или пользователях, выполните одно или несколько из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="a932c-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-203">разверните и настройте</span><span class="sxs-lookup"><span data-stu-id="a932c-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="a932c-204">шлюзы и серверы-посредники телефонной сети общего пользования (ТСОП);</span><span class="sxs-lookup"><span data-stu-id="a932c-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="a932c-205">определите политики голосовой связи, записи использования ТСОП и маршруты исходящих вызовов;</span><span class="sxs-lookup"><span data-stu-id="a932c-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="a932c-206">активируйте корпоративную голосовую связь для пользователей;</span><span class="sxs-lookup"><span data-stu-id="a932c-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="a932c-207">при необходимости настройте абонентские группы для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a932c-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="a932c-208">В зависимости от того, какие возможности поддерживаются корпоративными голосовыми функциями, могут потребоваться другие этапы настройки.</span><span class="sxs-lookup"><span data-stu-id="a932c-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="a932c-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a932c-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a932c-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a932c-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a932c-211">См. следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="a932c-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="a932c-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Настройка политик голосовой связи, записей использования КТСОП и голосовых маршрутов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a932c-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="a932c-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a932c-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a932c-214">Включите пользователей корпоративной голосовой почты для Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="a932c-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="a932c-215">На сервере Exchange UM убедитесь, что политика почтового ящика единой системы обмена сообщениями создана и у каждого пользователя есть уникальное назначение добавочного номера, а затем включите ее для единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="a932c-216">Администратор получателей Exchange</span><span class="sxs-lookup"><span data-stu-id="a932c-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="a932c-217">Для Exchange 2007 SP1 или более поздней версии ознакомьтесь &quot;со сведениями о том, как разрешить&quot; пользователям <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>единую систему обмена сообщениями на веб-странице.</span><span class="sxs-lookup"><span data-stu-id="a932c-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="a932c-218">2010 или более поздней версии пакета обновления можно &quot;узнать в <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>разделе Включение поддержки единой&quot; системы обмена сообщениями для пользователей Exchange.</span><span class="sxs-lookup"><span data-stu-id="a932c-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="a932c-219">Для Exchange 2013 вы найдете в <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>разделе Единая система обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a932c-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

