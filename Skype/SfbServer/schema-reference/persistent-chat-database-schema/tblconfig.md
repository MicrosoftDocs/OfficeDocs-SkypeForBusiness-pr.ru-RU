---
title: tblConfig
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig содержит неподдерживаемую конфигурацию сервера сохраняемой беседы в одной строке.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809739"
---
# <a name="tblconfig"></a><span data-ttu-id="e9ccc-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="e9ccc-103">tblConfig</span></span>
 
<span data-ttu-id="e9ccc-104">tblConfig содержит неподдерживаемую конфигурацию сервера сохраняемой беседы в одной строке.</span><span class="sxs-lookup"><span data-stu-id="e9ccc-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="e9ccc-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-105">**Columns**</span></span>

|<span data-ttu-id="e9ccc-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-106">**Column**</span></span>|<span data-ttu-id="e9ccc-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-107">**Type**</span></span>|<span data-ttu-id="e9ccc-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9ccc-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="e9ccc-109">configLabel</span></span>  <br/> |<span data-ttu-id="e9ccc-110">nvarchar (255), не равно null</span><span class="sxs-lookup"><span data-stu-id="e9ccc-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="e9ccc-111">Содержит "pool."</span><span class="sxs-lookup"><span data-stu-id="e9ccc-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="e9ccc-112">configContent</span><span class="sxs-lookup"><span data-stu-id="e9ccc-112">configContent</span></span>  <br/> |<span data-ttu-id="e9ccc-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="e9ccc-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="e9ccc-114">Содержимое конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e9ccc-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="e9ccc-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="e9ccc-115">configPoolID</span></span>  <br/> |<span data-ttu-id="e9ccc-116">GUID, не равно null</span><span class="sxs-lookup"><span data-stu-id="e9ccc-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="e9ccc-117">Уникальный идентификатор экземпляра базы данных.</span><span class="sxs-lookup"><span data-stu-id="e9ccc-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="e9ccc-118">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-118">**Key**</span></span>

|<span data-ttu-id="e9ccc-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-119">**Column**</span></span>|<span data-ttu-id="e9ccc-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e9ccc-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9ccc-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="e9ccc-121">configLabel</span></span>  <br/> |<span data-ttu-id="e9ccc-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="e9ccc-122">Primary key.</span></span>  <br/> |
   

