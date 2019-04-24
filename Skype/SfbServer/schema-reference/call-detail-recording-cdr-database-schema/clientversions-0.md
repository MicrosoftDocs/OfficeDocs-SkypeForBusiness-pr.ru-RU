---
title: Представление ClientVersions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Представление ClientVersions сохранение информации о различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в представлении представляет одной версии клиента. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213398"
---
# <a name="clientversions-view"></a><span data-ttu-id="c1240-105">Представление ClientVersions</span><span class="sxs-lookup"><span data-stu-id="c1240-105">ClientVersions view</span></span>
 
<span data-ttu-id="c1240-106">Представление ClientVersions сохранение информации о различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c1240-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c1240-107">Каждая запись в представлении представляет одной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="c1240-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="c1240-108">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1240-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1240-109">Возможно наличие нескольких записей для определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="c1240-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="c1240-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c1240-110">**Column**</span></span>|<span data-ttu-id="c1240-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="c1240-111">**Data Type**</span></span>|<span data-ttu-id="c1240-112">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="c1240-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1240-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="c1240-113">**VersionId**</span></span> <br/> |<span data-ttu-id="c1240-114">целое</span><span class="sxs-lookup"><span data-stu-id="c1240-114">int</span></span>  <br/> |<span data-ttu-id="c1240-115">Уникальный номер, идентифицирующий этот тип и версию клиента.</span><span class="sxs-lookup"><span data-stu-id="c1240-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="c1240-116">**Версия**</span><span class="sxs-lookup"><span data-stu-id="c1240-116">**Version**</span></span> <br/> |<span data-ttu-id="c1240-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1240-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c1240-118">Представляет агент пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1240-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="c1240-119">**Типа клиента**</span><span class="sxs-lookup"><span data-stu-id="c1240-119">**ClientType**</span></span> <br/> |<span data-ttu-id="c1240-120">целое</span><span class="sxs-lookup"><span data-stu-id="c1240-120">int</span></span>  <br/> |<span data-ttu-id="c1240-121">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="c1240-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="c1240-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="c1240-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="c1240-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="c1240-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c1240-124">Категория, к которой принадлежит клиент.</span><span class="sxs-lookup"><span data-stu-id="c1240-124">Category that the client belongs to.</span></span> <span data-ttu-id="c1240-125">Например клиент Conferencing_Attendant_1.0 принадлежит ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="c1240-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

