---
title: Таблица MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888518"
---
# <a name="medialist-table"></a><span data-ttu-id="7db70-103">Таблица MediaList</span><span class="sxs-lookup"><span data-stu-id="7db70-103">MediaList table</span></span>
 
<span data-ttu-id="7db70-104">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="7db70-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="7db70-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7db70-105">**Column**</span></span>|<span data-ttu-id="7db70-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="7db70-106">**Data Type**</span></span>|<span data-ttu-id="7db70-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="7db70-107">**Key/Index**</span></span>|<span data-ttu-id="7db70-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="7db70-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7db70-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="7db70-109">**MediaId**</span></span> <br/> |<span data-ttu-id="7db70-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7db70-110">tinyint</span></span>  <br/> |<span data-ttu-id="7db70-111">Primary</span><span class="sxs-lookup"><span data-stu-id="7db70-111">Primary</span></span>  <br/> |<span data-ttu-id="7db70-112">Значения: 1–7</span><span class="sxs-lookup"><span data-stu-id="7db70-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="7db70-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="7db70-113">**Media**</span></span> <br/> |<span data-ttu-id="7db70-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7db70-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7db70-115">Статическое сопоставление значений MediaID и Media</span><span class="sxs-lookup"><span data-stu-id="7db70-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="7db70-116">1 — мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="7db70-116">1 -- IM</span></span> <br/>  <span data-ttu-id="7db70-117">2 – Передача файлов</span><span class="sxs-lookup"><span data-stu-id="7db70-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="7db70-118">3-Удаленная помощь</span><span class="sxs-lookup"><span data-stu-id="7db70-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="7db70-119">4 – общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="7db70-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="7db70-120">5 — аудио</span><span class="sxs-lookup"><span data-stu-id="7db70-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="7db70-121">6 — видео</span><span class="sxs-lookup"><span data-stu-id="7db70-121">6 -- Video</span></span> <br/>  <span data-ttu-id="7db70-122">7 — приглашение на приложение</span><span class="sxs-lookup"><span data-stu-id="7db70-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="7db70-123">Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join: </span><span class="sxs-lookup"><span data-stu-id="7db70-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
