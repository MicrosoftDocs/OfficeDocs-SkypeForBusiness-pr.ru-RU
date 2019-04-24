---
title: Таблица CallType в Скайп для Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213363"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="98308-103">Таблица CallType в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="98308-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="98308-104">Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.</span><span class="sxs-lookup"><span data-stu-id="98308-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="98308-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="98308-105">**Column**</span></span>|<span data-ttu-id="98308-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="98308-106">**Data Type**</span></span>|<span data-ttu-id="98308-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="98308-107">**Key/Index**</span></span>|<span data-ttu-id="98308-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="98308-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="98308-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="98308-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="98308-110">целое</span><span class="sxs-lookup"><span data-stu-id="98308-110">int</span></span>  <br/> |<span data-ttu-id="98308-111">Primary</span><span class="sxs-lookup"><span data-stu-id="98308-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="98308-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="98308-112">**CallType**</span></span> <br/> |<span data-ttu-id="98308-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="98308-113">nvarchar</span></span>  <br/> || <span data-ttu-id="98308-114">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="98308-114">Allowed values:</span></span> <br/>  <span data-ttu-id="98308-115">0 — Неизвестный</span><span class="sxs-lookup"><span data-stu-id="98308-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="98308-116">1 — обмен мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="98308-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="98308-117">2 — Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="98308-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="98308-118">3 — аудио</span><span class="sxs-lookup"><span data-stu-id="98308-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="98308-119">4 — аудио и видео</span><span class="sxs-lookup"><span data-stu-id="98308-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="98308-120">5 - Передача файла</span><span class="sxs-lookup"><span data-stu-id="98308-120">5 - File Transfer</span></span> <br/> |
   

