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
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в представлении представляет собой одну версию клиента. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296541"
---
# <a name="clientversions-view"></a><span data-ttu-id="00082-105">Представление Клиентверсионс</span><span class="sxs-lookup"><span data-stu-id="00082-105">ClientVersions view</span></span>
 
<span data-ttu-id="00082-106">В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="00082-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="00082-107">Каждая запись в представлении представляет собой одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="00082-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="00082-108">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00082-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00082-109">Для некоторых столбцов может быть несколько записей.</span><span class="sxs-lookup"><span data-stu-id="00082-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="00082-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="00082-110">**Column**</span></span>|<span data-ttu-id="00082-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="00082-111">**Data Type**</span></span>|<span data-ttu-id="00082-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="00082-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00082-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="00082-113">**VersionId**</span></span> <br/> |<span data-ttu-id="00082-114">целое</span><span class="sxs-lookup"><span data-stu-id="00082-114">int</span></span>  <br/> |<span data-ttu-id="00082-115">Уникальный номер, показывающий этот тип клиента и версию.</span><span class="sxs-lookup"><span data-stu-id="00082-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="00082-116">**Версия**</span><span class="sxs-lookup"><span data-stu-id="00082-116">**Version**</span></span> <br/> |<span data-ttu-id="00082-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="00082-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="00082-118">Представляет агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="00082-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="00082-119">**Клиенттипе**</span><span class="sxs-lookup"><span data-stu-id="00082-119">**ClientType**</span></span> <br/> |<span data-ttu-id="00082-120">целое</span><span class="sxs-lookup"><span data-stu-id="00082-120">int</span></span>  <br/> |<span data-ttu-id="00082-121">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="00082-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="00082-122">**Клиенткатегори**</span><span class="sxs-lookup"><span data-stu-id="00082-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="00082-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="00082-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="00082-124">Категория, к которой относится клиент.</span><span class="sxs-lookup"><span data-stu-id="00082-124">Category that the client belongs to.</span></span> <span data-ttu-id="00082-125">Например, клиент КонференЦинг_аттендант_ 1.0 принадлежит к Клиенткатегори Каа.</span><span class="sxs-lookup"><span data-stu-id="00082-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

