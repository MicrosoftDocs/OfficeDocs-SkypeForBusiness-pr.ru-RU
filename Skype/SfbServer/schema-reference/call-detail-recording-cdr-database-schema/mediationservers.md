---
title: Таблица MediationServers
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
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: Таблица MediationServers является вспомогательной. В каждой записи хранится информация об одном сервере-посреднике, который участвует в вызовах с записями в базе данных.
ms.openlocfilehash: e498409087ee5cf41b32b29ec5f66a147290e1ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814769"
---
# <a name="mediationservers-table"></a><span data-ttu-id="1de14-104">Таблица MediationServers</span><span class="sxs-lookup"><span data-stu-id="1de14-104">MediationServers table</span></span>
 
<span data-ttu-id="1de14-105">Таблица MediationServers является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="1de14-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="1de14-106">В каждой записи хранится информация об одном сервере-посреднике, который участвует в вызовах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1de14-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="1de14-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="1de14-107">**Column**</span></span>|<span data-ttu-id="1de14-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="1de14-108">**Data Type**</span></span>|<span data-ttu-id="1de14-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="1de14-109">**Key/Index**</span></span>|<span data-ttu-id="1de14-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="1de14-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1de14-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="1de14-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="1de14-112">int</span><span class="sxs-lookup"><span data-stu-id="1de14-112">int</span></span>  <br/> |<span data-ttu-id="1de14-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1de14-113">Primary</span></span>  <br/> |<span data-ttu-id="1de14-114">Уникальный номер, идентифицирующий этот сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="1de14-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="1de14-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="1de14-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="1de14-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1de14-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="1de14-117">Имя сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="1de14-117">Mediation Server name.</span></span>  <br/> |
   

