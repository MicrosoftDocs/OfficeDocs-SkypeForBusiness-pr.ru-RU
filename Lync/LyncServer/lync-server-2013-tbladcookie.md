---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="4f6c0-102">tblADCookie в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f6c0-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f6c0-103">_**Тема последнего изменения:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="4f6c0-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="4f6c0-104">Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="4f6c0-105">Столбцов</span><span class="sxs-lookup"><span data-stu-id="4f6c0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f6c0-106">Столбец</span><span class="sxs-lookup"><span data-stu-id="4f6c0-106">Column</span></span></th>
<th><span data-ttu-id="4f6c0-107">Тип</span><span class="sxs-lookup"><span data-stu-id="4f6c0-107">Type</span></span></th>
<th><span data-ttu-id="4f6c0-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4f6c0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f6c0-109">Прингуид</span><span class="sxs-lookup"><span data-stu-id="4f6c0-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="4f6c0-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-111">Идентификатор GUID участника отслеживаемого домена.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f6c0-112">Приндчост</span><span class="sxs-lookup"><span data-stu-id="4f6c0-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="4f6c0-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-114">Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f6c0-115">Адкконтент</span><span class="sxs-lookup"><span data-stu-id="4f6c0-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-116">изображение (двоичное)</span><span class="sxs-lookup"><span data-stu-id="4f6c0-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-117">Cookie синхронизации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f6c0-118">Ластупдатед</span><span class="sxs-lookup"><span data-stu-id="4f6c0-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-119">datetime</span><span class="sxs-lookup"><span data-stu-id="4f6c0-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-120">Метка времени со временем обновления строки.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f6c0-121">Локкедунтил</span><span class="sxs-lookup"><span data-stu-id="4f6c0-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-122">datetime</span><span class="sxs-lookup"><span data-stu-id="4f6c0-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-123">Время, по истечении которого изменения строки будут заблокированы.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="4f6c0-124">Это является частью механизма программного обеспечения, который гарантирует, что только одна из служб чата выполняет синхронизацию службы каталогов Active Directory за один раз.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4f6c0-125">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f6c0-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f6c0-126">Столбцы (-ы)</span><span class="sxs-lookup"><span data-stu-id="4f6c0-126">Column(s)</span></span></th>
<th><span data-ttu-id="4f6c0-127">Описание</span><span class="sxs-lookup"><span data-stu-id="4f6c0-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f6c0-128">Прингуид</span><span class="sxs-lookup"><span data-stu-id="4f6c0-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-129">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f6c0-130">Прингуид</span><span class="sxs-lookup"><span data-stu-id="4f6c0-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="4f6c0-131">Внешний ключ с подстановкой в таблице Principal. Прингуид.</span><span class="sxs-lookup"><span data-stu-id="4f6c0-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

