---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig содержит несколько серверов сохраняемого чата неподдерживаемой конфигурации в одну строку.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898939"
---
# <a name="tblconfig"></a><span data-ttu-id="d3d31-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="d3d31-103">tblConfig</span></span>
 
<span data-ttu-id="d3d31-104">tblConfig содержит несколько серверов сохраняемого чата неподдерживаемой конфигурации в одну строку.</span><span class="sxs-lookup"><span data-stu-id="d3d31-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="d3d31-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="d3d31-105">**Columns**</span></span>

|<span data-ttu-id="d3d31-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d3d31-106">**Column**</span></span>|<span data-ttu-id="d3d31-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d3d31-107">**Type**</span></span>|<span data-ttu-id="d3d31-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="d3d31-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3d31-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="d3d31-109">configLabel</span></span>  <br/> |<span data-ttu-id="d3d31-110">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="d3d31-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d3d31-111">Содержит «pool».</span><span class="sxs-lookup"><span data-stu-id="d3d31-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="d3d31-112">configContent</span><span class="sxs-lookup"><span data-stu-id="d3d31-112">configContent</span></span>  <br/> |<span data-ttu-id="d3d31-113">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="d3d31-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="d3d31-114">Содержимое конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d3d31-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="d3d31-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="d3d31-115">configPoolID</span></span>  <br/> |<span data-ttu-id="d3d31-116">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="d3d31-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="d3d31-117">Уникальный идентификатор экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3d31-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="d3d31-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="d3d31-118">**Key**</span></span>

|<span data-ttu-id="d3d31-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d3d31-119">**Column**</span></span>|<span data-ttu-id="d3d31-120">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="d3d31-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3d31-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="d3d31-121">configLabel</span></span>  <br/> |<span data-ttu-id="d3d31-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="d3d31-122">Primary key.</span></span>  <br/> |
   

