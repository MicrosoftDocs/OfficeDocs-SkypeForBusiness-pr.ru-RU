---
title: Таблица ContentTypes в Скайп для Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894989"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bca89-104">Таблица ContentTypes в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bca89-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bca89-105">Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям.</span><span class="sxs-lookup"><span data-stu-id="bca89-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="bca89-106">Каждая запись в таблице представляет один тип контента.</span><span class="sxs-lookup"><span data-stu-id="bca89-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="bca89-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bca89-107">**Column**</span></span>|<span data-ttu-id="bca89-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bca89-108">**Data Type**</span></span>|<span data-ttu-id="bca89-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bca89-109">**Key/Index**</span></span>|<span data-ttu-id="bca89-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="bca89-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bca89-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="bca89-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="bca89-112">целое</span><span class="sxs-lookup"><span data-stu-id="bca89-112">int</span></span>  <br/> |<span data-ttu-id="bca89-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bca89-113">Primary</span></span>  <br/> |<span data-ttu-id="bca89-114">Уникальный номер, идентифицирующий тип контента.</span><span class="sxs-lookup"><span data-stu-id="bca89-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="bca89-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="bca89-115">**ContentType**</span></span> <br/> |<span data-ttu-id="bca89-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bca89-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="bca89-117">Имя типа контента.</span><span class="sxs-lookup"><span data-stu-id="bca89-117">Content type name.</span></span>  <br/> |
   

