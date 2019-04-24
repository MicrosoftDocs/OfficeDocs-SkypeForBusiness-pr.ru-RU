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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213251"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8e8a7-104">Таблица ContentTypes в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8e8a7-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8e8a7-105">Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям.</span><span class="sxs-lookup"><span data-stu-id="8e8a7-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="8e8a7-106">Каждая запись в таблице представляет один тип контента.</span><span class="sxs-lookup"><span data-stu-id="8e8a7-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="8e8a7-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8e8a7-107">**Column**</span></span>|<span data-ttu-id="8e8a7-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8e8a7-108">**Data Type**</span></span>|<span data-ttu-id="8e8a7-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8e8a7-109">**Key/Index**</span></span>|<span data-ttu-id="8e8a7-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8e8a7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e8a7-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="8e8a7-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="8e8a7-112">целое</span><span class="sxs-lookup"><span data-stu-id="8e8a7-112">int</span></span>  <br/> |<span data-ttu-id="8e8a7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8e8a7-113">Primary</span></span>  <br/> |<span data-ttu-id="8e8a7-114">Уникальный номер, идентифицирующий тип контента.</span><span class="sxs-lookup"><span data-stu-id="8e8a7-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="8e8a7-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="8e8a7-115">**ContentType**</span></span> <br/> |<span data-ttu-id="8e8a7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e8a7-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="8e8a7-117">Имя типа контента.</span><span class="sxs-lookup"><span data-stu-id="8e8a7-117">Content type name.</span></span>  <br/> |
   

