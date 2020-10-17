---
title: 'Lync Server 2013: процесс развертывания для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54335e8f70753a77f937819f896135ec1fe67b93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526896"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="cb575-102">Процесс развертывания для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb575-102">Deployment process for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb575-103">_**Последнее изменение темы:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="cb575-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="cb575-104">В этом разделе представлен обзор этапов и действий, необходимых при развертывании приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="cb575-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="cb575-105">Процедура развертывания группы ответа</span><span class="sxs-lookup"><span data-stu-id="cb575-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb575-106">Этап</span><span class="sxs-lookup"><span data-stu-id="cb575-106">Phase</span></span></th>
<th><span data-ttu-id="cb575-107">Действия</span><span class="sxs-lookup"><span data-stu-id="cb575-107">Steps</span></span></th>
<th><span data-ttu-id="cb575-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="cb575-108">Permissions</span></span></th>
<th><span data-ttu-id="cb575-109">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="cb575-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb575-110">Установка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="cb575-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="cb575-111">Приложение группы ответа устанавливается и активируется по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cb575-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="cb575-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cb575-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="cb575-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Развертывание корпоративной голосовой связи в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb575-114">Установка компонентов для группы ответа</span><span class="sxs-lookup"><span data-stu-id="cb575-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="cb575-115">Командлеты Lync Server, панель управления Lync Server, средство настройки группы ответа, агенты входа и выхода, а также клиентская веб-служба "группа ответа" устанавливается в составе веб-служб.</span><span class="sxs-lookup"><span data-stu-id="cb575-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="cb575-116">Веб-службы устанавливаются при развертывании пула Enterprise Edition или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cb575-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="cb575-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cb575-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="cb575-118"><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb575-119">Включение пользователей для Lync 2013 и корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="cb575-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="cb575-120">Включите пользователей, которые будут агентами для Lync Server и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cb575-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="cb575-121">Пользователей необходимо включить до того, как их можно будет добавлять в группы агентов.</span><span class="sxs-lookup"><span data-stu-id="cb575-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="cb575-122">Как правило, для пользователей включена поддержка Lync Server во время развертывания Enterprise Edition или Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="cb575-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="cb575-123">Для пользователей включена поддержка корпоративной голосовой связи во время развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cb575-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="cb575-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="cb575-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="cb575-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="cb575-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="cb575-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cb575-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb575-129">Создание и настройка групп ответа, которые состоят из групп агентов, очередей и рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="cb575-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cb575-130">Используйте панель управления Lync Server или Командная консоль Lync Server, чтобы выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="cb575-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="cb575-131">Создайте и настройте группы агентов.</span><span class="sxs-lookup"><span data-stu-id="cb575-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="cb575-132">Создайте и настройте очереди.</span><span class="sxs-lookup"><span data-stu-id="cb575-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="cb575-133">Кроме того, можно использовать командную консоль Lync Server для создания предопределенных рабочих часов и праздников для группы ответа.</span><span class="sxs-lookup"><span data-stu-id="cb575-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="cb575-134">С помощью средства настройки группы ответа или командной консоли Lync Server можно создавать рабочие процессы (сервисные группы или потоки вызовов интерактивного речевого ответа (IVR)), в том числе настраиваемые рабочие часы и праздники для группы ответа.</span><span class="sxs-lookup"><span data-stu-id="cb575-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cb575-135">Вы можете получить доступ к средству настройки группы ответа с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb575-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="cb575-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cb575-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="cb575-137">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="cb575-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="cb575-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="cb575-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="cb575-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="cb575-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="cb575-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="cb575-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Создание групп агентов группы ответа Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cb575-143"><a href="lync-server-2013-create-response-group-queues.md">Создание очередей группы ответа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cb575-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Необязательно Определение рабочих часов для группы ответа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cb575-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Необязательно Определение наборов праздников группы ответа в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cb575-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Создание или изменение рабочего процесса в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb575-147">(Необязательно) Задание настроек на уровне приложения</span><span class="sxs-lookup"><span data-stu-id="cb575-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="cb575-148">Используйте командную консоль Lync Server, чтобы настроить используемую по умолчанию конфигурацию хранения музыки, а также звуковой файл по умолчанию для хранения музыки, период отсрочки агента удерживаемого абонента и конфигурацию контекста вызовов.</span><span class="sxs-lookup"><span data-stu-id="cb575-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="cb575-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cb575-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="cb575-150">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="cb575-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="cb575-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="cb575-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="cb575-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="cb575-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Управление параметрами группы ответа уровня приложения в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb575-155">(Необязательно) Делегирование управления группами реагирования</span><span class="sxs-lookup"><span data-stu-id="cb575-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="cb575-156">Назначьте пользователям роль CsResponseGroupManager для делегирования настройки групп ответа.</span><span class="sxs-lookup"><span data-stu-id="cb575-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="cb575-157">После этого менеджеры группы ответа могут настраивать назначенные им группы ответа.</span><span class="sxs-lookup"><span data-stu-id="cb575-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="cb575-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cb575-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="cb575-159">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="cb575-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="cb575-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="cb575-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="cb575-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cb575-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="cb575-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cb575-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb575-164">Проверка развертывания группы ответа</span><span class="sxs-lookup"><span data-stu-id="cb575-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="cb575-165">Протестируйте ответ на звонки в сервисную группу и рабочие процессы IVR, чтобы гарантировать правильную работу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cb575-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

