---
title: 'Lync Server 2013: записи использования ТСОП'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="4f4a6-102">Записи использования ТСОП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f4a6-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f4a6-103">_**Тема последнего изменения:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="4f4a6-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="4f4a6-104">Планирование записей использования PSTN включает в себя список всех разрешений на звонки, которые в настоящее время используются в вашей организации, от Генерального директора до временных сотрудников, консультантов и сотрудников по договору.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-104">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="4f4a6-105">Кроме того, этот процесс позволяет повторно проверить существующие разрешения на вызов и исправить их.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-105">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="4f4a6-106">Вы можете создавать записи об использовании PSTN только для тех разрешений на звонки, которые применяются к предполагаемым пользователям голосовой связи, но это решение может создавать записи использования PSTN для всех разрешений на звонки, независимо от того, могут ли в данный момент отсутствовать некоторые из них. применить к группе пользователей, которые должны быть включены в рамках корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-106">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="4f4a6-107">Если добавлены разрешения на вызов изменение или добавление новых пользователей с разными разрешениями на вызов, вы будете уже созданы нужные записи использования PSTN.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-107">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="4f4a6-108">В следующей таблице приведены типичные режимы работы с ТСОП.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="4f4a6-109">Записи использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="4f4a6-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f4a6-110">Атрибут номера</span><span class="sxs-lookup"><span data-stu-id="4f4a6-110">Phone attribute</span></span></th>
<th><span data-ttu-id="4f4a6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="4f4a6-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f4a6-112">Local</span><span class="sxs-lookup"><span data-stu-id="4f4a6-112">Local</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-113">Местные звонки</span><span class="sxs-lookup"><span data-stu-id="4f4a6-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f4a6-114">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="4f4a6-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-115">Междугородние звонки</span><span class="sxs-lookup"><span data-stu-id="4f4a6-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f4a6-116">International</span><span class="sxs-lookup"><span data-stu-id="4f4a6-116">International</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-117">Международные звонки</span><span class="sxs-lookup"><span data-stu-id="4f4a6-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f4a6-118">Delhi</span><span class="sxs-lookup"><span data-stu-id="4f4a6-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-119">Штатные сотрудники, расположенные в г. Дели</span><span class="sxs-lookup"><span data-stu-id="4f4a6-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f4a6-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="4f4a6-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-121">Штатные сотрудники, расположенные в г. Редмонд</span><span class="sxs-lookup"><span data-stu-id="4f4a6-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f4a6-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="4f4a6-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-123">Временные сотрудники, расположенные в г. Редмонд</span><span class="sxs-lookup"><span data-stu-id="4f4a6-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f4a6-124">Zurich</span><span class="sxs-lookup"><span data-stu-id="4f4a6-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="4f4a6-125">Штатные сотрудники, расположенные в г. Цюрих</span><span class="sxs-lookup"><span data-stu-id="4f4a6-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f4a6-p102">Сами по себе режимы работы с ТСОП не выполняют никаких действий. Чтобы режимы работы с ТСОП начали работать, необходимо связь их со следующими данными:</span><span class="sxs-lookup"><span data-stu-id="4f4a6-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="4f4a6-128">Политики голосовых служб, назначенные пользователям.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="4f4a6-129">Маршруты, назначенные номерам телефонов.</span><span class="sxs-lookup"><span data-stu-id="4f4a6-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="4f4a6-130">Дополнительные сведения о политиках голосовой связи и маршрутах можно найти в разделе [политики голосовой связи в Lync server 2013](lync-server-2013-voice-policies.md) и [Голосовые маршруты в Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="4f4a6-131">Подробнее о том, как создать и настроить их, можно найти [в разделе Настройка голосовых маршрутов для исходящих звонков в Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="4f4a6-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

