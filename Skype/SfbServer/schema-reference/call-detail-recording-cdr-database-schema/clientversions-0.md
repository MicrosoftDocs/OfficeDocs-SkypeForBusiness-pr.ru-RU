---
title: Представление Клиентверсионс
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в представлении представляет собой одну версию клиента. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815417"
---
# <a name="clientversions-view"></a><span data-ttu-id="ac3ce-105">Представление Клиентверсионс</span><span class="sxs-lookup"><span data-stu-id="ac3ce-105">ClientVersions view</span></span>
 
<span data-ttu-id="ac3ce-106">В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ac3ce-107">Каждая запись в представлении представляет собой одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="ac3ce-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac3ce-109">Для некоторых столбцов может быть несколько записей.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="ac3ce-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-110">**Column**</span></span>|<span data-ttu-id="ac3ce-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-111">**Data Type**</span></span>|<span data-ttu-id="ac3ce-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac3ce-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-113">**VersionId**</span></span> <br/> |<span data-ttu-id="ac3ce-114">целое</span><span class="sxs-lookup"><span data-stu-id="ac3ce-114">int</span></span>  <br/> |<span data-ttu-id="ac3ce-115">Уникальный номер, показывающий этот тип клиента и версию.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="ac3ce-116">**Версия**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-116">**Version**</span></span> <br/> |<span data-ttu-id="ac3ce-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ac3ce-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ac3ce-118">Представляет агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="ac3ce-119">**клиенттипе**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-119">**ClientType**</span></span> <br/> |<span data-ttu-id="ac3ce-120">целое</span><span class="sxs-lookup"><span data-stu-id="ac3ce-120">int</span></span>  <br/> |<span data-ttu-id="ac3ce-121">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="ac3ce-122">**клиенткатегори**</span><span class="sxs-lookup"><span data-stu-id="ac3ce-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="ac3ce-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ac3ce-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="ac3ce-124">Категория, к которой относится клиент.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-124">Category that the client belongs to.</span></span> <span data-ttu-id="ac3ce-125">Например, клиент Conferencing_Attendant_1 .0 принадлежит Клиенткатегори Каа.</span><span class="sxs-lookup"><span data-stu-id="ac3ce-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

