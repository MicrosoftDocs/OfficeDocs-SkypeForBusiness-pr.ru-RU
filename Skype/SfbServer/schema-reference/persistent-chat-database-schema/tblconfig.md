---
title: tblConfig
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
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="2a020-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="2a020-103">tblConfig</span></span>
 
<span data-ttu-id="2a020-104">tblConfig содержит несколько серверов сохраняемого чата неподдерживаемой конфигурации в одну строку.</span><span class="sxs-lookup"><span data-stu-id="2a020-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="2a020-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="2a020-105">**Columns**</span></span>

|<span data-ttu-id="2a020-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a020-106">**Column**</span></span>|<span data-ttu-id="2a020-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2a020-107">**Type**</span></span>|<span data-ttu-id="2a020-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2a020-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2a020-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="2a020-109">configLabel</span></span>  <br/> |<span data-ttu-id="2a020-110">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="2a020-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2a020-111">Содержит «pool».</span><span class="sxs-lookup"><span data-stu-id="2a020-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="2a020-112">configContent</span><span class="sxs-lookup"><span data-stu-id="2a020-112">configContent</span></span>  <br/> |<span data-ttu-id="2a020-113">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="2a020-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="2a020-114">Содержимое конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2a020-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="2a020-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="2a020-115">configPoolID</span></span>  <br/> |<span data-ttu-id="2a020-116">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="2a020-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="2a020-117">Уникальный идентификатор экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="2a020-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="2a020-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="2a020-118">**Key**</span></span>

|<span data-ttu-id="2a020-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2a020-119">**Column**</span></span>|<span data-ttu-id="2a020-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2a020-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2a020-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="2a020-121">configLabel</span></span>  <br/> |<span data-ttu-id="2a020-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2a020-122">Primary key.</span></span>  <br/> |
   

