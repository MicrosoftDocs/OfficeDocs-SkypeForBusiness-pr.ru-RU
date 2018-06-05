---
title: Таблица MediaList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: c9309219399fac30e318f8e112dd82269fff5ac2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569770"
---
# <a name="medialist-table"></a><span data-ttu-id="4dea5-103">Таблица MediaList</span><span class="sxs-lookup"><span data-stu-id="4dea5-103">MediaList table</span></span>
 
<span data-ttu-id="4dea5-104">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4dea5-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="4dea5-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="4dea5-105">**Column**</span></span>|<span data-ttu-id="4dea5-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="4dea5-106">**Data Type**</span></span>|<span data-ttu-id="4dea5-107">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="4dea5-107">**Key/Index**</span></span>|<span data-ttu-id="4dea5-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="4dea5-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4dea5-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="4dea5-109">**MediaId**</span></span> <br/> |<span data-ttu-id="4dea5-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="4dea5-110">tinyint</span></span>  <br/> |<span data-ttu-id="4dea5-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4dea5-111">Primary</span></span>  <br/> |<span data-ttu-id="4dea5-112">Значения: 1–7</span><span class="sxs-lookup"><span data-stu-id="4dea5-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="4dea5-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="4dea5-113">**Media**</span></span> <br/> |<span data-ttu-id="4dea5-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4dea5-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="4dea5-115">Статическое сопоставление значений MediaID и Media</span><span class="sxs-lookup"><span data-stu-id="4dea5-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="4dea5-116">1 — мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="4dea5-116">1 -- IM</span></span> <br/>  <span data-ttu-id="4dea5-117">2 - передача файлов</span><span class="sxs-lookup"><span data-stu-id="4dea5-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="4dea5-118">3 — удаленный помощник</span><span class="sxs-lookup"><span data-stu-id="4dea5-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="4dea5-119">4 - общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="4dea5-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="4dea5-120">5 — аудио</span><span class="sxs-lookup"><span data-stu-id="4dea5-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="4dea5-121">6 — видео</span><span class="sxs-lookup"><span data-stu-id="4dea5-121">6 -- Video</span></span> <br/>  <span data-ttu-id="4dea5-122">7 - приглашение из приложения</span><span class="sxs-lookup"><span data-stu-id="4dea5-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="4dea5-123">Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join: </span><span class="sxs-lookup"><span data-stu-id="4dea5-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```