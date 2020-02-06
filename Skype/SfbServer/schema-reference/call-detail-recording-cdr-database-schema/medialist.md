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
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815037"
---
# <a name="medialist-table"></a><span data-ttu-id="bf4b8-103">Таблица MediaList</span><span class="sxs-lookup"><span data-stu-id="bf4b8-103">MediaList table</span></span>
 
<span data-ttu-id="bf4b8-104">Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="bf4b8-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="bf4b8-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="bf4b8-105">**Column**</span></span>|<span data-ttu-id="bf4b8-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="bf4b8-106">**Data Type**</span></span>|<span data-ttu-id="bf4b8-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="bf4b8-107">**Key/Index**</span></span>|<span data-ttu-id="bf4b8-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="bf4b8-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf4b8-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="bf4b8-109">**MediaId**</span></span> <br/> |<span data-ttu-id="bf4b8-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf4b8-110">tinyint</span></span>  <br/> |<span data-ttu-id="bf4b8-111">Primary</span><span class="sxs-lookup"><span data-stu-id="bf4b8-111">Primary</span></span>  <br/> |<span data-ttu-id="bf4b8-112">Значения: 1–7</span><span class="sxs-lookup"><span data-stu-id="bf4b8-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="bf4b8-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="bf4b8-113">**Media**</span></span> <br/> |<span data-ttu-id="bf4b8-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bf4b8-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="bf4b8-115">Статическое сопоставление значений MediaID и Media</span><span class="sxs-lookup"><span data-stu-id="bf4b8-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="bf4b8-116">1 — мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="bf4b8-116">1 -- IM</span></span> <br/>  <span data-ttu-id="bf4b8-117">2 – Передача файлов</span><span class="sxs-lookup"><span data-stu-id="bf4b8-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="bf4b8-118">3-Удаленная помощь</span><span class="sxs-lookup"><span data-stu-id="bf4b8-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="bf4b8-119">4 – общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="bf4b8-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="bf4b8-120">5 — аудио</span><span class="sxs-lookup"><span data-stu-id="bf4b8-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="bf4b8-121">6 — видео</span><span class="sxs-lookup"><span data-stu-id="bf4b8-121">6 -- Video</span></span> <br/>  <span data-ttu-id="bf4b8-122">7 — приглашение на приложение</span><span class="sxs-lookup"><span data-stu-id="bf4b8-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="bf4b8-123">Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join: </span><span class="sxs-lookup"><span data-stu-id="bf4b8-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
