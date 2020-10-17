---
title: 'Lync Server 2013: разрешения и необходимые условия для настройки группы ответа'
description: 'Lync Server 2013: разрешения и необходимые условия для настройки группы ответа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7a0548c1d8886eb7741d1a31b24b480c1a2d30f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560905"
---
# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="37394-103">Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37394-103">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37394-104">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="37394-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="37394-105">Группа ответа это функция управления голосовым вызовом корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37394-105">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="37394-106">В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить группу ответа и административные учетные данные и разрешения, необходимые для выполнения задач по настройке.</span><span class="sxs-lookup"><span data-stu-id="37394-106">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="37394-107">В этом разделе предполагается, что вы прочитали документацию по планированию, относящуюся к группе ответа.</span><span class="sxs-lookup"><span data-stu-id="37394-107">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="37394-108">Дополнительные сведения приведены в статье [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="37394-108">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="37394-109">Инструменты настройки и административные роли</span><span class="sxs-lookup"><span data-stu-id="37394-109">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="37394-110">Для настройки группы ответа можно использовать следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="37394-110">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="37394-111">Панель управления сервера Lync</span><span class="sxs-lookup"><span data-stu-id="37394-111">Lync Server Control Panel</span></span>

  - <span data-ttu-id="37394-112">Средство настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="37394-112">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="37394-113">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="37394-113">Lync Server Management Shell</span></span>

