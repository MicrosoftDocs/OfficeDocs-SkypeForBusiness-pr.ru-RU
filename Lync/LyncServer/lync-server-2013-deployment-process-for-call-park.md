---
title: 'Lync Server 2013: процесс развертывания для парковки вызовов'
description: 'Lync Server 2013: процесс развертывания для парковки вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 149252d39ba3fc0c552900c87e453c60e1651a08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575715"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="e82b4-103">Процесс развертывания для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e82b4-103">Deployment process for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e82b4-104">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="e82b4-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="e82b4-105">В этом разделе представлен обзор действий, необходимых для развертывания приложения парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e82b4-105">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="e82b4-106">Перед настройкой парковки вызовов необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="e82b4-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="e82b4-107">Компоненты, необходимые для парковки вызовов, устанавливаются и включаются при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e82b4-107">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="e82b4-108">Процесс развертывания парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="e82b4-108">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e82b4-109">Этап</span><span class="sxs-lookup"><span data-stu-id="e82b4-109">Phase</span></span></th>
<th><span data-ttu-id="e82b4-110">Действия</span><span class="sxs-lookup"><span data-stu-id="e82b4-110">Steps</span></span></th>
<th><span data-ttu-id="e82b4-111">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="e82b4-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="e82b4-112">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="e82b4-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e82b4-113">Настройка диапазонов орбит парковки вызовов в таблице орбит</span><span class="sxs-lookup"><span data-stu-id="e82b4-113">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="e82b4-114">С помощью панели управления Lync Server или командлета <strong>New – CSCallParkOrbit</strong> создайте Диапазоны орбит в таблице орбит парковки вызовов и свяжите их со службой приложения, в которой размещается приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e82b4-114">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e82b4-p102">Для простой интеграции с существующими абонентскими группами диапазоны орбит обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров орбит в таблице орбит парковки вызовов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e82b4-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="e82b4-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e82b4-117">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e82b4-118">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-118">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-119">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-120">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-120">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e82b4-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e82b4-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e82b4-122">Настройка параметров приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="e82b4-122">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="e82b4-123">Используйте командлет <strong>Set – CsCpsConfiguration</strong> для настройки параметров парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e82b4-123">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="e82b4-124">Рекомендуется настроить параметр <strong>OnTimeoutURI</strong> для настройки резервного назначения для использования при истечении времени ожидания приостановленного вызова. Кроме того, можно настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e82b4-124">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="e82b4-125"><strong>EnableMusicOnHold</strong> для включения и выключения музыки при удержании вызова (необязательный параметр);</span><span class="sxs-lookup"><span data-stu-id="e82b4-125">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="e82b4-126"><strong>MaxCallPickupAttempts</strong> для определения количества ответных звонков припаркованным вызовом в адрес отвечающего телефона до переадресации звонка на резервный URI (необязательный параметр);</span><span class="sxs-lookup"><span data-stu-id="e82b4-126">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="e82b4-127"><strong>CallPickupTimeoutThreshold</strong> для определения времени между парковкой вызова и вызовом телефонного номера, по которому на вызов был получен ответ (необязательный параметр);</span><span class="sxs-lookup"><span data-stu-id="e82b4-127">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e82b4-128">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e82b4-128">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e82b4-129">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-129">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-130">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-131">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-131">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e82b4-132"><a href="lync-server-2013-configure-call-park-settings.md">Настройка параметров парковки вызовов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e82b4-132"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e82b4-133">Можно настроить музыку при удержании (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e82b4-133">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="e82b4-134">Используйте командлет <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> для настройки и загрузки аудиофайла, если вы не хотите использовать стандартную музыку при удержании.</span><span class="sxs-lookup"><span data-stu-id="e82b4-134">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="e82b4-135">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e82b4-135">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e82b4-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-136">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-137">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-137">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-138">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-138">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e82b4-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Настройка музыки парковки вызовов на удержании в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e82b4-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e82b4-140">Настройка политики голосовой связи для включения парковки вызовов для пользователей</span><span class="sxs-lookup"><span data-stu-id="e82b4-140">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="e82b4-141">Используйте панель управления Lync Server или командлет <strong>Set – CSVoicePolicy</strong> с параметром <strong>enablecallpark задано</strong> , чтобы включить приостановку вызовов для пользователей в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e82b4-141">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e82b4-142">По умолчанию парковки вызовов отключен для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="e82b4-142">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="e82b4-143">При наличии нескольких политик голосовой связи убедитесь в том, что свойство EnableCallPark задано для каждой политики голосовой связи, а не только для политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e82b4-143">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="e82b4-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e82b4-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e82b4-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-146">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-146">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e82b4-148"><a href="lync-server-2013-enable-call-park-for-users.md">Включение парковки вызовов для пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e82b4-148"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e82b4-149">Проверка правил нормализации для приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="e82b4-149">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="e82b4-p104">Орбиты парковки вызовов не требуют нормализации. Убедитесь, что правила нормализации не включают ваши диапазоны орбиты. При необходимости создайте дополнительные правила нормализации для блокирования нормализации орбит.</span><span class="sxs-lookup"><span data-stu-id="e82b4-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="e82b4-153">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e82b4-153">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e82b4-154">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-154">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-155">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-155">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e82b4-156">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e82b4-156">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e82b4-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Проверка правил нормализации для парковки вызовов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e82b4-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e82b4-158">Проверка развертывания парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="e82b4-158">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="e82b4-159">Проверка парковки и получение вызовов убедитесь, что конфигурация работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="e82b4-159">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e82b4-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Необязательно Проверка развертывания парковки вызовов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e82b4-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

