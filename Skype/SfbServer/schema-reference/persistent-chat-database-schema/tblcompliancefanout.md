---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: Тблкомплианцефанаут включает все серверы, которые обрабатывали событие соответствия требованиям.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814657"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="c1d16-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="c1d16-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="c1d16-104">Тблкомплианцефанаут включает все серверы, которые обрабатывали событие соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c1d16-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="c1d16-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="c1d16-105">**Columns**</span></span>

|<span data-ttu-id="c1d16-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c1d16-106">**Column**</span></span>|<span data-ttu-id="c1d16-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="c1d16-107">**Type**</span></span>|<span data-ttu-id="c1d16-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c1d16-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1d16-109">фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="c1d16-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="c1d16-110">целое</span><span class="sxs-lookup"><span data-stu-id="c1d16-110">int</span></span>  <br/> |<span data-ttu-id="c1d16-111">Код события.</span><span class="sxs-lookup"><span data-stu-id="c1d16-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="c1d16-112">фанаутсерверид</span><span class="sxs-lookup"><span data-stu-id="c1d16-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="c1d16-113">целое</span><span class="sxs-lookup"><span data-stu-id="c1d16-113">int</span></span>  <br/> |<span data-ttu-id="c1d16-114">Идентификация сервера (соответствующая таблице Тблсерверидентити. Серверид).</span><span class="sxs-lookup"><span data-stu-id="c1d16-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="c1d16-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="c1d16-115">**Key**</span></span>

|<span data-ttu-id="c1d16-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="c1d16-116">**Column**</span></span>|<span data-ttu-id="c1d16-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c1d16-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1d16-118">фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="c1d16-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="c1d16-119">Внешний ключ с подстановкой в таблице Тблкомплианцедата. Кмплевентид.</span><span class="sxs-lookup"><span data-stu-id="c1d16-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

