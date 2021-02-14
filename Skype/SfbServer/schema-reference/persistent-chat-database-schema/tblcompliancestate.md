---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809729"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="0d00c-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="0d00c-103">tblComplianceState</span></span>
 
<span data-ttu-id="0d00c-104">Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.</span><span class="sxs-lookup"><span data-stu-id="0d00c-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="0d00c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="0d00c-105">**Columns**</span></span>

|<span data-ttu-id="0d00c-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0d00c-106">**Column**</span></span>|<span data-ttu-id="0d00c-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0d00c-107">**Type**</span></span>|<span data-ttu-id="0d00c-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0d00c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0d00c-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="0d00c-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="0d00c-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0d00c-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="0d00c-111">Идентификатор последнего обработанного события соответствия.</span><span class="sxs-lookup"><span data-stu-id="0d00c-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="0d00c-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="0d00c-112">activeServerID</span></span>  <br/> |<span data-ttu-id="0d00c-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0d00c-113">int, not null</span></span>  <br/> |<span data-ttu-id="0d00c-114">Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.</span><span class="sxs-lookup"><span data-stu-id="0d00c-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="0d00c-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="0d00c-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="0d00c-116">datetime2, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0d00c-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="0d00c-117">Время окончания блокировки (если значение activeServerID не равно -1).</span><span class="sxs-lookup"><span data-stu-id="0d00c-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

