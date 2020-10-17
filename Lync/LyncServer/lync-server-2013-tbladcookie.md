---
title: 'Lync Server 2013: tblADCookie'
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
ms.openlocfilehash: bf372f3dfc39f3ca90cbe0019af09e8d9dd33d26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509516"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="8c1c1-102">tblADCookie в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c1c1-102">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c1c1-103">_**Последнее изменение темы:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8c1c1-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8c1c1-104">tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="8c1c1-105">Столбцы</span><span class="sxs-lookup"><span data-stu-id="8c1c1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c1c1-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="8c1c1-106">Column</span></span></th>
<th><span data-ttu-id="8c1c1-107">Тип</span><span class="sxs-lookup"><span data-stu-id="8c1c1-107">Type</span></span></th>
<th><span data-ttu-id="8c1c1-108">Описание</span><span class="sxs-lookup"><span data-stu-id="8c1c1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c1c1-109">прингуид</span><span class="sxs-lookup"><span data-stu-id="8c1c1-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-110">GUID, не NULL</span><span class="sxs-lookup"><span data-stu-id="8c1c1-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-111">GUID субъекта для домена, за которым осуществляется мониторинг.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c1c1-112">приндчост</span><span class="sxs-lookup"><span data-stu-id="8c1c1-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="8c1c1-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-114">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c1c1-115">адкконтент</span><span class="sxs-lookup"><span data-stu-id="8c1c1-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="8c1c1-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-117">Файл cookie синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c1c1-118">ластупдатед</span><span class="sxs-lookup"><span data-stu-id="8c1c1-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-119">datetime</span><span class="sxs-lookup"><span data-stu-id="8c1c1-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c1c1-121">локкедунтил</span><span class="sxs-lookup"><span data-stu-id="8c1c1-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="8c1c1-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-p101">время, до которого строка заблокирована для внесения изменений. Это часть механизма программной блокировки, которая обеспечивает одновременное выполнение синхронизации Active Directory только одной службой чата.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8c1c1-125">Keys</span><span class="sxs-lookup"><span data-stu-id="8c1c1-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c1c1-126">Столбцы</span><span class="sxs-lookup"><span data-stu-id="8c1c1-126">Column(s)</span></span></th>
<th><span data-ttu-id="8c1c1-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8c1c1-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c1c1-128">прингуид</span><span class="sxs-lookup"><span data-stu-id="8c1c1-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c1c1-130">прингуид</span><span class="sxs-lookup"><span data-stu-id="8c1c1-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="8c1c1-131">Внешний ключ с поиском в таблице Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="8c1c1-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