<span data-ttu-id="37394-114">Для того чтобы настроить группы ответа, необходимо быть членом по крайней мере одной из следующих административных ролей:</span><span class="sxs-lookup"><span data-stu-id="37394-114">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37394-115"><strong>Группа безопасности Active Directory (1)</strong></span><span class="sxs-lookup"><span data-stu-id="37394-115"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="37394-116">Создайте рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="37394-116">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="37394-117">Назначьте менеджера</span><span class="sxs-lookup"><span data-stu-id="37394-117">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="37394-118">Создайте, назначьте агентов, очереди</span><span class="sxs-lookup"><span data-stu-id="37394-118">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="37394-119">Создайте дни праздников и рабочие часы</span><span class="sxs-lookup"><span data-stu-id="37394-119">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="37394-120">Активируйте или деактивируйте рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="37394-120">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="37394-121">Настройте рабочий процесс (Интерактивное речевое взаимодействие (IVR) или сервисную группу)</span><span class="sxs-lookup"><span data-stu-id="37394-121">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37394-122"><strong>ксреспонсеграупадминистратор</strong></span><span class="sxs-lookup"><span data-stu-id="37394-122"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="37394-123">√</span><span class="sxs-lookup"><span data-stu-id="37394-123">√</span></span></p></td>
<td><p><span data-ttu-id="37394-124">√</span><span class="sxs-lookup"><span data-stu-id="37394-124">√</span></span></p></td>
<td><p><span data-ttu-id="37394-125">√</span><span class="sxs-lookup"><span data-stu-id="37394-125">√</span></span></p></td>
<td><p><span data-ttu-id="37394-126">√</span><span class="sxs-lookup"><span data-stu-id="37394-126">√</span></span></p></td>
<td><p><span data-ttu-id="37394-127">√</span><span class="sxs-lookup"><span data-stu-id="37394-127">√</span></span></p></td>
<td><p><span data-ttu-id="37394-128">√</span><span class="sxs-lookup"><span data-stu-id="37394-128">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37394-129"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="37394-129"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="37394-130">√ (2)</span><span class="sxs-lookup"><span data-stu-id="37394-130">√(2)</span></span></p></td>
<td><p><span data-ttu-id="37394-131">√ (3)</span><span class="sxs-lookup"><span data-stu-id="37394-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="37394-132">√ (3)</span><span class="sxs-lookup"><span data-stu-id="37394-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="37394-133">√ (3)</span><span class="sxs-lookup"><span data-stu-id="37394-133">√(3)</span></span></p></td>
<td><p><span data-ttu-id="37394-134">√ (3)</span><span class="sxs-lookup"><span data-stu-id="37394-134">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37394-135"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="37394-135"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="37394-136">√</span><span class="sxs-lookup"><span data-stu-id="37394-136">√</span></span></p></td>
<td><p><span data-ttu-id="37394-137">√</span><span class="sxs-lookup"><span data-stu-id="37394-137">√</span></span></p></td>
<td><p><span data-ttu-id="37394-138">√</span><span class="sxs-lookup"><span data-stu-id="37394-138">√</span></span></p></td>
<td><p><span data-ttu-id="37394-139">√</span><span class="sxs-lookup"><span data-stu-id="37394-139">√</span></span></p></td>
<td><p><span data-ttu-id="37394-140">√</span><span class="sxs-lookup"><span data-stu-id="37394-140">√</span></span></p></td>
<td><p><span data-ttu-id="37394-141">√</span><span class="sxs-lookup"><span data-stu-id="37394-141">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37394-142"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="37394-142"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="37394-143">√</span><span class="sxs-lookup"><span data-stu-id="37394-143">√</span></span></p></td>
<td><p><span data-ttu-id="37394-144">√</span><span class="sxs-lookup"><span data-stu-id="37394-144">√</span></span></p></td>
<td><p><span data-ttu-id="37394-145">√</span><span class="sxs-lookup"><span data-stu-id="37394-145">√</span></span></p></td>
<td><p><span data-ttu-id="37394-146">√</span><span class="sxs-lookup"><span data-stu-id="37394-146">√</span></span></p></td>
<td><p><span data-ttu-id="37394-147">√</span><span class="sxs-lookup"><span data-stu-id="37394-147">√</span></span></p></td>
<td><p><span data-ttu-id="37394-148">√</span><span class="sxs-lookup"><span data-stu-id="37394-148">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37394-149"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="37394-149"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="37394-150">√</span><span class="sxs-lookup"><span data-stu-id="37394-150">√</span></span></p></td>
<td><p><span data-ttu-id="37394-151">√</span><span class="sxs-lookup"><span data-stu-id="37394-151">√</span></span></p></td>
<td><p><span data-ttu-id="37394-152">√</span><span class="sxs-lookup"><span data-stu-id="37394-152">√</span></span></p></td>
<td><p><span data-ttu-id="37394-153">√</span><span class="sxs-lookup"><span data-stu-id="37394-153">√</span></span></p></td>
<td><p><span data-ttu-id="37394-154">√</span><span class="sxs-lookup"><span data-stu-id="37394-154">√</span></span></p></td>
<td><p><span data-ttu-id="37394-155">√</span><span class="sxs-lookup"><span data-stu-id="37394-155">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37394-156"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="37394-156"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="37394-157">√ (4)</span><span class="sxs-lookup"><span data-stu-id="37394-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="37394-158">√ (4)</span><span class="sxs-lookup"><span data-stu-id="37394-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="37394-159">√ (4)</span><span class="sxs-lookup"><span data-stu-id="37394-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="37394-160">√ (4)</span><span class="sxs-lookup"><span data-stu-id="37394-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="37394-161">√ (4)</span><span class="sxs-lookup"><span data-stu-id="37394-161">√(4)</span></span></p></td>
<td><p><span data-ttu-id="37394-162">√ (4)</span><span class="sxs-lookup"><span data-stu-id="37394-162">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="37394-163"><STRONG>(1)</STRONG> объект пользователя доменных служб Active Directory должен быть членом указанной группы безопасности Active Directory в списке.</span><span class="sxs-lookup"><span data-stu-id="37394-163"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="37394-164">Администратор или другой делегированный участник группы Active Directory с соответствующими разрешениями для добавления пользователей в группу безопасности (например, администратору, операторам учетных записей) должен добавить объект пользователя в указанную группу безопасности или группу, чтобы пользователь мог выполнять указанные функции.</span><span class="sxs-lookup"><span data-stu-id="37394-164">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="37394-165"><STRONG>(2)</STRONG> только для рабочих процессов, назначенных Ксреспонсеграупадминистратор для CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="37394-165"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="37394-166"><STRONG>(3)</STRONG> диспетчер группы ответа может назначить другой участник CsResponseGroupManager рабочему процессу, который уже управляется текущим руководителем.</span><span class="sxs-lookup"><span data-stu-id="37394-166"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="37394-167"><STRONG>(4)</STRONG> CsViewOnlyAdministrator могут выполнять только командлеты "Get" Командная консоль управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37394-167"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="37394-168">Необходимые условия для настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="37394-168">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="37394-169">Для группы ответа требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="37394-169">Response Group requires the following components:</span></span>

  - <span data-ttu-id="37394-170">служба приложения;</span><span class="sxs-lookup"><span data-stu-id="37394-170">Application service</span></span>

  - <span data-ttu-id="37394-171">приложение группы ответа;</span><span class="sxs-lookup"><span data-stu-id="37394-171">Response Group application</span></span>

  - <span data-ttu-id="37394-172">Языковые пакеты</span><span class="sxs-lookup"><span data-stu-id="37394-172">Language packs</span></span>

  - <span data-ttu-id="37394-173">Хранилище файлов (для хранения аудиофайлов)</span><span class="sxs-lookup"><span data-stu-id="37394-173">File store (to hold audio files)</span></span>

  - <span data-ttu-id="37394-174">Веб-службы (включает средство настройки группы ответа и консоль "вход и выход" агентов).</span><span class="sxs-lookup"><span data-stu-id="37394-174">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="37394-175">Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37394-175">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="37394-176">Перед настройкой группы ответа может потребоваться выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="37394-176">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="37394-177">Включение пользователей для Lync Server 2013 и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37394-177">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="37394-178">Изменить файл конфигурации для соответствия стандартам Federal Information Processing (FIPS).</span><span class="sxs-lookup"><span data-stu-id="37394-178">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="37394-179">Изменить параметры сортировки базы данных для поддержки символов транскрипций ий, мэн, цзан для названий очередей и групп агентов.</span><span class="sxs-lookup"><span data-stu-id="37394-179">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="37394-180">Включение пользователей</span><span class="sxs-lookup"><span data-stu-id="37394-180">Enabling Users</span></span>

