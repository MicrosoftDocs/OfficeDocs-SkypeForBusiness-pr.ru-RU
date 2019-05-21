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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: Тблкомплианцефанаут включает все серверы, которые обрабатывали событие соответствия требованиям.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295505"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="dbed1-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="dbed1-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="dbed1-104">Тблкомплианцефанаут включает все серверы, которые обрабатывали событие соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="dbed1-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="dbed1-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="dbed1-105">**Columns**</span></span>

|<span data-ttu-id="dbed1-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="dbed1-106">**Column**</span></span>|<span data-ttu-id="dbed1-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="dbed1-107">**Type**</span></span>|<span data-ttu-id="dbed1-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dbed1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dbed1-109">Фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="dbed1-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="dbed1-110">целое</span><span class="sxs-lookup"><span data-stu-id="dbed1-110">int</span></span>  <br/> |<span data-ttu-id="dbed1-111">Код события.</span><span class="sxs-lookup"><span data-stu-id="dbed1-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="dbed1-112">Фанаутсерверид</span><span class="sxs-lookup"><span data-stu-id="dbed1-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="dbed1-113">целое</span><span class="sxs-lookup"><span data-stu-id="dbed1-113">int</span></span>  <br/> |<span data-ttu-id="dbed1-114">Идентификация сервера (соответствующая таблице Тблсерверидентити. Серверид).</span><span class="sxs-lookup"><span data-stu-id="dbed1-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="dbed1-115">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="dbed1-115">**Key**</span></span>

|<span data-ttu-id="dbed1-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="dbed1-116">**Column**</span></span>|<span data-ttu-id="dbed1-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="dbed1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dbed1-118">Фанаутевентид</span><span class="sxs-lookup"><span data-stu-id="dbed1-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="dbed1-119">Внешний ключ с подстановкой в таблице Тблкомплианцедата. Кмплевентид.</span><span class="sxs-lookup"><span data-stu-id="dbed1-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

