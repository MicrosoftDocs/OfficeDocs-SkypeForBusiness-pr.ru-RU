---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874059"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="401c2-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="401c2-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="401c2-104">tblComplianceFanout содержит все серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="401c2-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="401c2-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="401c2-105">**Columns**</span></span>

|<span data-ttu-id="401c2-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="401c2-106">**Column**</span></span>|<span data-ttu-id="401c2-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="401c2-107">**Type**</span></span>|<span data-ttu-id="401c2-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="401c2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="401c2-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="401c2-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="401c2-110">целое</span><span class="sxs-lookup"><span data-stu-id="401c2-110">int</span></span>  <br/> |<span data-ttu-id="401c2-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="401c2-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="401c2-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="401c2-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="401c2-113">целое</span><span class="sxs-lookup"><span data-stu-id="401c2-113">int</span></span>  <br/> |<span data-ttu-id="401c2-114">Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="401c2-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="401c2-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="401c2-115">**Key**</span></span>

|<span data-ttu-id="401c2-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="401c2-116">**Column**</span></span>|<span data-ttu-id="401c2-117">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="401c2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="401c2-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="401c2-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="401c2-119">Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="401c2-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

