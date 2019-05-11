---
title: Таблица ContentTypes в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям. Каждая запись в таблице представляет один тип контента.
ms.openlocfilehash: e30f5f142b9b1e166266cf8d45fe7657fee1b1b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901082"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9c6a5-104">Таблица ContentTypes в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9c6a5-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9c6a5-105">Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям.</span><span class="sxs-lookup"><span data-stu-id="9c6a5-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="9c6a5-106">Каждая запись в таблице представляет один тип контента.</span><span class="sxs-lookup"><span data-stu-id="9c6a5-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="9c6a5-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9c6a5-107">**Column**</span></span>|<span data-ttu-id="9c6a5-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="9c6a5-108">**Data Type**</span></span>|<span data-ttu-id="9c6a5-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="9c6a5-109">**Key/Index**</span></span>|<span data-ttu-id="9c6a5-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="9c6a5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c6a5-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="9c6a5-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="9c6a5-112">целое</span><span class="sxs-lookup"><span data-stu-id="9c6a5-112">int</span></span>  <br/> |<span data-ttu-id="9c6a5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9c6a5-113">Primary</span></span>  <br/> |<span data-ttu-id="9c6a5-114">Уникальный номер, идентифицирующий тип контента.</span><span class="sxs-lookup"><span data-stu-id="9c6a5-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="9c6a5-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="9c6a5-115">**ContentType**</span></span> <br/> |<span data-ttu-id="9c6a5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c6a5-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9c6a5-117">Имя типа контента.</span><span class="sxs-lookup"><span data-stu-id="9c6a5-117">Content type name.</span></span>  <br/> |
   

