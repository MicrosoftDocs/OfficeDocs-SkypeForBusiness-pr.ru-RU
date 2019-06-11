---
title: 'Lync Server 2013: процесс развертывания для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="0bb2f-102">Процесс развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bb2f-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bb2f-103">_**Тема последнего изменения:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="0bb2f-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="0bb2f-104">В этом разделе приводятся общие этапы и инструкции по развертыванию приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="0bb2f-105">Процедура развертывания группы ответа</span><span class="sxs-lookup"><span data-stu-id="0bb2f-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0bb2f-106">Этап</span><span class="sxs-lookup"><span data-stu-id="0bb2f-106">Phase</span></span></th>
<th><span data-ttu-id="0bb2f-107">Шаги</span><span class="sxs-lookup"><span data-stu-id="0bb2f-107">Steps</span></span></th>
<th><span data-ttu-id="0bb2f-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="0bb2f-108">Permissions</span></span></th>
<th><span data-ttu-id="0bb2f-109">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="0bb2f-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0bb2f-110">Установка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="0bb2f-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-111">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0bb2f-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb2f-114">Установка компонентов для группы ответа</span><span class="sxs-lookup"><span data-stu-id="0bb2f-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-115">Командлеты Lync Server, панель управления Lync Server, средство настройки группы ответа, агент "вход и выход из консоли" и клиентская веб-служба "группа ответа" устанавливается как часть веб-служб.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="0bb2f-116">Веб-службы устанавливаются при развертывании пула Enterprise Edition или стандартного сервера выпусков.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0bb2f-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-118"><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bb2f-119">Включение пользователей для Lync 2013 и для корпоративного голосовой связи</span><span class="sxs-lookup"><span data-stu-id="0bb2f-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-120">Включите пользователей, которые будут агентами для Lync Server и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="0bb2f-121">Пользователей необходимо включить до того, как их можно будет добавлять в группы агентов.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="0bb2f-122">Как правило, пользователи работают с Lync Server во время развертывания Enterprise Edition или Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="0bb2f-123">Для пользователей, использующих корпоративную голосовую раскладку, включены пользователи.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0bb2f-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="0bb2f-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение и повторное включение учетной записи пользователя для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0bb2f-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Включение пользователей корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb2f-129">Создание и настройка групп ответа, которые состоят из групп агентов, очередей и рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="0bb2f-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0bb2f-130">С помощью панели управления Lync Server или командной консоли Lync Server вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="0bb2f-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="0bb2f-131">Создайте и настройте группы агентов.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="0bb2f-132">Создайте и настройте очереди.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="0bb2f-133">Кроме того, можно использовать командную консоль Lync Server для создания стандартных рабочих часов и праздников для группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="0bb2f-134">С помощью средства настройки группы ответа или командной консоли Lync Server вы можете создавать рабочие процессы (группы слежения или потоки звонков для голосовой связи), в том числе пользовательские группы ответов и рабочие часы и праздники.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0bb2f-135">Вы можете получить доступ к средству настройки группы ответа с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="0bb2f-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0bb2f-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0bb2f-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0bb2f-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Создание групп агента группы ответа Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0bb2f-143"><a href="lync-server-2013-create-response-group-queues.md">Создание очередей группы ответа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0bb2f-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Необязательно Определение группы ответа в рабочее время в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0bb2f-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="0bb2f-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Создание или изменение рабочего процесса в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bb2f-147">(Необязательно) Задание настроек на уровне приложения</span><span class="sxs-lookup"><span data-stu-id="0bb2f-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-148">Используйте командную консоль Lync Server для настройки стандартной конфигурации сохранения музыки, используемого по умолчанию звукового файла для сохранения музыки, периода отсрочки агента рингбакк и контекстной конфигурации вызова.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0bb2f-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0bb2f-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Управление параметрами группы ответа уровня приложения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0bb2f-155">(Необязательно) Делегирование управления группами реагирования</span><span class="sxs-lookup"><span data-stu-id="0bb2f-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-156">Назначьте пользователям роль Ксреспонсеграупманажер для делегирования конфигурации групп ответов.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="0bb2f-157">После этого диспетчер групп ответов может настроить назначенные им группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0bb2f-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="0bb2f-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="0bb2f-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0bb2f-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование контроля доступа на основе ролей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0bb2f-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0bb2f-164">Проверка развертывания группы ответа</span><span class="sxs-lookup"><span data-stu-id="0bb2f-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="0bb2f-165">Протестируйте ответ на звонки в сервисную группу и рабочие процессы IVR, чтобы гарантировать правильную работу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0bb2f-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

