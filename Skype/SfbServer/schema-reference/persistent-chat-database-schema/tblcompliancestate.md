---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295477"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="54c16-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="54c16-103">tblComplianceState</span></span>
 
<span data-ttu-id="54c16-104">Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.</span><span class="sxs-lookup"><span data-stu-id="54c16-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="54c16-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="54c16-105">**Columns**</span></span>

|<span data-ttu-id="54c16-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="54c16-106">**Column**</span></span>|<span data-ttu-id="54c16-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="54c16-107">**Type**</span></span>|<span data-ttu-id="54c16-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="54c16-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54c16-109">Ластпроцесседентрид</span><span class="sxs-lookup"><span data-stu-id="54c16-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="54c16-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="54c16-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="54c16-111">Идентификатор последнего обработанного события соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="54c16-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="54c16-112">Активесерверид</span><span class="sxs-lookup"><span data-stu-id="54c16-112">activeServerID</span></span>  <br/> |<span data-ttu-id="54c16-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="54c16-113">int, not null</span></span>  <br/> |<span data-ttu-id="54c16-114">Идентификатор сервера соответствия, который удерживает монопольную блокировку для базы данных, или значение-1, если нет.</span><span class="sxs-lookup"><span data-stu-id="54c16-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="54c16-115">Локкекспиратионтиме</span><span class="sxs-lookup"><span data-stu-id="54c16-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="54c16-116">datetime2, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="54c16-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="54c16-117">Заблокируйте срок действия (если Активесерверид не является 1).</span><span class="sxs-lookup"><span data-stu-id="54c16-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

