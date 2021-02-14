---
title: Таблица EdgeServers в Skype для бизнеса Server 2015
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
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица EdgeServers является вспомогательной. В каждой записи хранится информация об одном сервере, который участвует в вызовах с записями в базе данных.
ms.openlocfilehash: 98f37ecbf976fb08ae27e080f5e9e498558131fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813209"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a5136-104">Таблица EdgeServers в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="a5136-104">EdgeServers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a5136-105">Таблица EdgeServers является вспомогательной.</span><span class="sxs-lookup"><span data-stu-id="a5136-105">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="a5136-106">В каждой записи хранится информация об одном сервере, который участвует в вызовах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a5136-106">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="a5136-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a5136-107">**Column**</span></span>|<span data-ttu-id="a5136-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a5136-108">**Data Type**</span></span>|<span data-ttu-id="a5136-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a5136-109">**Key/Index**</span></span>|<span data-ttu-id="a5136-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="a5136-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5136-111">**EdgeServerId**</span><span class="sxs-lookup"><span data-stu-id="a5136-111">**EdgeServerId**</span></span> <br/> |<span data-ttu-id="a5136-112">int</span><span class="sxs-lookup"><span data-stu-id="a5136-112">int</span></span>  <br/> |<span data-ttu-id="a5136-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a5136-113">Primary</span></span>  <br/> |<span data-ttu-id="a5136-114">Уникальный номер, идентифицирующий этот сервер.</span><span class="sxs-lookup"><span data-stu-id="a5136-114">Unique number identifying this Edge Server.</span></span>  <br/> |
|<span data-ttu-id="a5136-115">**EdgeServer**</span><span class="sxs-lookup"><span data-stu-id="a5136-115">**EdgeServer**</span></span> <br/> |<span data-ttu-id="a5136-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a5136-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="a5136-117">Имя сервера.</span><span class="sxs-lookup"><span data-stu-id="a5136-117">Edge Server name.</span></span>  <br/> |
   

