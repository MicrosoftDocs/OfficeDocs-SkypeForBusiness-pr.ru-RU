---
title: 'Lync Server 2013: таблица CallType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f99ae304ea9f45658903637221f234405107d4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="calltype-table-in-lync-server-2013"></a><span data-ttu-id="99f1c-102">Таблица CallType в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99f1c-102">CallType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99f1c-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="99f1c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="99f1c-104">Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.</span><span class="sxs-lookup"><span data-stu-id="99f1c-104">The CallType table is a static table that stores the list of possible call types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99f1c-105">Столбец</span><span class="sxs-lookup"><span data-stu-id="99f1c-105">Column</span></span></th>
<th><span data-ttu-id="99f1c-106">Тип данных</span><span class="sxs-lookup"><span data-stu-id="99f1c-106">Data Type</span></span></th>
<th><span data-ttu-id="99f1c-107">Ключ или индекс</span><span class="sxs-lookup"><span data-stu-id="99f1c-107">Key/Index</span></span></th>
<th><span data-ttu-id="99f1c-108">Сведения</span><span class="sxs-lookup"><span data-stu-id="99f1c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99f1c-109"><strong>каллтипеид</strong></span><span class="sxs-lookup"><span data-stu-id="99f1c-109"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="99f1c-110">int</span><span class="sxs-lookup"><span data-stu-id="99f1c-110">int</span></span></p></td>
<td><p><span data-ttu-id="99f1c-111">Primary</span><span class="sxs-lookup"><span data-stu-id="99f1c-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99f1c-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="99f1c-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="99f1c-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="99f1c-113">nvarchar</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="99f1c-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="99f1c-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="99f1c-115">0 — неизвестный</span><span class="sxs-lookup"><span data-stu-id="99f1c-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="99f1c-116">1 — обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="99f1c-116">1 – Instant Messaging</span></span></p></li>
<li><p><span data-ttu-id="99f1c-117">2 — общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="99f1c-117">2 -- Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="99f1c-118">3 — аудио</span><span class="sxs-lookup"><span data-stu-id="99f1c-118">3 -- Audio</span></span></p></li>
<li><p><span data-ttu-id="99f1c-119">4 — аудио и видео</span><span class="sxs-lookup"><span data-stu-id="99f1c-119">4 – Audio and Video</span></span></p></li>
<li><p><span data-ttu-id="99f1c-120">5 — передача файла</span><span class="sxs-lookup"><span data-stu-id="99f1c-120">5 – File Transfer</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

