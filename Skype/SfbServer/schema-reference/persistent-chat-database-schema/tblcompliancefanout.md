---
title: tblComplianceFanout
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
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="73f67-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="73f67-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="73f67-104">tblComplianceFanout содержит все серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="73f67-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="73f67-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="73f67-105">**Columns**</span></span>

|<span data-ttu-id="73f67-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="73f67-106">**Column**</span></span>|<span data-ttu-id="73f67-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="73f67-107">**Type**</span></span>|<span data-ttu-id="73f67-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="73f67-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73f67-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="73f67-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="73f67-110">целое</span><span class="sxs-lookup"><span data-stu-id="73f67-110">int</span></span>  <br/> |<span data-ttu-id="73f67-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="73f67-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="73f67-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="73f67-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="73f67-113">целое</span><span class="sxs-lookup"><span data-stu-id="73f67-113">int</span></span>  <br/> |<span data-ttu-id="73f67-114">Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="73f67-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="73f67-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="73f67-115">**Key**</span></span>

|<span data-ttu-id="73f67-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="73f67-116">**Column**</span></span>|<span data-ttu-id="73f67-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="73f67-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73f67-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="73f67-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="73f67-119">Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="73f67-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

