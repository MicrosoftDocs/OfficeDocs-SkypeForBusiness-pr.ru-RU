---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212637"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="2c8b4-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="2c8b4-103">tblComplianceState</span></span>
 
<span data-ttu-id="2c8b4-104">Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="2c8b4-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="2c8b4-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="2c8b4-105">**Columns**</span></span>

|<span data-ttu-id="2c8b4-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="2c8b4-106">**Column**</span></span>|<span data-ttu-id="2c8b4-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2c8b4-107">**Type**</span></span>|<span data-ttu-id="2c8b4-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2c8b4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c8b4-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="2c8b4-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="2c8b4-110">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="2c8b4-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="2c8b4-111">Идентификатор последнего обработанного события соответствия.</span><span class="sxs-lookup"><span data-stu-id="2c8b4-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="2c8b4-112">значение activeServerID</span><span class="sxs-lookup"><span data-stu-id="2c8b4-112">activeServerID</span></span>  <br/> |<span data-ttu-id="2c8b4-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="2c8b4-113">int, not null</span></span>  <br/> |<span data-ttu-id="2c8b4-114">Идентификатор сервера соответствия, удерживая монопольная блокировка базы данных, или значение -1, если нет.</span><span class="sxs-lookup"><span data-stu-id="2c8b4-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="2c8b4-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="2c8b4-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="2c8b4-116">datetime2, не может быть null</span><span class="sxs-lookup"><span data-stu-id="2c8b4-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="2c8b4-117">Время окончания блокировки (если значение activeServerID не -1).</span><span class="sxs-lookup"><span data-stu-id="2c8b4-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

