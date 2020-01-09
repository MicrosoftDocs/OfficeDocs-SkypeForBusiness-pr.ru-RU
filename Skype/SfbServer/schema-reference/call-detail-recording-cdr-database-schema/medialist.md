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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: 243fd3fb705826584f4e786441cdc1faa9075777
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992929"
---
# <a name="medialist-table"></a><span data-ttu-id="a8711-103">Таблица MediaList</span><span class="sxs-lookup"><span data-stu-id="a8711-103">MediaList table</span></span>
 
<span data-ttu-id="a8711-104">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a8711-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="a8711-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a8711-105">**Column**</span></span>|<span data-ttu-id="a8711-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="a8711-106">**Data Type**</span></span>|<span data-ttu-id="a8711-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="a8711-107">**Key/Index**</span></span>|<span data-ttu-id="a8711-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="a8711-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8711-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="a8711-109">**MediaId**</span></span> <br/> |<span data-ttu-id="a8711-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a8711-110">tinyint</span></span>  <br/> |<span data-ttu-id="a8711-111">Primary</span><span class="sxs-lookup"><span data-stu-id="a8711-111">Primary</span></span>  <br/> |<span data-ttu-id="a8711-112">Значения: 1–7</span><span class="sxs-lookup"><span data-stu-id="a8711-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="a8711-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="a8711-113">**Media**</span></span> <br/> |<span data-ttu-id="a8711-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a8711-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a8711-115">Статическое сопоставление значений MediaID и Media</span><span class="sxs-lookup"><span data-stu-id="a8711-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="a8711-116">1 — мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="a8711-116">1 -- IM</span></span> <br/>  <span data-ttu-id="a8711-117">2 – Передача файлов</span><span class="sxs-lookup"><span data-stu-id="a8711-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="a8711-118">3-Удаленная помощь</span><span class="sxs-lookup"><span data-stu-id="a8711-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="a8711-119">4 – общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="a8711-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="a8711-120">5 — аудио</span><span class="sxs-lookup"><span data-stu-id="a8711-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="a8711-121">6 — видео</span><span class="sxs-lookup"><span data-stu-id="a8711-121">6 -- Video</span></span> <br/>  <span data-ttu-id="a8711-122">7 — приглашение на приложение</span><span class="sxs-lookup"><span data-stu-id="a8711-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="a8711-123">Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join: </span><span class="sxs-lookup"><span data-stu-id="a8711-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
