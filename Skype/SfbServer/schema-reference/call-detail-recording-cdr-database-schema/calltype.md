---
title: Таблица CallType в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="66c7a-103">Таблица CallType в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66c7a-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="66c7a-104">Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.</span><span class="sxs-lookup"><span data-stu-id="66c7a-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="66c7a-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="66c7a-105">**Column**</span></span>|<span data-ttu-id="66c7a-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="66c7a-106">**Data Type**</span></span>|<span data-ttu-id="66c7a-107">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="66c7a-107">**Key/Index**</span></span>|<span data-ttu-id="66c7a-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="66c7a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66c7a-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="66c7a-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="66c7a-110">целое</span><span class="sxs-lookup"><span data-stu-id="66c7a-110">int</span></span>  <br/> |<span data-ttu-id="66c7a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="66c7a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="66c7a-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="66c7a-112">**CallType**</span></span> <br/> |<span data-ttu-id="66c7a-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="66c7a-113">nvarchar</span></span>  <br/> || <span data-ttu-id="66c7a-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="66c7a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="66c7a-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="66c7a-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="66c7a-116">1 — обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="66c7a-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="66c7a-117">2 — Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="66c7a-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="66c7a-118">3 — аудио</span><span class="sxs-lookup"><span data-stu-id="66c7a-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="66c7a-119">4 — аудио и видео</span><span class="sxs-lookup"><span data-stu-id="66c7a-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="66c7a-120">5 - Передача файла</span><span class="sxs-lookup"><span data-stu-id="66c7a-120">5 - File Transfer</span></span> <br/> |
   