<span data-ttu-id="37394-181">Первым этапом настройки группы ответа является создание групп агентов.</span><span class="sxs-lookup"><span data-stu-id="37394-181">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="37394-182">Прежде чем можно будет создать группу агентов, необходимо включить пользователей, которые будут агентами для группы ответа для Lync Server 2013 и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37394-182">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="37394-183">Включение пользователей для Lync Server 2013 обычно является шагом в развертывании сервера Enterprise Edition или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="37394-183">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="37394-184">Дополнительные сведения о включении пользователей для Lync Server 2013 приведены в статье [Отключение или повторное включение учетной записи пользователя для Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="37394-184">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="37394-185">Включение пользователей для корпоративной голосовой связи обычно является шагом в развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="37394-185">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="37394-186">Дополнительную информацию можно узнать [в статье Включение поддержки корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="37394-186">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="37394-187">Соответствие требованиям стандарта FIPS</span><span class="sxs-lookup"><span data-stu-id="37394-187">Complying with FIPS requirements</span></span>

<span data-ttu-id="37394-188">Данный подраздел касается вас, только если вашей организации необходимо соответствовать федеральному стандарту по (FIPS, США).</span><span class="sxs-lookup"><span data-stu-id="37394-188">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="37394-189">Чтобы соответствовать стандарту, после установки Web Services необходимо изменить файл Web.config уровня приложения на использование другого криптографического алгоритма.</span><span class="sxs-lookup"><span data-stu-id="37394-189">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="37394-190">Нужно указать, чтобы ASP.NET использовал алгоритм Triple Data Encryption Standard (3DES) для обработки данных о состоянии просмотра.</span><span class="sxs-lookup"><span data-stu-id="37394-190">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="37394-191">Для приложения группы ответа это требование применяется к средству настройки группы ответа, а также к консоли входа и выхода агента.</span><span class="sxs-lookup"><span data-stu-id="37394-191">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="37394-192">Сведения об этих требованиях можно найти в статье 911722 базы знаний Майкрософт "сообщение об ошибке при доступе к веб-страницам ASP.NET с включенным состоянием отображения после обновления ASP.NET 1,1 до ASP.NET 2,0" по адресу " [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183) .</span><span class="sxs-lookup"><span data-stu-id="37394-192">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="37394-193">Чтобы изменить файл Web.config, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="37394-193">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="37394-194">В текстовом редакторе, например в Блокноте, файл Web.config уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="37394-194">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="37394-195">В файле Web.config выберите `<system.web>` раздел.</span><span class="sxs-lookup"><span data-stu-id="37394-195">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="37394-196">Добавьте `<machineKey>` в раздел следующий раздел `<system.web>` :</span><span class="sxs-lookup"><span data-stu-id="37394-196">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="37394-197">Сохраните файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="37394-197">Save the Web.config file.</span></span>

