---
title: Контрольный список развертывания Lync Server 2013 для конференц-связи с телефонным подключением
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc593e5a40633f98146c4ce94f82b132f15ca6d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="9caa7-102">Контрольный список развертывания для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9caa7-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9caa7-103">_**Последнее изменение темы:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="9caa7-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="9caa7-104">Компоненты, необходимые для конференц-связи с телефонным подключением, разворачиваются при развертывании рабочей нагрузки конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9caa7-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="9caa7-105">Перед настройкой конференц-связи с телефонным подключением необходимо выполнить развертывание корпоративной голосовой или сервер-посредника и шлюза телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9caa7-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="9caa7-106">Перед тем как пользователи смогут присоединяться к аудио- или видеоконференции из ТСОП, необходимо выполнить все действия, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9caa7-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9caa7-107">При переходе с Office Communications Server 2007 R2 необходимо установить последние обновления для среды Office Communications Server 2007 R2 перед развертыванием конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="9caa7-108">Процесс развертывания конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="9caa7-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9caa7-109">Этап</span><span class="sxs-lookup"><span data-stu-id="9caa7-109">Phase</span></span></th>
<th><span data-ttu-id="9caa7-110">Шаги</span><span class="sxs-lookup"><span data-stu-id="9caa7-110">Steps</span></span></th>
<th><span data-ttu-id="9caa7-111">Разрешения</span><span class="sxs-lookup"><span data-stu-id="9caa7-111">Permissions</span></span></th>
<th><span data-ttu-id="9caa7-112">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="9caa7-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-113"><strong>Создание топологии, включающей рабочую нагрузку конференц-связи, включая сервер-посредник и шлюз PSTN, а также развертывание пула переднего плана или сервера Standard Edition</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9caa7-114">Запустите построитель топологий для настройки топологии.</span><span class="sxs-lookup"><span data-stu-id="9caa7-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="9caa7-115">При настройке топологии выберите вариант конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="9caa7-116">Опубликуйте топологию и разверните пул переднего плана или сервер Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9caa7-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="9caa7-117">При необходимости создайте изолированный сервер-посредник и свяжите его с шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="9caa7-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9caa7-118">Этот шаг необходим только в том случае, если вы не развертываете корпоративную голосовую связь и не размещаете сервер-посредник с помощью сервера Enterprise Едитионфронт или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9caa7-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="9caa7-119">При развертывании корпоративной голосовой связи вы устанавливаете и настраиваете серверы-посредники и шлюзы PSTN в рамках развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9caa7-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="9caa7-120">При совместном размещении сервера-посредника устанавливается и настраивается сервер-посредник в составе пула переднего плана или развертывания сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9caa7-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="9caa7-121">Администраторы домена</span><span class="sxs-lookup"><span data-stu-id="9caa7-121">Domain Admins</span></span></p>
<p><span data-ttu-id="9caa7-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-123">Администратор</span><span class="sxs-lookup"><span data-stu-id="9caa7-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9caa7-124"><a href="lync-server-2013-deploying-lync-server.md">Развертывание Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="9caa7-125">Создание изолированного пула серверов-посредников: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-126"><strong>Настройка абонентских групп</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-127">Абонентская группа — это набор правил нормализации телефонных номеров, которые преобразуют телефонные номера, набранные из определенного местонахождения, в единый стандартный формат (E.164) для авторизации телефона и маршрутизации вызова.</span><span class="sxs-lookup"><span data-stu-id="9caa7-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="9caa7-128">Один и тот же телефонный номер, набранный в разных местонахождениях, может на основе соответствующих абонентских групп преобразовываться в разные номера E.164, в зависимости от местонахождения.</span><span class="sxs-lookup"><span data-stu-id="9caa7-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="9caa7-129">При развертывании корпоративной голосовой связи вы настраиваете абонентские группы в рамках этого развертывания и должны быть уверены, что абонентские группы также должны поддерживать Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="9caa7-130">Если вы не развертываете корпоративную голосовую связь, необходимо настроить абонентские группы для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="9caa7-131">Настройте абонентские группы с помощью панели управления Lync Server 2013 или Командная консоль Lync Server, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="9caa7-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="9caa7-132">Создайте одну или несколько абонентских групп для маршрутизации доступа по телефонной линии телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="9caa7-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="9caa7-p105">Назначьте каждому пулу абонентскую группу по умолчанию. Установите в параметре <strong>Dial-in conferencing region (Регион конференц-связи с телефонным подключением)</strong> географическое расположение, которому соответствует эта абонентская группа. Регион связывает абонентскую группу с номерами доступа по телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="9caa7-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9caa7-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Настройка абонентских планов для конференц-связи с телефонным подключением в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-141"><strong>Убедитесь, что абонентским группам назначены регионы</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-142">Выполните командлеты <strong>Get – CsDialPlan</strong> и <strong>Set – CsDialPlan</strong> , чтобы убедиться, что для всех абонентских абонентов назначен регион.</span><span class="sxs-lookup"><span data-stu-id="9caa7-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Убедитесь, что в телефонных планах Lync Server 2013 назначены регионы</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-148"><strong>Проверка или изменение требований персонального идентификационного номера (ПИН-кода) пользователя (необязательно)</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-149">Используйте панель управления Lync Server 2013 или командную консоль Lync Server для просмотра или изменения <strong>политики ПИН-кодов</strong>для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="9caa7-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="9caa7-150">Можно задать минимальную длину ПИН-кода, максимальное количество попыток входа, истечение срока действия ПИН-кода, а также указать, разрешены ли общие шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9caa7-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Необязательно Проверка параметров политики ПИН-кода в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-155"><strong>Настройка политики конференц-связи для поддержки конференц-связи с телефонным подключением</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-156">Настройте параметры <strong>политики Конференц</strong> -связи с помощью панели управления lync Server 2013 или консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9caa7-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="9caa7-157">Укажите следующее.</span><span class="sxs-lookup"><span data-stu-id="9caa7-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="9caa7-158">Разрешено ли телефонное подключение к конференции в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9caa7-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="9caa7-159">Могут ли пользователи приглашать анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="9caa7-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="9caa7-p108">Могут ли непроверенные пользователи присоединяться к конференции с помощью телефонного подключения. При присоединении с обратным звонком сервер конференций звонит пользователю, и пользователь отвечает по телефону, чтобы присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="9caa7-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9caa7-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Настройка политики конференц-связи с телефонным подключением в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-166"><strong>Настройка номеров доступа по телефонной линии</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-167">Используйте панель управления Lync Server 2013 или командную консоль Lync Server, чтобы настроить номера доступа для телефонного подключения, вызываемые пользователями для связи с Конференцией, и указать регионы, которые связывают номер доступа с соответствующими абонентской абонентской настройкой.</span><span class="sxs-lookup"><span data-stu-id="9caa7-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="9caa7-168">Первые три номера доступа для региона, указанные абонентской группой организатора, включаются в приглашение на конференцию.</span><span class="sxs-lookup"><span data-stu-id="9caa7-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="9caa7-169">Все номера доступа доступны на странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9caa7-170">После создания номеров доступа для телефонного подключения можно использовать командлет <STRONG>Set – CsDialInConferencingAccessNumber</STRONG> , чтобы изменить отображаемое имя контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.</span><span class="sxs-lookup"><span data-stu-id="9caa7-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="9caa7-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-175"><strong>Проверка параметров конференц-связи с телефонным подключением (необязательно)</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-176">С помощью командлета <strong>Get-CsDialinConferencingAccessNumber</strong> найдите абонентские группы, имеющие регион конференц-связи с телефонным подключением, который не используется ни одним номером доступа, а также найдите номера доступа, которым не назначен регион.</span><span class="sxs-lookup"><span data-stu-id="9caa7-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="9caa7-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="9caa7-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Необязательно Проверка параметров конференц-связи с телефонным подключением в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-183"><strong>Изменение сопоставления клавиш для команд DTMF (необязательно)</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-184">С помощью командлета <strong>Set-CsDialinConferencingDtmfConfiguration</strong> измените сочетания клавиш, используемые для команд тонального набора (DTMF), которые могут использоваться участниками для управления параметрами конференции (такими как отключение и включение звука или блокировка и разблокировка).</span><span class="sxs-lookup"><span data-stu-id="9caa7-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="9caa7-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Необязательно Изменение сопоставления клавиш для команд DTMF в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-189"><strong>Изменение функциональности присоединения к конференции и передачи оповещений (необязательно)</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-190">С помощью командлета <strong>Set-CsDialinConferencingConfiguration</strong> измените порядок работы оповещений, когда участники присоединяются к конференции или покидают ее.</span><span class="sxs-lookup"><span data-stu-id="9caa7-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Необязательно Включение и отключение объявлений о присоединении и выходе из конференции в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-195"><strong>Проверка конференц-связи с телефонным подключением (необязательно)</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-196">С помощью командлета <strong>Test-CsDialInConferencing</strong> протестируйте правильность работы номеров доступа для указанного пула.</span><span class="sxs-lookup"><span data-stu-id="9caa7-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Необязательно Проверка конференц-связи с телефонным подключением в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-201"><strong>Развертывание надстройки собраний по сети для Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-202">Разверните надстройку "собрание по сети" для Lync 2013, чтобы пользователи могли планировать конференции, поддерживающие Конференц-связь с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="9caa7-203">Надстройка "собрание по сети" для Lync 2013 устанавливается автоматически при установке Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9caa7-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-204">Администраторы</span><span class="sxs-lookup"><span data-stu-id="9caa7-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="9caa7-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Развертывание надстройки собраний по сети для Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-206"><strong>Настройка параметров учетных записей пользователей</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-207">С помощью панели управления Lync Server 2013 или командной консоли Lync Server настройте <strong>универсальный код ресурса (URI)</strong> телефонной линии в качестве уникального нормализованного номера телефона (например, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="9caa7-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="9caa7-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9caa7-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="9caa7-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="9caa7-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9caa7-211"><a href="lync-server-2013-configure-user-account-settings.md">Настройка параметров учетных записей пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9caa7-212">Предложен Настройка каталогов конференций</span><span class="sxs-lookup"><span data-stu-id="9caa7-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="9caa7-213">Используйте командлет <strong>New-CsConferenceDirectory</strong> для создания одного каталога конференций для каждых 999 пользователей в пуле.</span><span class="sxs-lookup"><span data-stu-id="9caa7-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9caa7-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Требования к конференц-связи с телефонным подключением в Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(рекомендуется) создание каталогов конференций</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9caa7-216"><strong>Приглашение пользователей принять участие в конференц-связи с телефонным подключением и установка начальных ПИН-кодов (необязательно)</strong></span><span class="sxs-lookup"><span data-stu-id="9caa7-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="9caa7-217">С помощью скрипта <strong>Set-CsPinSendCAWelcomeMail</strong> установите начальные ПИН-коды пользователей и отправьте приветственное сообщение, содержащее начальный ПИН-код и ссылку на страницу параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="9caa7-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="9caa7-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9caa7-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9caa7-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Необязательно Добро пожаловать в Конференц-связь с телефонным подключением в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9caa7-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

