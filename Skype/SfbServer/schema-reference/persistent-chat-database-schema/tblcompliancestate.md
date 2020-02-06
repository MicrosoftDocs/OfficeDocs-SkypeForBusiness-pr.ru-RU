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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814637"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="62f41-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="62f41-103">tblComplianceState</span></span>
 
<span data-ttu-id="62f41-104">Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.</span><span class="sxs-lookup"><span data-stu-id="62f41-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="62f41-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="62f41-105">**Columns**</span></span>

|<span data-ttu-id="62f41-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="62f41-106">**Column**</span></span>|<span data-ttu-id="62f41-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62f41-107">**Type**</span></span>|<span data-ttu-id="62f41-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="62f41-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="62f41-109">ластпроцесседентрид</span><span class="sxs-lookup"><span data-stu-id="62f41-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="62f41-110">bigint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="62f41-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="62f41-111">Идентификатор последнего обработанного события соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="62f41-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="62f41-112">активесерверид</span><span class="sxs-lookup"><span data-stu-id="62f41-112">activeServerID</span></span>  <br/> |<span data-ttu-id="62f41-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="62f41-113">int, not null</span></span>  <br/> |<span data-ttu-id="62f41-114">Идентификатор сервера соответствия, который удерживает монопольную блокировку для базы данных, или значение-1, если нет.</span><span class="sxs-lookup"><span data-stu-id="62f41-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="62f41-115">локкекспиратионтиме</span><span class="sxs-lookup"><span data-stu-id="62f41-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="62f41-116">datetime2, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="62f41-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="62f41-117">Заблокируйте срок действия (если Активесерверид не является 1).</span><span class="sxs-lookup"><span data-stu-id="62f41-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

