---
title: Процесс развертывания для интеграции локальной единой системы обмена сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d60b120db57ad73c33e682fa8150e99f5606e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="1e6b5-102">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e6b5-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e6b5-103">_**Последнее изменение темы:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="1e6b5-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="1e6b5-104">Если вы хотите интегрировать единую систему обмена сообщениями Exchange с Lync Server 2013, необходимо выполнить действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="1e6b5-105">Кроме того, ознакомьтесь с рекомендациями по планированию и развертыванию, описанными в статье [рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="1e6b5-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="1e6b5-106">В этом разделе предполагается, что вы развернули Lync Server 2013 с совмещенным сервером-посредником и что вы включили пользователей для Lync Server 2013, но не обязательно выполнили все действия по развертыванию и настройке, чтобы включить корпоративную голосовую связь, как описано в статье Deployment [Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="1e6b5-107">Процесс интеграции единой системы обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="1e6b5-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1e6b5-108">Важно скоординировать администраторов Exchange вашей организации, чтобы подтвердить задачи, которые они будут выполнять для обеспечения успешной интеграции.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="1e6b5-109">Этап</span><span class="sxs-lookup"><span data-stu-id="1e6b5-109">Phase</span></span></th>
<th><span data-ttu-id="1e6b5-110">Шаги</span><span class="sxs-lookup"><span data-stu-id="1e6b5-110">Steps</span></span></th>
<th><span data-ttu-id="1e6b5-111">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="1e6b5-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="1e6b5-112">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="1e6b5-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e6b5-113">Выполните развертывание одного из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-114">Microsoft Exchange Server 2007 с пакетом обновления 1 (SP2) или последним пакетом обновления</span><span class="sxs-lookup"><span data-stu-id="1e6b5-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-115">Microsoft Exchange Server 2010 или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="1e6b5-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e6b5-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1e6b5-117">Если вы используете Microsoft Exchange Server 2013, установите следующие роли Exchange Server в том же лесу или в другом лесу, что и Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-118">клиентский доступ;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-119">Почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="1e6b5-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="1e6b5-120">Если Microsoft Exchange Server 2013 и единая система обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange так, чтобы он доверял лесу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="1e6b5-121">Если вы используете Exchange 2010, установите следующие роли Exchange Server в том же лесу или в другом лесу, что и Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-122">единая система обмена сообщениями;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-123">транспортный сервер-концентратор;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-124">клиентский доступ;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-125">Почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="1e6b5-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="1e6b5-126">Если Lync Server 2013 и единая система обмена сообщениями Exchange установлены в разных лесах, настройте каждый лес Exchange так, чтобы он доверял лесу Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-127">Администраторы предприятия (если это первый сервер Exchange Server в организации)</span><span class="sxs-lookup"><span data-stu-id="1e6b5-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="1e6b5-128">-ИЛИ-</span><span class="sxs-lookup"><span data-stu-id="1e6b5-128">-OR-</span></span></p>
<p><span data-ttu-id="1e6b5-129">Администратор организации Exchange (если это не первый сервер Exchange Server в организации)</span><span class="sxs-lookup"><span data-stu-id="1e6b5-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-130">Изучите соответствующую документацию для вашей версии Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="1e6b5-131">Документация по развертыванию Exchange Server <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 на сайте.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-131">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="1e6b5-132">Документация по развертыванию Exchange Server 2010 или новейшей <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>версии пакета обновления на сайте.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="1e6b5-133">Планирование и развертывание Microsoft Exchange Server 2013 на <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>сайте.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6b5-134">Установите сертификаты.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-135">Скачайте и установите сертификаты для каждого сервера единой системы обмена сообщениями Exchange из доверенного корневого центра сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="1e6b5-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="1e6b5-136">Сертификаты необходимы для взаимной безопасности на уровне транспорта (MTLS) между серверами, на которых запущены службы единой системы обмена сообщениями Exchange и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-137">Администраторы</span><span class="sxs-lookup"><span data-stu-id="1e6b5-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Настройка сертификатов на сервере, на котором работает единая система обмена сообщениями Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e6b5-139">Создайте и настройте новую абонентскую группу SIP единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-140">На сервере единой системы обмена сообщениями Exchange создайте абонентскую группу SIP на основе конкретных требований к развертыванию вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-141">Администратор организации Exchange</span><span class="sxs-lookup"><span data-stu-id="1e6b5-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-142">Для Exchange 2007 с пакетом обновления 1 (SP1 &quot;) или более поздней версии ознакомьтесь со статьей&quot; создание <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>абонентской группы URI SIP единой системы обмена сообщениями в.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-143">&quot; В <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>статье &quot;Создание абонентской группы единой системы обмена сообщениями для Exchange 2010 или более позднего пакета обновления.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-144">Для Exchange 2013: единая система обмена <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-144">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6b5-145">Настройте параметры безопасности для абонентской группы SIP единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-146">Для шифрования трафика корпоративной голосовой связи настройте параметры безопасности для абонентской группы SIP единой системы обмена сообщениями Exchange в качестве защиты или <strong>защиты</strong> <strong>SIP</strong> .</span><span class="sxs-lookup"><span data-stu-id="1e6b5-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="1e6b5-147">Это особенно важный шаг, если вы развернули или запланируете развертывание устройств Lync Phone Edition в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="1e6b5-148">Для работы устройств Lync Phone Edition в среде с интеграцией единой системы обмена сообщениями Exchange параметры шифрования Lync Server должны быть согласованы с параметрами безопасности абонентской группы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="1e6b5-149">Дополнительные сведения см. в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-150">Администратор организации Exchange</span><span class="sxs-lookup"><span data-stu-id="1e6b5-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1e6b5-152">Сведения об Exchange 2007 с пакетом обновления 1 (SP1) или более поздней версии см.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="1e6b5-153">&quot;Настройка безопасности для абонентской группы единой системы обмена&quot; сообщениями <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-154">Для Exchange 2010 или более поздней версии пакета обновления см. также следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="1e6b5-155">&quot;Настройка безопасности VoIP для абонентской группы&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-156">Для Exchange 2013: единая система обмена <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-156">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e6b5-157">Добавьте серверы единой системы обмена сообщениями в абонентскую группу SIP единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-158">Чтобы добавленный сервер единой системы обмена сообщениями отвечал на входящие звонки и обрабатывал их, необходимо добавить его в абонентскую группу единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="1e6b5-159">В этом случае добавьте сервер в абонентскую группу SIP единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-160">Администраторы</span><span class="sxs-lookup"><span data-stu-id="1e6b5-160">Administrators</span></span></p>
<p><span data-ttu-id="1e6b5-161">Администраторы Exchange Server</span><span class="sxs-lookup"><span data-stu-id="1e6b5-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-162">В случае с Exchange 2007 с пакетом обновления 1 &quot;(SP1) или более поздней версии Узнайте,&quot; как <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>добавить сервер единой системы обмена сообщениями в абонентскую службу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-163">Для Exchange 2010 или более поздней версии можно &quot;просмотреть или настроить свойства сервера&quot; единой системы обмена сообщениями <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>на сайте.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-164">Для Exchange 2013: единая система обмена <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-164">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6b5-165">Настройте SIP-адреса для почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-166">Назначьте SIP адреса почтовым ящикам пользователей корпоративной голосовой связи, которые будут использовать функции единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-167">Lync Server 2013, администратор</span><span class="sxs-lookup"><span data-stu-id="1e6b5-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="1e6b5-168">Администратор получателей Exchange</span><span class="sxs-lookup"><span data-stu-id="1e6b5-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-169">Для Exchange 2007 с пакетом обновления 1 (SP1 &quot;) или более поздней версии Узнайте, как добавить, удалить или изменить SIP адрес для&quot; пользователя <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>с включенной поддержкой единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-170">Для Exchange 2010 или более поздней версии в &quot;разделе изменение SIP SIP Address для пользователя&quot; с включенной поддержкой <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>единой системы обмена сообщениями по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-171">Для Exchange 2013: единая система обмена <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-171">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e6b5-172">Запустите скрипт exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-173">На сервере, на котором запущены службы единой системы обмена сообщениями, откройте командную консоль Exchange и запустите сценарий сценарий ExchUCUtil. ps1, который выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-174">Предоставляет Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory единой системы обмена сообщениями Exchange, а именно абонентских групп SIP, созданных в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-175">Создает объект шлюза IP единой системы обмена сообщениями в Active Directory для каждого пула Lync Server 2013 Enterprise Edition или сервера Standard Edition, на котором размещаются пользователи, для которых включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-176">Создает сервисную группу единой системы обмена сообщениями Exchange для каждого шлюза.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="1e6b5-177">Пилотным идентификатором сервисной группы будет имя абонентской группы, связанной с соответствующим шлюзом.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="1e6b5-178">Их необходимо сопоставлять 1:1, если абонентских групп несколько.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1e6b5-179">Администратор организации Exchange</span><span class="sxs-lookup"><span data-stu-id="1e6b5-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="1e6b5-180">Администратор получателей Exchange</span><span class="sxs-lookup"><span data-stu-id="1e6b5-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Настройка единой системы обмена сообщениями в Microsoft Exchange для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6b5-182">Настройка абонентских планов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-183">При интеграции с Exchange 2007 с пакетом обновления 1 (SP1) или более поздним пакетом обновления или Exchange 2010 создайте новую абонентскую группу для корпоративной голосовой связи с именем, соответствующим полному доменному имени абонентской группы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="1e6b5-184">Это потребуется сделать для каждой абонентской группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="1e6b5-185">Если вы интегрируетесь с Exchange 2010 с пакетом обновления 1 (SP1), убедитесь, что настроены соответствующие корпоративные и глобальные абонентские группы на уровне сайта или на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="1e6b5-186">При интеграции с Exchange 2010 с пакетом обновления 1 (SP1) абонентская группа Lync Server и имена абонентской группы SIP единой системы обмена сообщениями Exchange не должны сопоставляться.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="1e6b5-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1e6b5-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-188"><a href="lync-server-2013-configuring-dial-plans.md">Настройка абонентских планов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e6b5-189">Запустите средство интеграции единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-190">На Lync Server 2013 выполните <strong>ocsumutil. exe</strong>, который:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-191">создает объекты контактов абонентского доступа и автосекретаря;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-192">Проверка наличия абонентской группы корпоративной голосовой связи с именем, которое соответствует полному доменному имени абонентской группы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="1e6b5-193">Если вы используете Exchange 2010 с пакетом обновления 1 (SP1) или более поздней версии, имена абонентской группы не обязательно должны быть согласованы, и вы можете пропустить предупреждение этого средства.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="1e6b5-194">Это средство работает, проверяя параметры Active Directory единой системы обмена сообщениями Exchange и позволяя администратору Lync Server 2013 просматривать, создавать и редактировать объекты контактов.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-195">RTCUniversalServerAdmins <em>и</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1e6b5-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="1e6b5-196">Для успешного выполнения ocsumutil.exe пользователь должен принадлежать обеим этим группам.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="1e6b5-197">Чтобы создать объекты контактов, пользователей, запускающий средство ocsumutil.exe, должен обладать нужными разрешениями для подразделения Active Directory, в котором хранятся новые объекты контактов.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="1e6b5-198">Эти разрешения можно получить, выполнив командлет <STRONG>Grant-CsOUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="1e6b5-199">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="1e6b5-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Настройка Lync Server 2013 для работы с единой системой обмена сообщениями на сервере Microsoft Exchange</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6b5-201">При необходимости выполните другие действия по настройке корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-202">Если вы еще не настроили параметры корпоративной голосовой связи на серверах или пользователях, выполните одно или несколько из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-203">разверните и настройте</span><span class="sxs-lookup"><span data-stu-id="1e6b5-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="1e6b5-204">шлюзы и серверы-посредники телефонной сети общего пользования (ТСОП);</span><span class="sxs-lookup"><span data-stu-id="1e6b5-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-205">определите политики голосовой связи, записи использования ТСОП и маршруты исходящих вызовов;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-206">активируйте пользователей для применения Enterprise Voice;</span><span class="sxs-lookup"><span data-stu-id="1e6b5-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="1e6b5-207">при необходимости настройте абонентские группы для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="1e6b5-208">В зависимости от включенных функций корпоративной голосовой связи может потребоваться выполнить другие действия по настройке.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1e6b5-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1e6b5-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1e6b5-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-211">См. следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="1e6b5-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="1e6b5-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="1e6b5-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1e6b5-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e6b5-214">Включение пользователей корпоративной голосовой связи для единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-215">На сервере единой системы обмена сообщениями Exchange убедитесь, что создана политика почтовых ящиков единой системы обмена сообщениями и у каждого пользователя есть уникальное назначение добавочного номера, а затем включите для пользователя единую систему обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-216">Администратор получателей Exchange</span><span class="sxs-lookup"><span data-stu-id="1e6b5-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="1e6b5-217">Для Exchange 2007 с пакетом обновления 1 (SP1 &quot;) или более <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>поздней версии Узнайте,&quot; как включить для пользователя поддержку единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-218">Для сервера Exchange 2010 или более поздней версии &quot;в разделе Включение поддержки единой системы&quot; обмена <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>сообщениями в Exchange или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="1e6b5-219">Для Exchange 2013: единая система обмена <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>сообщениями по адресу.</span><span class="sxs-lookup"><span data-stu-id="1e6b5-219">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