5.  <span data-ttu-id="37394-198">Перезапустите службу служб IIS, выполнив следующую команду в командной строки:</span><span class="sxs-lookup"><span data-stu-id="37394-198">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="37394-199">Поддержка символов транскрипций ий, мэн и цзан</span><span class="sxs-lookup"><span data-stu-id="37394-199">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="37394-200">Данный раздел относится к вам, только если вашей организации нужна поддержка подобных символов</span><span class="sxs-lookup"><span data-stu-id="37394-200">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37394-201">Сведения о том, что представляют собой символы Yi, Мэн и подобных, а также причины, по которым они могут быть важны для развертывания, можно узнать в статье кодировки GB18030 <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A> .</span><span class="sxs-lookup"><span data-stu-id="37394-201">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="37394-p106">Для поддержки данных символов необходимо изменить параметры сортировки базы данных Rgsconfig. Измените параметры сортировки столбца **Название** в следующих таблицах каждой базы данных Rgsconfig:</span><span class="sxs-lookup"><span data-stu-id="37394-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="37394-204">dbo. ажентграупс</span><span class="sxs-lookup"><span data-stu-id="37394-204">dbo.AgentGroups</span></span>

  - <span data-ttu-id="37394-205">dbo. BusinessHours</span><span class="sxs-lookup"><span data-stu-id="37394-205">dbo.BusinessHours</span></span>

  - <span data-ttu-id="37394-206">dbo. холидайсетс</span><span class="sxs-lookup"><span data-stu-id="37394-206">dbo.HolidaySets</span></span>

  - <span data-ttu-id="37394-207">dbo. Очереди</span><span class="sxs-lookup"><span data-stu-id="37394-207">dbo.Queues</span></span>

  - <span data-ttu-id="37394-208">dbo. Выгружен</span><span class="sxs-lookup"><span data-stu-id="37394-208">dbo.Workflows</span></span>

<span data-ttu-id="37394-209">Для SQL Server 2008 R2 и SQL Server 2012 используйте \_ Параметры сортировки латиницы General \_ 100 (с учетом диакритических знаков).</span><span class="sxs-lookup"><span data-stu-id="37394-209">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="37394-210">При использовании этих параметров сортировки все имена объектов не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="37394-210">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="37394-211">Изменить параметры сортировки можно с помощью Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="37394-211">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="37394-212">Дополнительные сведения об использовании этого средства приведены в разделе "использование SQL Server Management Studio" [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184) .</span><span class="sxs-lookup"><span data-stu-id="37394-212">For details about using this tool, see "Using SQL Server Management Studio" at [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="37394-213">Чтобы изменить параметры сортировки, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="37394-213">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="37394-214">Убедитесь в том, что SQL Server Management Studio настроен так, что можно было бы вносить изменения, требующие пересоздания таблиц.</span><span class="sxs-lookup"><span data-stu-id="37394-214">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="37394-215">Дополнительные сведения см. в разделе "сохранение (не разрешено)" в диалоговом окне "сохранение (запрещен)" [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186) .</span><span class="sxs-lookup"><span data-stu-id="37394-215">For details, see "Save (Not Permitted) Dialog Box" at [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="37394-216">Дополнительные сведения о настройке параметров сортировки столбцов приведены в разделе "инструкции: Set collation Columns (визуальные инструменты для баз данных)" в [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185) .</span><span class="sxs-lookup"><span data-stu-id="37394-216">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="37394-217">Используя Microsoft SQL Server Management Studio подключитесь к базе данных Rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="37394-217">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="37394-218">Найдите нужную таблицу в базе данных Rgsconfig, щелкните ее правой кнопкой мыши и выберите **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="37394-218">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="37394-219">Измените параметры сортировки столбца **Название** и сохраните таблицу.</span><span class="sxs-lookup"><span data-stu-id="37394-219">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

