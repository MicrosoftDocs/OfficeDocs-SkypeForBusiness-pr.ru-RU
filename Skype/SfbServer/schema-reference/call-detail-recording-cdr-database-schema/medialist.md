---
title: Таблица MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813139"
---
# <a name="medialist-table"></a><span data-ttu-id="17150-103">Таблица MediaList</span><span class="sxs-lookup"><span data-stu-id="17150-103">MediaList table</span></span>
 
<span data-ttu-id="17150-104">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="17150-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="17150-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="17150-105">**Column**</span></span>|<span data-ttu-id="17150-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="17150-106">**Data Type**</span></span>|<span data-ttu-id="17150-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="17150-107">**Key/Index**</span></span>|<span data-ttu-id="17150-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="17150-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17150-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="17150-109">**MediaId**</span></span> <br/> |<span data-ttu-id="17150-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="17150-110">tinyint</span></span>  <br/> |<span data-ttu-id="17150-111">Primary</span><span class="sxs-lookup"><span data-stu-id="17150-111">Primary</span></span>  <br/> |<span data-ttu-id="17150-112">Значения: 1–7</span><span class="sxs-lookup"><span data-stu-id="17150-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="17150-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="17150-113">**Media**</span></span> <br/> |<span data-ttu-id="17150-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="17150-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="17150-115">Статическое сопоставление значений MediaID и Media:</span><span class="sxs-lookup"><span data-stu-id="17150-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="17150-116">1 — мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="17150-116">1 -- IM</span></span> <br/>  <span data-ttu-id="17150-117">2 — передача файлов</span><span class="sxs-lookup"><span data-stu-id="17150-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="17150-118">3 — удаленная помощь</span><span class="sxs-lookup"><span data-stu-id="17150-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="17150-119">4 — общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="17150-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="17150-120">5 — звук</span><span class="sxs-lookup"><span data-stu-id="17150-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="17150-121">6 — видео</span><span class="sxs-lookup"><span data-stu-id="17150-121">6 -- Video</span></span> <br/>  <span data-ttu-id="17150-122">7 — приглашение приложения</span><span class="sxs-lookup"><span data-stu-id="17150-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="17150-123">Если вы пытаетесь определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, необходимо использовать следующий фрагмент кода join:</span><span class="sxs-lookup"><span data-stu-id="17150-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
