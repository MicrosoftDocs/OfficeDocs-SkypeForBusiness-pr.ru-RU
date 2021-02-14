---
title: Таблица ContentTypes в Skype для бизнеса Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816089"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0db30-104">Таблица ContentTypes в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0db30-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0db30-p102">Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="0db30-p102">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions. Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="0db30-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0db30-107">**Column**</span></span>|<span data-ttu-id="0db30-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="0db30-108">**Data Type**</span></span>|<span data-ttu-id="0db30-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="0db30-109">**Key/Index**</span></span>|<span data-ttu-id="0db30-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="0db30-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0db30-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="0db30-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="0db30-112">int</span><span class="sxs-lookup"><span data-stu-id="0db30-112">int</span></span>  <br/> |<span data-ttu-id="0db30-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0db30-113">Primary</span></span>  <br/> |<span data-ttu-id="0db30-114">Уникальный номер, идентифицирующий этот тип содержимого.</span><span class="sxs-lookup"><span data-stu-id="0db30-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="0db30-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="0db30-115">**ContentType**</span></span> <br/> |<span data-ttu-id="0db30-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0db30-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="0db30-117">Имя типа содержимого.</span><span class="sxs-lookup"><span data-stu-id="0db30-117">Content type name.</span></span>  <br/> |
   

