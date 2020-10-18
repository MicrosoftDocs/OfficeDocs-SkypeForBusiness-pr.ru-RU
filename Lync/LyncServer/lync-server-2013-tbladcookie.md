---
title: 'Lync Server 2013: tblADCookie'
description: 'Lync Server 2013: tblADCookie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573725"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="1af46-103">tblADCookie в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1af46-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1af46-104">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="1af46-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="1af46-105">tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.</span><span class="sxs-lookup"><span data-stu-id="1af46-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="1af46-106">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1af46-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1af46-107">Столбец</span><span class="sxs-lookup"><span data-stu-id="1af46-107">Column</span></span></th>
<th><span data-ttu-id="1af46-108">Тип</span><span class="sxs-lookup"><span data-stu-id="1af46-108">Type</span></span></th>
<th><span data-ttu-id="1af46-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1af46-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1af46-110">прингуид</span><span class="sxs-lookup"><span data-stu-id="1af46-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="1af46-111">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="1af46-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1af46-112">GUID субъекта для домена, за которым осуществляется мониторинг.</span><span class="sxs-lookup"><span data-stu-id="1af46-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af46-113">приндчост</span><span class="sxs-lookup"><span data-stu-id="1af46-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="1af46-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="1af46-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="1af46-115">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</span><span class="sxs-lookup"><span data-stu-id="1af46-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af46-116">адкконтент</span><span class="sxs-lookup"><span data-stu-id="1af46-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="1af46-117">image (binary)</span><span class="sxs-lookup"><span data-stu-id="1af46-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="1af46-118">Файл cookie синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1af46-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af46-119">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="1af46-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="1af46-120">datetime</span><span class="sxs-lookup"><span data-stu-id="1af46-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="1af46-121">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="1af46-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1af46-122">локкедунтил</span><span class="sxs-lookup"><span data-stu-id="1af46-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="1af46-123">datetime</span><span class="sxs-lookup"><span data-stu-id="1af46-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="1af46-p101">время, до которого строка заблокирована для внесения изменений. Это часть механизма программной блокировки, которая обеспечивает одновременное выполнение синхронизации Active Directory только одной службой чата.</span><span class="sxs-lookup"><span data-stu-id="1af46-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1af46-126">Keys</span><span class="sxs-lookup"><span data-stu-id="1af46-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1af46-127">Столбцы</span><span class="sxs-lookup"><span data-stu-id="1af46-127">Column(s)</span></span></th>
<th><span data-ttu-id="1af46-128">Описание</span><span class="sxs-lookup"><span data-stu-id="1af46-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1af46-129">прингуид</span><span class="sxs-lookup"><span data-stu-id="1af46-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="1af46-130">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="1af46-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1af46-131">прингуид</span><span class="sxs-lookup"><span data-stu-id="1af46-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="1af46-132">Внешний ключ с поиском в таблице Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="1af46-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

