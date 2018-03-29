---
title: Таблица ContentTypes в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям. Каждая запись в таблице представляет один тип контента.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="82320-104">Таблица ContentTypes в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="82320-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82320-105">Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям.</span><span class="sxs-lookup"><span data-stu-id="82320-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="82320-106">Каждая запись в таблице представляет один тип контента.</span><span class="sxs-lookup"><span data-stu-id="82320-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="82320-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="82320-107">**Column**</span></span>|<span data-ttu-id="82320-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="82320-108">**Data Type**</span></span>|<span data-ttu-id="82320-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="82320-109">**Key/Index**</span></span>|<span data-ttu-id="82320-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="82320-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82320-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="82320-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="82320-112">целое</span><span class="sxs-lookup"><span data-stu-id="82320-112">int</span></span>  <br/> |<span data-ttu-id="82320-113">Primary</span><span class="sxs-lookup"><span data-stu-id="82320-113">Primary</span></span>  <br/> |<span data-ttu-id="82320-114">Уникальный номер, идентифицирующий тип контента.</span><span class="sxs-lookup"><span data-stu-id="82320-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="82320-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="82320-115">**ContentType**</span></span> <br/> |<span data-ttu-id="82320-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="82320-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="82320-117">Имя типа контента.</span><span class="sxs-lookup"><span data-stu-id="82320-117">Content type name.</span></span>  <br/> |
   

