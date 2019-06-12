---
title: 'Lync Server 2013: tblLastInviteId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be882798a620933af28c7e6697a388ef01817e5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="41aef-102">tblLastInviteId в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41aef-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41aef-103">_**Тема последнего изменения:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="41aef-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="41aef-104">Тблластинвитеид — это последний идентификатор приглашения, созданный (и использованный в таблице ТблпринЦипалинвитес) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="41aef-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="41aef-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="41aef-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41aef-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="41aef-106">Column</span></span></th>
<th><span data-ttu-id="41aef-107">Тип</span><span class="sxs-lookup"><span data-stu-id="41aef-107">Type</span></span></th>
<th><span data-ttu-id="41aef-108">Описание</span><span class="sxs-lookup"><span data-stu-id="41aef-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41aef-109">Принид</span><span class="sxs-lookup"><span data-stu-id="41aef-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="41aef-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="41aef-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="41aef-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="41aef-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41aef-112">Ластинвитеид</span><span class="sxs-lookup"><span data-stu-id="41aef-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="41aef-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="41aef-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="41aef-114">Идентификатор приглашения последнего использован.</span><span class="sxs-lookup"><span data-stu-id="41aef-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="41aef-115">Параметры</span><span class="sxs-lookup"><span data-stu-id="41aef-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41aef-116">Столбец</span><span class="sxs-lookup"><span data-stu-id="41aef-116">Column</span></span></th>
<th><span data-ttu-id="41aef-117">Описание</span><span class="sxs-lookup"><span data-stu-id="41aef-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41aef-118">Принид</span><span class="sxs-lookup"><span data-stu-id="41aef-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="41aef-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="41aef-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41aef-120">Принид</span><span class="sxs-lookup"><span data-stu-id="41aef-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="41aef-121">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="41aef-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="41aef-122">См. также</span><span class="sxs-lookup"><span data-stu-id="41aef-122">See Also</span></span>


[<span data-ttu-id="41aef-123">tblPrincipalInvites в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41aef-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

