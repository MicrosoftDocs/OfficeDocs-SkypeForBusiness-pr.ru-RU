---
title: 'Lync Server 2013: назначение политик присутствия для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 618ab1b18f92d19f65084d321b71219cc0fafb06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="ffafd-102">Назначение политик присутствия для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffafd-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffafd-103">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="ffafd-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="ffafd-104">Политика присутствия представляет собой набор ограничений, которые влияют на данные присутствия.</span><span class="sxs-lookup"><span data-stu-id="ffafd-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="ffafd-105">В следующей таблице описываются параметры политики присутствия, доступные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ffafd-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="ffafd-106">Параметры политики присутствия</span><span class="sxs-lookup"><span data-stu-id="ffafd-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="ffafd-107">Имя XML-файла</span><span class="sxs-lookup"><span data-stu-id="ffafd-107">XML name</span></span></th>
<th><span data-ttu-id="ffafd-108">Отображаемое имя</span><span class="sxs-lookup"><span data-stu-id="ffafd-108">Display name</span></span></th>
<th><span data-ttu-id="ffafd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ffafd-109">Description</span></span></th>
<th><span data-ttu-id="ffafd-110">Тип</span><span class="sxs-lookup"><span data-stu-id="ffafd-110">Type</span></span></th>
<th><span data-ttu-id="ffafd-111">Значение</span><span class="sxs-lookup"><span data-stu-id="ffafd-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffafd-112">категорисубскриптионс</span><span class="sxs-lookup"><span data-stu-id="ffafd-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="ffafd-113">Максимальное число подписок на категории подписчика</span><span class="sxs-lookup"><span data-stu-id="ffafd-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="ffafd-p102">Ограничение числа подписок на категории подписчика. Например, когда подписчик Communicator подписывается на данные присутствия пользователя, он получает подписку на категорию для всех карточек контакта, данных календаря, заметок, служб и категорий состояния.</span><span class="sxs-lookup"><span data-stu-id="ffafd-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="ffafd-116">Значение "0" означает, что на данный контактный объект или пользователя не могут подписаться другие пользователи.</span><span class="sxs-lookup"><span data-stu-id="ffafd-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ffafd-117">Этот параметр может иметь существенное влияние на производительность, если для него задано большое значение, и средний пользователь имеет большое количество пользователей, подписывающихся на данные о его присутствии.</span><span class="sxs-lookup"><span data-stu-id="ffafd-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="ffafd-118">Целое число</span><span class="sxs-lookup"><span data-stu-id="ffafd-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="ffafd-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="ffafd-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffafd-120">промптедсубскриберс</span><span class="sxs-lookup"><span data-stu-id="ffafd-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="ffafd-121">Максимальное число оповещений о подписках на присутствие в очереди</span><span class="sxs-lookup"><span data-stu-id="ffafd-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="ffafd-p103">Ограничивает число записей в таблице предложенных подписчиков. Этот параметр определяет максимальное число запросов, которые можно поместить в очередь данного пользователя. Например, когда пользователь А подписывается на данные о присуствии пользователя Б, пользователь Б получает уведомление о том, что пользователь А подписался на данные пользователя Б, и в таблице предложенных подписчиков пользователя Б создается запрос подтверждения. После того как пользователь Б примет (или подтвердит) подписку, запрос подтверждения удаляется из таблицы предложенных подписчиков пользователя Б.</span><span class="sxs-lookup"><span data-stu-id="ffafd-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="ffafd-126">Значение "0" означает, что пользователь не будет получать запрос, когда кто-то подписывается на данные о его присутствии.</span><span class="sxs-lookup"><span data-stu-id="ffafd-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="ffafd-127">Целое число или маркер</span><span class="sxs-lookup"><span data-stu-id="ffafd-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="ffafd-128">0-500</span><span class="sxs-lookup"><span data-stu-id="ffafd-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ffafd-129">По умолчанию **Политика** и **Служба среднего** уровня присутствия устанавливаются при развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ffafd-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="ffafd-130">В следующей таблице приведены параметры двух этих политик присутствия.</span><span class="sxs-lookup"><span data-stu-id="ffafd-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="ffafd-131">Политики присутствия</span><span class="sxs-lookup"><span data-stu-id="ffafd-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffafd-132">Имя политики</span><span class="sxs-lookup"><span data-stu-id="ffafd-132">Policy name</span></span></th>
<th><span data-ttu-id="ffafd-133">Описание</span><span class="sxs-lookup"><span data-stu-id="ffafd-133">Description</span></span></th>
<th><span data-ttu-id="ffafd-134">категорисубскриптионс</span><span class="sxs-lookup"><span data-stu-id="ffafd-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="ffafd-135">промптедсубскриберс</span><span class="sxs-lookup"><span data-stu-id="ffafd-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffafd-136">Политика по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ffafd-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="ffafd-p105">Политика для обычных пользователей. Это политика присутствия по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ffafd-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="ffafd-139">1000</span><span class="sxs-lookup"><span data-stu-id="ffafd-139">1000</span></span></p></td>
<td><p><span data-ttu-id="ffafd-140">200</span><span class="sxs-lookup"><span data-stu-id="ffafd-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffafd-141">Служба: среднее</span><span class="sxs-lookup"><span data-stu-id="ffafd-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="ffafd-142">Политика для приложений, которым требуется большее число пользователей, подписывающихся на данные о присутствии объекта.</span><span class="sxs-lookup"><span data-stu-id="ffafd-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="ffafd-143">1000</span><span class="sxs-lookup"><span data-stu-id="ffafd-143">1000</span></span></p></td>
<td><p><span data-ttu-id="ffafd-144">нуль</span><span class="sxs-lookup"><span data-stu-id="ffafd-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

