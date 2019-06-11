---
title: 'Lync Server 2013: разрешения и необходимые условия для настройки группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a><span data-ttu-id="70eea-102">Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70eea-102">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70eea-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="70eea-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="70eea-104">Группа ответа — это функция управления голосовым звонком в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="70eea-104">Response Group is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="70eea-105">В этой статье описаны действия, которые необходимо выполнить, прежде чем можно будет настроить группу ответа и учетные данные администратора и разрешения, необходимые для выполнения задач настройки.</span><span class="sxs-lookup"><span data-stu-id="70eea-105">This topic describes what you need to have in place before you can configure Response Group and the administrative credentials and permissions you need to perform configuration tasks.</span></span>

<span data-ttu-id="70eea-106">В этом разделе предполагается, что вы прочитали документацию по планированию, связанную с группой ответа.</span><span class="sxs-lookup"><span data-stu-id="70eea-106">This section assumes that you have read the planning documentation related to Response Group.</span></span> <span data-ttu-id="70eea-107">Подробнее смотрите в разделе [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="70eea-107">For details, see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in the Planning documentation.</span></span>

<div>

## <a name="configuration-tools-and-administrative-roles"></a><span data-ttu-id="70eea-108">Средства настройки и административные роли</span><span class="sxs-lookup"><span data-stu-id="70eea-108">Configuration Tools and Administrative Roles</span></span>

<span data-ttu-id="70eea-109">Для настройки группы ответа можно использовать следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="70eea-109">You can use the following administrative tools to configure Response Group:</span></span>

  - <span data-ttu-id="70eea-110">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="70eea-110">Lync Server Control Panel</span></span>

  - <span data-ttu-id="70eea-111">настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="70eea-111">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="70eea-112">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="70eea-112">Lync Server Management Shell</span></span>

<span data-ttu-id="70eea-113">Для того чтобы настроить группы ответа, необходимо быть членом по крайней мере одной из следующих административных ролей:</span><span class="sxs-lookup"><span data-stu-id="70eea-113">To configure response groups, you must be a member of at least one of the following administrative roles:</span></span>


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
<td><p><span data-ttu-id="70eea-114"><strong>Группа безопасности Active Directory (1)</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-114"><strong>Active Directory Security Group (1)</strong></span></span></p></td>
<td><p><span data-ttu-id="70eea-115">Создайте рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="70eea-115">Create Workflow</span></span></p></td>
<td><p><span data-ttu-id="70eea-116">Назначьте менеджера</span><span class="sxs-lookup"><span data-stu-id="70eea-116">Assign Manager</span></span></p></td>
<td><p><span data-ttu-id="70eea-117">Создайте, назначьте агентов, очереди</span><span class="sxs-lookup"><span data-stu-id="70eea-117">Create /assign agents, queues</span></span></p></td>
<td><p><span data-ttu-id="70eea-118">Создайте дни праздников и рабочие часы</span><span class="sxs-lookup"><span data-stu-id="70eea-118">Create / manage holiday and business hours</span></span></p></td>
<td><p><span data-ttu-id="70eea-119">Активируйте или деактивируйте рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="70eea-119">Activate / deactivate workflow</span></span></p></td>
<td><p><span data-ttu-id="70eea-120">Настройте рабочий процесс (Интерактивное речевое взаимодействие (IVR) или сервисную группу)</span><span class="sxs-lookup"><span data-stu-id="70eea-120">Configure workflow (IVR or Hunt Group)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70eea-121"><strong>CsResponseGroupAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-121"><strong>CsResponseGroupAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="70eea-122">√</span><span class="sxs-lookup"><span data-stu-id="70eea-122">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-123">√</span><span class="sxs-lookup"><span data-stu-id="70eea-123">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-124">√</span><span class="sxs-lookup"><span data-stu-id="70eea-124">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-125">√</span><span class="sxs-lookup"><span data-stu-id="70eea-125">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-126">√</span><span class="sxs-lookup"><span data-stu-id="70eea-126">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-127">√</span><span class="sxs-lookup"><span data-stu-id="70eea-127">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70eea-128"><strong>CsResponseGroupManager</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-128"><strong>CsResponseGroupManager</strong></span></span></p></td>
<td> </td>
<td><p><span data-ttu-id="70eea-129">√(2)</span><span class="sxs-lookup"><span data-stu-id="70eea-129">√(2)</span></span></p></td>
<td><p><span data-ttu-id="70eea-130">√(3)</span><span class="sxs-lookup"><span data-stu-id="70eea-130">√(3)</span></span></p></td>
<td><p><span data-ttu-id="70eea-131">√(3)</span><span class="sxs-lookup"><span data-stu-id="70eea-131">√(3)</span></span></p></td>
<td><p><span data-ttu-id="70eea-132">√(3)</span><span class="sxs-lookup"><span data-stu-id="70eea-132">√(3)</span></span></p></td>
<td><p><span data-ttu-id="70eea-133">√(3)</span><span class="sxs-lookup"><span data-stu-id="70eea-133">√(3)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70eea-134"><strong>CsVoiceAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-134"><strong>CsVoiceAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="70eea-135">√</span><span class="sxs-lookup"><span data-stu-id="70eea-135">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-136">√</span><span class="sxs-lookup"><span data-stu-id="70eea-136">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-137">√</span><span class="sxs-lookup"><span data-stu-id="70eea-137">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-138">√</span><span class="sxs-lookup"><span data-stu-id="70eea-138">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-139">√</span><span class="sxs-lookup"><span data-stu-id="70eea-139">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-140">√</span><span class="sxs-lookup"><span data-stu-id="70eea-140">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70eea-141"><strong>CsServerAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-141"><strong>CsServerAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="70eea-142">√</span><span class="sxs-lookup"><span data-stu-id="70eea-142">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-143">√</span><span class="sxs-lookup"><span data-stu-id="70eea-143">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-144">√</span><span class="sxs-lookup"><span data-stu-id="70eea-144">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-145">√</span><span class="sxs-lookup"><span data-stu-id="70eea-145">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-146">√</span><span class="sxs-lookup"><span data-stu-id="70eea-146">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-147">√</span><span class="sxs-lookup"><span data-stu-id="70eea-147">√</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70eea-148"><strong>CsAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-148"><strong>CsAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="70eea-149">√</span><span class="sxs-lookup"><span data-stu-id="70eea-149">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-150">√</span><span class="sxs-lookup"><span data-stu-id="70eea-150">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-151">√</span><span class="sxs-lookup"><span data-stu-id="70eea-151">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-152">√</span><span class="sxs-lookup"><span data-stu-id="70eea-152">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-153">√</span><span class="sxs-lookup"><span data-stu-id="70eea-153">√</span></span></p></td>
<td><p><span data-ttu-id="70eea-154">√</span><span class="sxs-lookup"><span data-stu-id="70eea-154">√</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70eea-155"><strong>CsViewOnlyAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="70eea-155"><strong>CsViewOnlyAdministrator</strong></span></span></p></td>
<td><p><span data-ttu-id="70eea-156">√(4)</span><span class="sxs-lookup"><span data-stu-id="70eea-156">√(4)</span></span></p></td>
<td><p><span data-ttu-id="70eea-157">√(4)</span><span class="sxs-lookup"><span data-stu-id="70eea-157">√(4)</span></span></p></td>
<td><p><span data-ttu-id="70eea-158">√(4)</span><span class="sxs-lookup"><span data-stu-id="70eea-158">√(4)</span></span></p></td>
<td><p><span data-ttu-id="70eea-159">√(4)</span><span class="sxs-lookup"><span data-stu-id="70eea-159">√(4)</span></span></p></td>
<td><p><span data-ttu-id="70eea-160">√(4)</span><span class="sxs-lookup"><span data-stu-id="70eea-160">√(4)</span></span></p></td>
<td><p><span data-ttu-id="70eea-161">√(4)</span><span class="sxs-lookup"><span data-stu-id="70eea-161">√(4)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="70eea-162"><STRONG>(1)</STRONG> объект пользователя доменных служб Active Directory должен быть членом указанной группы безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70eea-162"><STRONG>(1)</STRONG> An Active Directory Domain Services user object must be a member of the specified Active Directory security group listed.</span></span> <span data-ttu-id="70eea-163">Администратор или другой делегированный участник группы Active Directory с необходимыми разрешениями для добавления пользователей в группу безопасности (например, администратор, операторы учета) должен добавить объект пользователя в группу безопасности или группу, чтобы предоставить пользователю возможность выполните указанные функции.</span><span class="sxs-lookup"><span data-stu-id="70eea-163">An administrator or other delegated Active Directory group member with appropriate permissions to add users to a security group (For example, Administrator, Account Operators) must add a user object to the listed security group or group for the user to be able to perform the functions listed.</span></span> <span data-ttu-id="70eea-164"><STRONG>(2)</STRONG> только для рабочих процессов, которым ксреспонсеграупадминистратор назначены для ксреспонсеграупманажер.</span><span class="sxs-lookup"><span data-stu-id="70eea-164"><STRONG>(2)</STRONG> Only for workflows that the CsResponseGroupAdministrator has assigned to the CsResponseGroupManager.</span></span> <span data-ttu-id="70eea-165"><STRONG>(3)</STRONG> руководитель группы ответа может назначить другой участник ксреспонсеграупманажер рабочему процессу, который уже управляется текущим руководителем.</span><span class="sxs-lookup"><span data-stu-id="70eea-165"><STRONG>(3)</STRONG> A Response Group Manager can assign another member of CsResponseGroupManager to a workflow that the current manager already manages.</span></span> <span data-ttu-id="70eea-166"><STRONG>(4)</STRONG> ксвиевонлядминистратор может выполнить только командлет "Get" команд командной консоли для управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70eea-166"><STRONG>(4)</STRONG> CsViewOnlyAdministrator can only run verb "Get" Lync Server Management Shell cmdlets.</span></span>



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a><span data-ttu-id="70eea-167">Необходимые условия для настройки группы ответа</span><span class="sxs-lookup"><span data-stu-id="70eea-167">Response Group Configuration Prerequisites</span></span>

<span data-ttu-id="70eea-168">Для группы ответа требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="70eea-168">Response Group requires the following components:</span></span>

  - <span data-ttu-id="70eea-169">приложения</span><span class="sxs-lookup"><span data-stu-id="70eea-169">Application service</span></span>

  - <span data-ttu-id="70eea-170">"Группа ответа"</span><span class="sxs-lookup"><span data-stu-id="70eea-170">Response Group application</span></span>

  - <span data-ttu-id="70eea-171">Языковые пакеты</span><span class="sxs-lookup"><span data-stu-id="70eea-171">Language packs</span></span>

  - <span data-ttu-id="70eea-172">Хранилище файлов (для хранения аудиофайлов)</span><span class="sxs-lookup"><span data-stu-id="70eea-172">File store (to hold audio files)</span></span>

  - <span data-ttu-id="70eea-173">Веб-службы (в том числе средство настройки группы ответа и консоль "вход и выход" агентов)</span><span class="sxs-lookup"><span data-stu-id="70eea-173">Web Services (includes the Response Group Configuration Tool and the agents' sign-in and sign-out console)</span></span>

<span data-ttu-id="70eea-174">Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="70eea-174">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="70eea-175">Перед настройкой группы ответа может потребоваться выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="70eea-175">You might need to perform the following tasks before configuring Response Group:</span></span>

  - <span data-ttu-id="70eea-176">Включите пользователей для Lync Server 2013 и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="70eea-176">Enable users for Lync Server 2013 and Enterprise Voice.</span></span>

  - <span data-ttu-id="70eea-177">Изменить файл конфигурации для соответствия стандартам Federal Information Processing (FIPS).</span><span class="sxs-lookup"><span data-stu-id="70eea-177">Modify a configuration file to be compliant with Federal Information Processing Standards (FIPS).</span></span>

  - <span data-ttu-id="70eea-178">Изменить параметры сортировки базы данных для поддержки символов транскрипций ий, мэн, цзан для названий очередей и групп агентов.</span><span class="sxs-lookup"><span data-stu-id="70eea-178">Modify the database collation to support Yi, Meng, and Zang characters for queue names and agent group names.</span></span>

<div>

## <a name="enabling-users"></a><span data-ttu-id="70eea-179">Включение пользователей</span><span class="sxs-lookup"><span data-stu-id="70eea-179">Enabling Users</span></span>

<span data-ttu-id="70eea-180">Первый шаг в настройке группы ответа — создание групп агента.</span><span class="sxs-lookup"><span data-stu-id="70eea-180">The first step in configuring Response Group is to create agent groups.</span></span> <span data-ttu-id="70eea-181">Прежде чем можно будет создать группу агента, необходимо включить пользователей, которые будут агентами группы ответа для Lync Server 2013 и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="70eea-181">Before you can create an agent group, you must enable the users who will be agents for Response Group for Lync Server 2013 and Enterprise Voice.</span></span> <span data-ttu-id="70eea-182">Включение пользователей для Lync Server 2013 обычно является шагом на сервере Enterprise Edition или стандартном развертывании сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="70eea-182">Enabling users for Lync Server 2013 is typically a step in the Enterprise Edition server or Standard Edition server deployment.</span></span> <span data-ttu-id="70eea-183">Дополнительные сведения о включении пользователей для Lync Server 2013 можно найти в разделе [Отключение и повторное включение учетной записи пользователя в Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="70eea-183">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="70eea-184">Включение пользователей для корпоративной голосовой связи обычно является шагом в развертывании Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="70eea-184">Enabling users for Enterprise Voice is typically a step in the Enterprise Voice deployment.</span></span> <span data-ttu-id="70eea-185">Дополнительные сведения можно найти [в разделе Включение пользователей для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="70eea-185">For details, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>

</div>

<div>

## <a name="complying-with-fips-requirements"></a><span data-ttu-id="70eea-186">Соответствие требованиям стандарта FIPS</span><span class="sxs-lookup"><span data-stu-id="70eea-186">Complying with FIPS requirements</span></span>

<span data-ttu-id="70eea-187">Данный подраздел касается вас, только если вашей организации необходимо соответствовать федеральному стандарту по (FIPS, США).</span><span class="sxs-lookup"><span data-stu-id="70eea-187">This section applies to you only if your organization needs to comply with Federal Information Processing Standards (FIPS).</span></span>

<span data-ttu-id="70eea-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span><span class="sxs-lookup"><span data-stu-id="70eea-188">To be compliant with FIPS, you need to modify the application-level Web.config file to use a different cryptography algorithm after you install Web Services.</span></span> <span data-ttu-id="70eea-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span><span class="sxs-lookup"><span data-stu-id="70eea-189">You need to specify that ASP.NET use the Triple Data Encryption Standard (3DES) algorithm to process view state data.</span></span> <span data-ttu-id="70eea-190">Для приложения группы ответа это требование распространяется на средство настройки группы ответа и на консоль входа и выхода агента.</span><span class="sxs-lookup"><span data-stu-id="70eea-190">For the Response Group application, this requirement applies to the Response Group Configuration Tool and the agent sign-in and sign-out console.</span></span> <span data-ttu-id="70eea-191">Дополнительные сведения об этих требованиях можно найти в статье 911722 базы знаний Майкрософт "сообщение об ошибке при доступе к веб-страницам ASP.NET с включенным состоянием отображения после перехода с ASP.NET 1,1 на ASP.NET 2,0" [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)по адресу.</span><span class="sxs-lookup"><span data-stu-id="70eea-191">For details about this requirement, see Microsoft Knowledge Base article 911722, "You may receive an error message when you access ASP.NET webpages that have ViewState enabled after you upgrade from ASP.NET 1.1 to ASP.NET 2.0," at [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).</span></span>

<span data-ttu-id="70eea-192">Чтобы изменить файл Web.config, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="70eea-192">To modify the Web.config file, do the following:</span></span>

1.  <span data-ttu-id="70eea-193">В текстовом редакторе, например в Блокноте, файл Web.config уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="70eea-193">In a text editor such as Notepad, open the application-level Web.config file.</span></span>

2.  <span data-ttu-id="70eea-194">Найдите `<system.web>` раздел в файле Web. config.</span><span class="sxs-lookup"><span data-stu-id="70eea-194">In the Web.config file, locate the `<system.web>` section.</span></span>

3.  <span data-ttu-id="70eea-195">Добавьте в `<system.web>` раздел `<machineKey>` следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="70eea-195">Add the following `<machineKey>` section to in the `<system.web>` section:</span></span>
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  <span data-ttu-id="70eea-196">Сохраните файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="70eea-196">Save the Web.config file.</span></span>

5.  <span data-ttu-id="70eea-197">Перезапустите службу служб IIS, выполнив следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="70eea-197">Restart the Internet Information Services (IIS) service by running the following command at a command prompt:</span></span>
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a><span data-ttu-id="70eea-198">Поддержка символов транскрипций ий, мэн и цзан</span><span class="sxs-lookup"><span data-stu-id="70eea-198">Supporting Yi, Meng, and Zang Characters</span></span>

<span data-ttu-id="70eea-199">Данный раздел относится к вам, только если вашей организации нужна поддержка подобных символов</span><span class="sxs-lookup"><span data-stu-id="70eea-199">This section applies to you only if your organization needs to support Yi, Meng, or Zang characters.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70eea-200">Сведения о том, что собой представляют собой символы Yi, Менг и Занг, а также причины, по которым они могут быть важны для вашего развертывания, можно найти <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>в разделе кодировка GB18030.</span><span class="sxs-lookup"><span data-stu-id="70eea-200">For information on what the Yi, Meng, and Zang characters are and why they may be important to your deployment, see the information on the GB18030 character sets <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>.</span></span>



</div>

<span data-ttu-id="70eea-p106">Для поддержки символов ий, мэн и цзан необходимо изменить параметры сортировки базы данных Rgsconfig. Измените параметры сортировки столбца **Имя** в следующих таблицах каждой базы данных Rgsconfig:</span><span class="sxs-lookup"><span data-stu-id="70eea-p106">To support Yi, Meng, or Zang characters, you need to modify the collation for the Rgsconfig database. Change the collation of the **Name** column in the following tables in each Rgsconfig database:</span></span>

  - <span data-ttu-id="70eea-203">dbo.AgentGroups</span><span class="sxs-lookup"><span data-stu-id="70eea-203">dbo.AgentGroups</span></span>

  - <span data-ttu-id="70eea-204">dbo.BusinessHours</span><span class="sxs-lookup"><span data-stu-id="70eea-204">dbo.BusinessHours</span></span>

  - <span data-ttu-id="70eea-205">dbo.HolidaySets</span><span class="sxs-lookup"><span data-stu-id="70eea-205">dbo.HolidaySets</span></span>

  - <span data-ttu-id="70eea-206">dbo.Queues</span><span class="sxs-lookup"><span data-stu-id="70eea-206">dbo.Queues</span></span>

  - <span data-ttu-id="70eea-207">dbo.Workflows</span><span class="sxs-lookup"><span data-stu-id="70eea-207">dbo.Workflows</span></span>

<span data-ttu-id="70eea-208">Для SQL Server 2008 R2 и SQL Server 2012 используйте параметры сортировки по\_латинский\_General 100 (с учетом диакритических знаков).</span><span class="sxs-lookup"><span data-stu-id="70eea-208">For SQL Server 2008 R2 and SQL Server 2012, use the Latin\_General\_100 (Accent Sensitive) collation.</span></span> <span data-ttu-id="70eea-209">Если применяются эти параметры сортировки во всех именах объектов не учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="70eea-209">If you use this collation, all object names are not case-sensitive.</span></span>

<span data-ttu-id="70eea-210">Изменить параметры сортировки можно с помощью Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="70eea-210">You can change the collation by using Microsoft SQL Server Management Studio.</span></span> <span data-ttu-id="70eea-211">Подробнее об использовании этого средства можно найти в [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)разделе "использование SQL Server Management Studio".</span><span class="sxs-lookup"><span data-stu-id="70eea-211">For details about using this tool, see "Using SQL Server Management Studio" at [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184).</span></span> <span data-ttu-id="70eea-212">Для изменения параметров сортировки выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="70eea-212">Follow these steps to change the collation:</span></span>

1.  <span data-ttu-id="70eea-213">Убедитесь в том, что в Microsoft SQL Server Management Studio разрешено повторное создание таблиц, требующих изменения.</span><span class="sxs-lookup"><span data-stu-id="70eea-213">Be sure that SQL Server Management Studio is configured to allow changes that require tables to be recreated.</span></span> <span data-ttu-id="70eea-214">Подробные сведения можно найти в разделе "сохранить (неразрешенные)" [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)в диалоговом окне "о себе".</span><span class="sxs-lookup"><span data-stu-id="70eea-214">For details, see "Save (Not Permitted) Dialog Box" at [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186).</span></span> <span data-ttu-id="70eea-215">Дополнительные сведения о настройке параметров сортировки столбцов можно найти в [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)разделе Инструкции: Настройка параметров сортировки столбцов (визуальные инструменты для баз данных).</span><span class="sxs-lookup"><span data-stu-id="70eea-215">For details about setting a column collation, see "How to: Set Column Collation (Visual Database Tools)" at [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).</span></span>

2.  <span data-ttu-id="70eea-216">Используя Microsoft SQL Server Management Studio подключитесь к базе данных Rgsconfig.</span><span class="sxs-lookup"><span data-stu-id="70eea-216">Using Microsoft SQL Server Management Studio, connect to the Rgsconfig database.</span></span>

3.  <span data-ttu-id="70eea-217">Найдите в базе данных Rgsconfig таблицу, которую требуется изменить, щелкните ее правой кнопкой мыши и выберите **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="70eea-217">Find the table you want to change in the Rgsconfig database, right-click the table, and click **Design**.</span></span>

4.  <span data-ttu-id="70eea-218">Измените параметры сортировки столбца **Имя** и сохраните таблицу.</span><span class="sxs-lookup"><span data-stu-id="70eea-218">Change the collation of the **Name** column and save the table.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

