---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929849"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="64c4a-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="64c4a-103">tblComplianceState</span></span>
 
<span data-ttu-id="64c4a-104">Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="64c4a-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="64c4a-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="64c4a-105">**Columns**</span></span>

|<span data-ttu-id="64c4a-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="64c4a-106">**Column**</span></span>|<span data-ttu-id="64c4a-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="64c4a-107">**Type**</span></span>|<span data-ttu-id="64c4a-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="64c4a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64c4a-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="64c4a-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="64c4a-110">bigint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="64c4a-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="64c4a-111">Идентификатор последнего обработанного события соответствия.</span><span class="sxs-lookup"><span data-stu-id="64c4a-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="64c4a-112">значение activeServerID</span><span class="sxs-lookup"><span data-stu-id="64c4a-112">activeServerID</span></span>  <br/> |<span data-ttu-id="64c4a-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="64c4a-113">int, not null</span></span>  <br/> |<span data-ttu-id="64c4a-114">Идентификатор сервера соответствия, удерживая монопольная блокировка базы данных, или значение -1, если нет.</span><span class="sxs-lookup"><span data-stu-id="64c4a-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="64c4a-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="64c4a-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="64c4a-116">datetime2, не может быть null</span><span class="sxs-lookup"><span data-stu-id="64c4a-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="64c4a-117">Время окончания блокировки (если значение activeServerID не -1).</span><span class="sxs-lookup"><span data-stu-id="64c4a-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

