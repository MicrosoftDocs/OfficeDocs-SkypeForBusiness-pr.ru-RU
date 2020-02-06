---
title: Таблица "ContentType" в Skype для бизнеса Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes является вспомогательной таблицей, в которой хранится список типов контента, используемых в одноранговых сеансах и сеансах конференц-связи. Каждая запись в таблице представляет один тип контента.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815307"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="101ab-104">Таблица "ContentType" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="101ab-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="101ab-105">Таблица ContentTypes является вспомогательной таблицей, в которой хранится список типов контента, используемых в одноранговых сеансах и сеансах конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="101ab-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="101ab-106">Каждая запись в таблице представляет один тип контента.</span><span class="sxs-lookup"><span data-stu-id="101ab-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="101ab-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="101ab-107">**Column**</span></span>|<span data-ttu-id="101ab-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="101ab-108">**Data Type**</span></span>|<span data-ttu-id="101ab-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="101ab-109">**Key/Index**</span></span>|<span data-ttu-id="101ab-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="101ab-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="101ab-111">**контенттипеид**</span><span class="sxs-lookup"><span data-stu-id="101ab-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="101ab-112">целое</span><span class="sxs-lookup"><span data-stu-id="101ab-112">int</span></span>  <br/> |<span data-ttu-id="101ab-113">Primary</span><span class="sxs-lookup"><span data-stu-id="101ab-113">Primary</span></span>  <br/> |<span data-ttu-id="101ab-114">Уникальный номер, определяющий тип контента.</span><span class="sxs-lookup"><span data-stu-id="101ab-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="101ab-115">**Контента**</span><span class="sxs-lookup"><span data-stu-id="101ab-115">**ContentType**</span></span> <br/> |<span data-ttu-id="101ab-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="101ab-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="101ab-117">Имя типа контента.</span><span class="sxs-lookup"><span data-stu-id="101ab-117">Content type name.</span></span>  <br/> |
   

