---
title: 'Lync Server 2013: записи об использовании PSTN'
description: 'Lync Server 2013: записи об использовании PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565585"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="25754-103">Записи использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25754-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25754-104">_**Последнее изменение темы:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="25754-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="25754-p101">Планирование режимов работы с ТСОП в основном состоит из составления списка всех разрешений звонков, действующих в организации, начиная с генерального директора и заканчивая временными работниками, консультантами и работниками по контракту. Этот процесс позволяет перепроверять существующие разрешения звонков и вносить в них изменения. Вы можете создавать режимы работы с ТСОП только для тех разрешений звонков, которые будут применяться к предполагаемым пользователям корпоративной голосовой связи. Однако более рационально создавать режимы работы с ТСОП для всех разрешений звонков независимо от того, будут ли некоторые из них в настоящее время применяться к группе пользователей, включаемых для корпоративной голосовой связи. При изменении разрешений звонков или добавлении новых пользователей с разными разрешениями звонков требуемые режимы работы с ТСОП уже будут созданы.</span><span class="sxs-lookup"><span data-stu-id="25754-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="25754-109">В следующей таблице приведены типичные режимы работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="25754-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="25754-110">Режимы работы с ТСОП</span><span class="sxs-lookup"><span data-stu-id="25754-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25754-111">Атрибут номера</span><span class="sxs-lookup"><span data-stu-id="25754-111">Phone attribute</span></span></th>
<th><span data-ttu-id="25754-112">Описание</span><span class="sxs-lookup"><span data-stu-id="25754-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25754-113">Локальный</span><span class="sxs-lookup"><span data-stu-id="25754-113">Local</span></span></p></td>
<td><p><span data-ttu-id="25754-114">Местные звонки</span><span class="sxs-lookup"><span data-stu-id="25754-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25754-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="25754-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="25754-116">Междугородние звонки</span><span class="sxs-lookup"><span data-stu-id="25754-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25754-117">International</span><span class="sxs-lookup"><span data-stu-id="25754-117">International</span></span></p></td>
<td><p><span data-ttu-id="25754-118">Международные звонки</span><span class="sxs-lookup"><span data-stu-id="25754-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25754-119">Дели</span><span class="sxs-lookup"><span data-stu-id="25754-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="25754-120">Штатные сотрудники, расположенные в г. Дели</span><span class="sxs-lookup"><span data-stu-id="25754-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25754-121">Redmond</span><span class="sxs-lookup"><span data-stu-id="25754-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="25754-122">Штатные сотрудники, расположенные в г. Редмонд</span><span class="sxs-lookup"><span data-stu-id="25754-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25754-123">Назвать ее redmondtemps</span><span class="sxs-lookup"><span data-stu-id="25754-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="25754-124">Временные сотрудники, расположенные в г. Редмонд</span><span class="sxs-lookup"><span data-stu-id="25754-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25754-125">Цюрихе</span><span class="sxs-lookup"><span data-stu-id="25754-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="25754-126">Штатные сотрудники, расположенные в г. Цюрих</span><span class="sxs-lookup"><span data-stu-id="25754-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="25754-p102">Сами по себе режимы работы с ТСОП не выполняют никаких действий. Чтобы режимы работы с ТСОП начали работать, необходимо связь их со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="25754-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="25754-129">Политики голосовых служб, назначенные пользователям.</span><span class="sxs-lookup"><span data-stu-id="25754-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="25754-130">Маршруты, назначенные номерам телефонов.</span><span class="sxs-lookup"><span data-stu-id="25754-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="25754-131">Дополнительные сведения о политиках голосовой связи и маршрутах приведены в статье [политики голосовой связи в Lync server 2013](lync-server-2013-voice-policies.md) и [маршруты голосовых вызовов в Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="25754-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="25754-132">Сведения о том, как создавать и настраивать [маршруты голосовой связи, приведены в статье Настройка маршрутов голосовой связи для исходящих вызовов в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="25754-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

