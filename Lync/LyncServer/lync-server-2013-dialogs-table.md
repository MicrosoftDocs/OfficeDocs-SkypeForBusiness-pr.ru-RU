---
title: 'Lync Server 2013: таблица Dialogs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 326ecac8df81eeba11ed29ff9f1968b681cdb98f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="40951-102">Таблица Dialogs в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40951-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40951-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="40951-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="40951-104">Таблица диалогов — это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="40951-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40951-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="40951-105">Column</span></span></th>
<th><span data-ttu-id="40951-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="40951-106">Data Type</span></span></th>
<th><span data-ttu-id="40951-107">Ключ/индекс</span><span class="sxs-lookup"><span data-stu-id="40951-107">Key/Index</span></span></th>
<th><span data-ttu-id="40951-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="40951-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40951-109"><strong>сессионидтиме</strong></span><span class="sxs-lookup"><span data-stu-id="40951-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="40951-110">datetime</span><span class="sxs-lookup"><span data-stu-id="40951-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="40951-111">Primary</span><span class="sxs-lookup"><span data-stu-id="40951-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="40951-112">Время запроса сеанса; используется в сочетании с Сессионидсек для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="40951-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40951-113"><strong>сессионидсек</strong></span><span class="sxs-lookup"><span data-stu-id="40951-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="40951-114">целое</span><span class="sxs-lookup"><span data-stu-id="40951-114">int</span></span></p></td>
<td><p><span data-ttu-id="40951-115">Primary</span><span class="sxs-lookup"><span data-stu-id="40951-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="40951-116">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="40951-116">ID number to identify the session.</span></span> <span data-ttu-id="40951-117">Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="40951-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40951-118"><strong>екстерналчекксум</strong></span><span class="sxs-lookup"><span data-stu-id="40951-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="40951-119">целое</span><span class="sxs-lookup"><span data-stu-id="40951-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40951-120">Контрольная сумма Екстерналид.</span><span class="sxs-lookup"><span data-stu-id="40951-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="40951-121">Это поле используется для увеличения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="40951-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40951-122"><strong>екстерналид</strong></span><span class="sxs-lookup"><span data-stu-id="40951-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="40951-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="40951-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40951-124">ИДЕНТИФИКАТОР диалогового окна SIP, сохраненный в виде двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="40951-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="40951-125">Двоичный формат:</span><span class="sxs-lookup"><span data-stu-id="40951-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="40951-126">диалоговое окно; тег "from-Tag"</span><span class="sxs-lookup"><span data-stu-id="40951-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="40951-127">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="40951-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

