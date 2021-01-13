---
title: Таблица CallType в Skype для бизнеса Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813369"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="eda31-103">Таблица CallType в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="eda31-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eda31-104">Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.</span><span class="sxs-lookup"><span data-stu-id="eda31-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="eda31-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="eda31-105">**Column**</span></span>|<span data-ttu-id="eda31-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="eda31-106">**Data Type**</span></span>|<span data-ttu-id="eda31-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="eda31-107">**Key/Index**</span></span>|<span data-ttu-id="eda31-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="eda31-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eda31-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="eda31-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="eda31-110">int</span><span class="sxs-lookup"><span data-stu-id="eda31-110">int</span></span>  <br/> |<span data-ttu-id="eda31-111">Primary</span><span class="sxs-lookup"><span data-stu-id="eda31-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="eda31-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="eda31-112">**CallType**</span></span> <br/> |<span data-ttu-id="eda31-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="eda31-113">nvarchar</span></span>  <br/> || <span data-ttu-id="eda31-114">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="eda31-114">Allowed values:</span></span> <br/>  <span data-ttu-id="eda31-115">0 — неизвестный</span><span class="sxs-lookup"><span data-stu-id="eda31-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="eda31-116">1 — обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="eda31-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="eda31-117">2 — общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="eda31-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="eda31-118">3 — аудио</span><span class="sxs-lookup"><span data-stu-id="eda31-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="eda31-119">4 — звук и видео</span><span class="sxs-lookup"><span data-stu-id="eda31-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="eda31-120">5 — передача файлов</span><span class="sxs-lookup"><span data-stu-id="eda31-120">5 - File Transfer</span></span> <br/> |
   

