---
title: 'Lync Server 2013: процесс развертывания для парковки звонков'
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
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="b982c-102">Процесс развертывания для парковки звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b982c-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b982c-103">_**Тема последнего изменения:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="b982c-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="b982c-104">В этом разделе приводятся общие сведения о том, как развернуть приложение для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="b982c-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="b982c-105">Перед настройкой приостановки звонка необходимо развернуть Enterprise Edition или Standard Edition с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="b982c-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="b982c-106">Компоненты, необходимые для парковки звонков, устанавливаются и включаются при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b982c-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="b982c-107">Процесс развертывания парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="b982c-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b982c-108">Этап</span><span class="sxs-lookup"><span data-stu-id="b982c-108">Phase</span></span></th>
<th><span data-ttu-id="b982c-109">Шаги</span><span class="sxs-lookup"><span data-stu-id="b982c-109">Steps</span></span></th>
<th><span data-ttu-id="b982c-110">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="b982c-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="b982c-111">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="b982c-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b982c-112">Настройка диапазонов орбит парковки вызовов в таблице орбит</span><span class="sxs-lookup"><span data-stu-id="b982c-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="b982c-113">С помощью панели управления Lync Server или командлета <strong>New-кскаллпаркорбит</strong> создайте диапазоны на орбите в таблице с приостановкой на орбиту и свяжите их со службой приложения, на которой размещается приложение для приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="b982c-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b982c-p102">Для простой интеграции с существующими абонентскими группами диапазоны орбит обычно настраиваются как блок виртуальных расширений. Назначение номеров DID как номеров орбит в таблице орбит парковки вызовов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b982c-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="b982c-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b982c-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b982c-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b982c-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b982c-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b982c-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Создание или изменение диапазона орбиты на расстоянии вверх на сервере Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b982c-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b982c-121">Настройка параметров парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="b982c-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="b982c-122">Используйте командлет <strong>Set-кскпсконфигуратион</strong> , чтобы настроить параметры парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="b982c-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="b982c-123">Рекомендуется настроить параметр <strong>онтимеаутури</strong> для настройки резервного назначения для использования по истечении времени ожидания звонка. Вы также можете настроить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b982c-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="b982c-124"><strong>EnableMusicOnHold</strong> для включения и выключения музыки при удержании вызова (необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="b982c-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="b982c-125"><strong>MaxCallPickupAttempts</strong> для определения количества ответных звонков для припаркованных вызовов в адрес отвечающего телефона перед переадресацией звонка на резервный URI (необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="b982c-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="b982c-126"><strong>CallPickupTimeoutThreshold</strong> для определения времени между парковкой вызова и вызовом телефонного номера, по которому на вызов был получен ответ (необязательный параметр).</span><span class="sxs-lookup"><span data-stu-id="b982c-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b982c-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b982c-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b982c-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b982c-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b982c-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b982c-131"><a href="lync-server-2013-configure-call-park-settings.md">Настройка параметров парковки звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b982c-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b982c-132">Можно настроить музыку при удержании (необязательно)</span><span class="sxs-lookup"><span data-stu-id="b982c-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="b982c-133">Используйте командлет <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> для настройки и загрузки аудиофайла, если вы не хотите использовать стандартную музыку при удержании.</span><span class="sxs-lookup"><span data-stu-id="b982c-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="b982c-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b982c-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b982c-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b982c-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b982c-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b982c-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Настройка музыкального сопровождения для приема звонков на удержании в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b982c-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b982c-139">Настройка политики голосовой связи для поддержки приостановки звонков для пользователей</span><span class="sxs-lookup"><span data-stu-id="b982c-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="b982c-140">С помощью панели управления Lync Server или командлета <strong>Set-ксвоицеполици</strong> с параметром <strong>енаблекаллпарк</strong> , чтобы включить приостановку звонков для пользователей в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b982c-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b982c-141">По умолчанию приостановление звонков для всех пользователей отключено.</span><span class="sxs-lookup"><span data-stu-id="b982c-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="b982c-142">При наличии нескольких политик голосовой связи убедитесь в том, что свойство EnableCallPark задано для каждой политики голосовой связи, а не только для политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b982c-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="b982c-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b982c-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b982c-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b982c-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="b982c-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b982c-147"><a href="lync-server-2013-enable-call-park-for-users.md">Включение приостановки звонков для пользователей в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b982c-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b982c-148">Проверка правил нормализации для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="b982c-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="b982c-p104">Орбиты парковки вызовов не требуют нормализации. Убедитесь, что правила нормализации не включают ваши диапазоны орбиты. При необходимости создайте дополнительные правила нормализации для блокирования нормализации орбит.</span><span class="sxs-lookup"><span data-stu-id="b982c-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="b982c-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b982c-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="b982c-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="b982c-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="b982c-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="b982c-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="b982c-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Проверка правил нормализации для парковки звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b982c-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b982c-157">Проверка развертывания для остановки звонка</span><span class="sxs-lookup"><span data-stu-id="b982c-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="b982c-158">Проверьте парковку и извлечение вызовов, чтобы убедиться в том, что конфигурация работает корректно.</span><span class="sxs-lookup"><span data-stu-id="b982c-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="b982c-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Необязательно Проверка развертывания парковки звонков в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b982c-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

