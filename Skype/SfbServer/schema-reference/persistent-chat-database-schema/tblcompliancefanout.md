---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809799"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="03bab-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="03bab-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="03bab-104">tblComplianceFanout содержит все серверы, обработавшие событие соответствия.</span><span class="sxs-lookup"><span data-stu-id="03bab-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="03bab-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="03bab-105">**Columns**</span></span>

|<span data-ttu-id="03bab-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="03bab-106">**Column**</span></span>|<span data-ttu-id="03bab-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="03bab-107">**Type**</span></span>|<span data-ttu-id="03bab-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="03bab-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03bab-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="03bab-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="03bab-110">int</span><span class="sxs-lookup"><span data-stu-id="03bab-110">int</span></span>  <br/> |<span data-ttu-id="03bab-111">Идентификатор события.</span><span class="sxs-lookup"><span data-stu-id="03bab-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="03bab-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="03bab-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="03bab-113">int</span><span class="sxs-lookup"><span data-stu-id="03bab-113">int</span></span>  <br/> |<span data-ttu-id="03bab-114">Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="03bab-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="03bab-115">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="03bab-115">**Key**</span></span>

|<span data-ttu-id="03bab-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="03bab-116">**Column**</span></span>|<span data-ttu-id="03bab-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="03bab-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="03bab-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="03bab-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="03bab-119">Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="03bab-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

