---
title: 'Lync Server 2013: назначение политик присутствия на уровне пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905065e231869b4b6075fc1894e51c91df8f0aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="fd409-102">Назначение политик присутствия по каждому пользователю в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd409-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd409-103">_**Тема последнего изменения:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="fd409-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="fd409-104">Политика присутствия — это набор ограничений и ограничений, влияющих на присутствие.</span><span class="sxs-lookup"><span data-stu-id="fd409-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="fd409-105">В приведенной ниже таблице описаны параметры политики присутствия, доступные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd409-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="fd409-106">Параметры политики присутствия</span><span class="sxs-lookup"><span data-stu-id="fd409-106">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd409-107">Имя XML</span><span class="sxs-lookup"><span data-stu-id="fd409-107">XML name</span></span></th>
<th><span data-ttu-id="fd409-108">Отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="fd409-108">Display name</span></span></th>
<th><span data-ttu-id="fd409-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fd409-109">Description</span></span></th>
<th><span data-ttu-id="fd409-110">Тип</span><span class="sxs-lookup"><span data-stu-id="fd409-110">Type</span></span></th>
<th><span data-ttu-id="fd409-111">Значение</span><span class="sxs-lookup"><span data-stu-id="fd409-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd409-112">Категорисубскриптионс</span><span class="sxs-lookup"><span data-stu-id="fd409-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="fd409-113">Максимальное число подписок на категорию подписчика</span><span class="sxs-lookup"><span data-stu-id="fd409-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="fd409-114">Ограничивает число подписок на категорию подписчиков.</span><span class="sxs-lookup"><span data-stu-id="fd409-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="fd409-115">Например, если программа Communicator подписалась на присутствие пользователя, она получает подписку на категорию для каждой карточки контакта, данных календаря, заметок, служб и категорий состояний.</span><span class="sxs-lookup"><span data-stu-id="fd409-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="fd409-116">Значение 0 означает, что пользователь или объект контакта не может подписаться другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="fd409-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fd409-117">Этот параметр может существенно повлиять на производительность, если его значение установлено на большое число, а в среднем пользователь имеет большое количество пользователей, которые подписались на его присутствие.</span><span class="sxs-lookup"><span data-stu-id="fd409-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="fd409-118">Целое число</span><span class="sxs-lookup"><span data-stu-id="fd409-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="fd409-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="fd409-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd409-120">Промптедсубскриберс</span><span class="sxs-lookup"><span data-stu-id="fd409-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="fd409-121">Максимальное количество уведомлений о подписке на состояние присутствия в очереди</span><span class="sxs-lookup"><span data-stu-id="fd409-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="fd409-122">Ограничивает количество записей в таблице "запрашиваемые абоненты".</span><span class="sxs-lookup"><span data-stu-id="fd409-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="fd409-123">Этот параметр определяет максимальное количество запросов, которые можно поместить в очередь для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="fd409-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="fd409-124">Например, если пользователь A подписался на присутствие пользователя B, пользователь B получает сообщение о том, что пользователь A теперь подписан на пользователя B, и в таблице подписчиков пользователя B создается запрос подтверждения.</span><span class="sxs-lookup"><span data-stu-id="fd409-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="fd409-125">После того как пользователь B подтвердит, что подписку будет удалена, запрос подтверждения удаляется из таблицы подписчиков пользователя B.</span><span class="sxs-lookup"><span data-stu-id="fd409-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="fd409-126">Нулевое значение означает, что пользователю не будет предлагаться подписаться на свое присутствие.</span><span class="sxs-lookup"><span data-stu-id="fd409-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="fd409-127">Целое число или маркер</span><span class="sxs-lookup"><span data-stu-id="fd409-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="fd409-128">0-500</span><span class="sxs-lookup"><span data-stu-id="fd409-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd409-129">По умолчанию политика и **Служба** **по умолчанию** устанавливаются при развертывании сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd409-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="fd409-130">В приведенной ниже таблице описаны конкретные параметры двух политик присутствия.</span><span class="sxs-lookup"><span data-stu-id="fd409-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="fd409-131">Политики присутствия</span><span class="sxs-lookup"><span data-stu-id="fd409-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd409-132">Название политики</span><span class="sxs-lookup"><span data-stu-id="fd409-132">Policy name</span></span></th>
<th><span data-ttu-id="fd409-133">Описание</span><span class="sxs-lookup"><span data-stu-id="fd409-133">Description</span></span></th>
<th><span data-ttu-id="fd409-134">Категорисубскриптионс</span><span class="sxs-lookup"><span data-stu-id="fd409-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="fd409-135">Промптедсубскриберс</span><span class="sxs-lookup"><span data-stu-id="fd409-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd409-136">Политика по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fd409-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="fd409-137">Политика для обычных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fd409-137">Policy for typical users.</span></span> <span data-ttu-id="fd409-138">Это политика присутствия по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd409-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="fd409-139">1000</span><span class="sxs-lookup"><span data-stu-id="fd409-139">1000</span></span></p></td>
<td><p><span data-ttu-id="fd409-140">200</span><span class="sxs-lookup"><span data-stu-id="fd409-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd409-141">Служба: средняя</span><span class="sxs-lookup"><span data-stu-id="fd409-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="fd409-142">Политика для приложений, которым больше пользователей нужно подписаться на присутствие объекта.</span><span class="sxs-lookup"><span data-stu-id="fd409-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="fd409-143">1000</span><span class="sxs-lookup"><span data-stu-id="fd409-143">1000</span></span></p></td>
<td><p><span data-ttu-id="fd409-144">до</span><span class="sxs-lookup"><span data-stu-id="fd409-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

