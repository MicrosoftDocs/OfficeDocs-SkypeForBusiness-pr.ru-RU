---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929926"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="7c485-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="7c485-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="7c485-104">tblComplianceFanout содержит все серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="7c485-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="7c485-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="7c485-105">**Columns**</span></span>

|<span data-ttu-id="7c485-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c485-106">**Column**</span></span>|<span data-ttu-id="7c485-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7c485-107">**Type**</span></span>|<span data-ttu-id="7c485-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c485-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7c485-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="7c485-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="7c485-110">целое</span><span class="sxs-lookup"><span data-stu-id="7c485-110">int</span></span>  <br/> |<span data-ttu-id="7c485-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="7c485-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="7c485-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="7c485-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="7c485-113">целое</span><span class="sxs-lookup"><span data-stu-id="7c485-113">int</span></span>  <br/> |<span data-ttu-id="7c485-114">Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="7c485-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="7c485-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="7c485-115">**Key**</span></span>

|<span data-ttu-id="7c485-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c485-116">**Column**</span></span>|<span data-ttu-id="7c485-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c485-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c485-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="7c485-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="7c485-119">Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="7c485-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

