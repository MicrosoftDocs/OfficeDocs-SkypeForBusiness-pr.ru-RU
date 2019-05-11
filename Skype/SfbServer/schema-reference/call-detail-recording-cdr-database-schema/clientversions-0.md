---
title: Представление ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Представление ClientVersions сохранение информации о различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в представлении представляет одной версии клиента. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901524"
---
# <a name="clientversions-view"></a><span data-ttu-id="9bc58-105">Представление ClientVersions</span><span class="sxs-lookup"><span data-stu-id="9bc58-105">ClientVersions view</span></span>
 
<span data-ttu-id="9bc58-106">Представление ClientVersions сохранение информации о различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="9bc58-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9bc58-107">Каждая запись в представлении представляет одной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="9bc58-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="9bc58-108">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bc58-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9bc58-109">Возможно наличие нескольких записей для определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9bc58-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="9bc58-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9bc58-110">**Column**</span></span>|<span data-ttu-id="9bc58-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9bc58-111">**Data Type**</span></span>|<span data-ttu-id="9bc58-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9bc58-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9bc58-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="9bc58-113">**VersionId**</span></span> <br/> |<span data-ttu-id="9bc58-114">целое</span><span class="sxs-lookup"><span data-stu-id="9bc58-114">int</span></span>  <br/> |<span data-ttu-id="9bc58-115">Уникальный номер, идентифицирующий этот тип и версию клиента.</span><span class="sxs-lookup"><span data-stu-id="9bc58-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="9bc58-116">**Версия**</span><span class="sxs-lookup"><span data-stu-id="9bc58-116">**Version**</span></span> <br/> |<span data-ttu-id="9bc58-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9bc58-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9bc58-118">Представляет агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="9bc58-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="9bc58-119">**Типа клиента**</span><span class="sxs-lookup"><span data-stu-id="9bc58-119">**ClientType**</span></span> <br/> |<span data-ttu-id="9bc58-120">целое</span><span class="sxs-lookup"><span data-stu-id="9bc58-120">int</span></span>  <br/> |<span data-ttu-id="9bc58-121">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="9bc58-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="9bc58-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="9bc58-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="9bc58-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="9bc58-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="9bc58-124">Категория, к которой принадлежит клиент.</span><span class="sxs-lookup"><span data-stu-id="9bc58-124">Category that the client belongs to.</span></span> <span data-ttu-id="9bc58-125">Например клиент Conferencing_Attendant_1.0 принадлежит ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="9bc58-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

