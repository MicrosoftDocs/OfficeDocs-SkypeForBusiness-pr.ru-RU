---
title: 'Lync Server 2013: Настройка примеров видеороликов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="c6d4c-102">Настройка примеров видеороликов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6d4c-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6d4c-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c6d4c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c6d4c-104">Lync 2013 добавляет новые функции видео для 1080 1920 поддержки видео-и фотоальбомов в формате High Definition (HD) и видеофайлов в полноэкранном режиме.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="c6d4c-105">Измерения, основанные на данных о клиентах, показывают, что обычная пропускная способность видеоизображения увеличивается только в Lync 2010, но максимальная пропускная способность видеопотока увеличилась в соответствии с поддержкой полной поддержки HD (Дополнительные сведения можно найти в разделе "использование сетевого трафика мультимедиа" в [требованиях к пропускной способности сети для мультимедийного трафика в Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="c6d4c-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="c6d4c-106">Таким образом, администраторы могут ограничивать пропускную способность для определенных пользователей (например, пользователей в офисе филиалов с меньшим количеством сетевых ресурсов) и помогают обеспечить наилучшее качество видео для других пользователей (например, для руководителей).</span><span class="sxs-lookup"><span data-stu-id="c6d4c-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="c6d4c-107">В таблице ниже приведен список рекомендуемых параметров настройки видео для разных сетевых мощностей.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="c6d4c-108">Эти настройки ограничивают некоторые пользовательские сценарии от отправки и получения видеороликов с более высоким разрешением (см. правый столбец).</span><span class="sxs-lookup"><span data-stu-id="c6d4c-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="c6d4c-109">В результате минимально допустимой пропускной способности сети может быть недоступен видео из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="c6d4c-110">Рекомендуемые параметры видео</span><span class="sxs-lookup"><span data-stu-id="c6d4c-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="c6d4c-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="c6d4c-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="c6d4c-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="c6d4c-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="c6d4c-113">видеобитратекб</span><span class="sxs-lookup"><span data-stu-id="c6d4c-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="c6d4c-114">тоталрецеивевидеобитратекб</span><span class="sxs-lookup"><span data-stu-id="c6d4c-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="c6d4c-115">Ожидаемое разрешение видео для хорошего качества видео</span><span class="sxs-lookup"><span data-stu-id="c6d4c-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6d4c-116">Повышения</span><span class="sxs-lookup"><span data-stu-id="c6d4c-116">Best</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-117">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-117">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-118">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-118">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-119">8000</span><span class="sxs-lookup"><span data-stu-id="c6d4c-119">8000</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-120">8000</span><span class="sxs-lookup"><span data-stu-id="c6d4c-120">8000</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-121">Одноранговая сеть: до 1920 x 1080 разрешение видео</span><span class="sxs-lookup"><span data-stu-id="c6d4c-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="c6d4c-122">Режим коллекции: до 2 1920 x 1080 видео или несколько изображений с небольшим разрешением</span><span class="sxs-lookup"><span data-stu-id="c6d4c-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d4c-123">Good</span><span class="sxs-lookup"><span data-stu-id="c6d4c-123">Good</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-124">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-124">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-125">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-125">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-126">2500</span><span class="sxs-lookup"><span data-stu-id="c6d4c-126">2500</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-127">2500</span><span class="sxs-lookup"><span data-stu-id="c6d4c-127">2500</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-128">Одноранговая сеть: до 1280 x 720 разрешение видео</span><span class="sxs-lookup"><span data-stu-id="c6d4c-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="c6d4c-129">Представление "Коллекция": видео с разрешением до 5 640 x 360</span><span class="sxs-lookup"><span data-stu-id="c6d4c-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d4c-130">Средняя</span><span class="sxs-lookup"><span data-stu-id="c6d4c-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-131">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-131">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-132">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-132">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-133">1000</span><span class="sxs-lookup"><span data-stu-id="c6d4c-133">1000</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-134">1000</span><span class="sxs-lookup"><span data-stu-id="c6d4c-134">1000</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-135">Одноранговая сеть: до 960 x 540 разрешение видео</span><span class="sxs-lookup"><span data-stu-id="c6d4c-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="c6d4c-136">Представление "Коллекция": видео с разрешением до 5 424 x 240</span><span class="sxs-lookup"><span data-stu-id="c6d4c-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d4c-137">Минимум</span><span class="sxs-lookup"><span data-stu-id="c6d4c-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-138">Верно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-138">True</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-139">False</span><span class="sxs-lookup"><span data-stu-id="c6d4c-139">False</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-140">350</span><span class="sxs-lookup"><span data-stu-id="c6d4c-140">350</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-141">350</span><span class="sxs-lookup"><span data-stu-id="c6d4c-141">350</span></span></p></td>
<td><p><span data-ttu-id="c6d4c-142">Одноранговая сеть: до 424 x 240 разрешение видео</span><span class="sxs-lookup"><span data-stu-id="c6d4c-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="c6d4c-143">Представление коллекции: недоступно</span><span class="sxs-lookup"><span data-stu-id="c6d4c-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6d4c-144">Вы можете использовать сведения из приведенной выше таблицы для развертывания новых возможностей видеоконференций и коллекций видео для некоторых пользователей в вашей организации, в то же время разрешив разные разрешения для других.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="c6d4c-145">В приведенном ниже примере администратор разворачивает новые функции видео, которые обеспечивают высочайшее качество видео, доступное только для руководителей.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="c6d4c-146">Для сотрудников в удаленном офисе филиала, у которых низкая емкость сети, развернут только минимальный параметр из предыдущей таблицы.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="c6d4c-147">Для всех других сотрудников развернут параметр "хорошее" из предыдущей таблицы.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="c6d4c-148">Чтобы выполнить развертывание новых функций для руководителей, администратор создает политику конференц-связи с именем Ексекутивевидео.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="c6d4c-149">Ниже указаны параметры этой политики для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="c6d4c-150">Для Видеобитратекб установлено значение 8000 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="c6d4c-151">Для Тоталрецеивевидеобитратекб установлено значение 8000 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="c6d4c-152">Для Алловмултивиев установлено значение true</span><span class="sxs-lookup"><span data-stu-id="c6d4c-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="c6d4c-153">Для Енаблемултивиевжоин установлено значение true</span><span class="sxs-lookup"><span data-stu-id="c6d4c-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="c6d4c-154">Для сотрудников офиса подразделения администратор создает политику конференц-связи с именем Бранчоффицевидео.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="c6d4c-155">Ниже указаны параметры этой политики для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="c6d4c-156">Для Видеобитратекб установлено значение 350 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="c6d4c-157">Для Тоталрецеивевидеобитратекб установлено значение 350 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="c6d4c-158">Для Алловмултивиев установлено значение true</span><span class="sxs-lookup"><span data-stu-id="c6d4c-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="c6d4c-159">Для Енаблемултивиевжоин задано значение false</span><span class="sxs-lookup"><span data-stu-id="c6d4c-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="c6d4c-160">Для всех других сотрудников администратор создает политику конференц-связи с именем Стандардвидео.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="c6d4c-161">Ниже указаны параметры этой политики для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="c6d4c-162">Для Видеобитратекб установлено значение 2500 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="c6d4c-163">Для Тоталрецеивевидеобитратекб установлено значение 2500 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="c6d4c-164">Для Алловмултивиев установлено значение true</span><span class="sxs-lookup"><span data-stu-id="c6d4c-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="c6d4c-165">Для Енаблемултивиевжоин установлено значение true</span><span class="sxs-lookup"><span data-stu-id="c6d4c-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="c6d4c-166">Администратор назначает пользователям политику конференций, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="c6d4c-167">Политика конференц-связи Ексекутивевидео назначается для руководителей.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="c6d4c-168">Политика конференц-связи Бранчоффицевидео назначается всем сотрудникам в офисе филиала.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="c6d4c-169">Политика конференц-связи Стандардвидео назначается всем остальным сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="c6d4c-170">Эти назначения политик конференц-связи приводят к следующим действиям пользователя:</span><span class="sxs-lookup"><span data-stu-id="c6d4c-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="c6d4c-171">Все конференции, организованные любым пользователем в представлении коллекции, но сотрудники филиала не смогут работать с ним в режиме галереи.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="c6d4c-172">Для любой из двух или многосторонних конференций руководитель может отправить 1920 x 1080 High HD видео, если его оборудование и сетевая связь поддерживаются, а также получить 1920 x 1080 Full HD видео, в котором его смогут поддерживать другие участники.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="c6d4c-173">Сотрудникам, которые не предназначены для руководителей, более низкие разрешения, чем у руководителей, использующих две или многосторонние конференции, но по-прежнему имеют хорошее разрешение.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="c6d4c-174">Сотрудники филиалов будут получать качественное качество видеосвязи при использовании двух сторон, когда Lync отображает размер окна видео по умолчанию. Однако если окно Lync развернуто на весь экран, разрешение экрана не будет увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="c6d4c-175">У сотрудников филиалов есть только один активный видеоролик для многосторонних конференций.</span><span class="sxs-lookup"><span data-stu-id="c6d4c-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

