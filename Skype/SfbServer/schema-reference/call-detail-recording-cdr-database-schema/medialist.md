---
title: Таблица MediaList
ms.reviewer: ''
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
ms.openlocfilehash: 72ae6dbb145c3bb284f1090b01585591e4e773bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212910"
---
# <a name="medialist-table"></a><span data-ttu-id="7d194-103">Таблица MediaList</span><span class="sxs-lookup"><span data-stu-id="7d194-103">MediaList table</span></span>
 
<span data-ttu-id="7d194-104">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="7d194-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="7d194-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7d194-105">**Column**</span></span>|<span data-ttu-id="7d194-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7d194-106">**Data Type**</span></span>|<span data-ttu-id="7d194-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7d194-107">**Key/Index**</span></span>|<span data-ttu-id="7d194-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7d194-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d194-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="7d194-109">**MediaId**</span></span> <br/> |<span data-ttu-id="7d194-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7d194-110">tinyint</span></span>  <br/> |<span data-ttu-id="7d194-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7d194-111">Primary</span></span>  <br/> |<span data-ttu-id="7d194-112">Значения: 1–7</span><span class="sxs-lookup"><span data-stu-id="7d194-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="7d194-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="7d194-113">**Media**</span></span> <br/> |<span data-ttu-id="7d194-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7d194-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7d194-115">Статическое сопоставление значений MediaID и Media</span><span class="sxs-lookup"><span data-stu-id="7d194-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="7d194-116">1 — мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="7d194-116">1 -- IM</span></span> <br/>  <span data-ttu-id="7d194-117">2 - передача файлов</span><span class="sxs-lookup"><span data-stu-id="7d194-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="7d194-118">3 — удаленный помощник</span><span class="sxs-lookup"><span data-stu-id="7d194-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="7d194-119">4 - общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="7d194-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="7d194-120">5 — аудио</span><span class="sxs-lookup"><span data-stu-id="7d194-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="7d194-121">6 — видео</span><span class="sxs-lookup"><span data-stu-id="7d194-121">6 -- Video</span></span> <br/>  <span data-ttu-id="7d194-122">7 - приглашение из приложения</span><span class="sxs-lookup"><span data-stu-id="7d194-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="7d194-123">Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join: </span><span class="sxs-lookup"><span data-stu-id="7d194-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
