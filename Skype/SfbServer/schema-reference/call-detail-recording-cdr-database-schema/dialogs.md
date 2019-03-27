---
title: Таблица диалогов в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица диалогов представляет собой вспомогательную таблицу, в которой хранятся сведения об идентификаторах Dialogid для сеансов peer-to-peer.
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889630"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="656e9-103">Таблица диалогов в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="656e9-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="656e9-104">Таблица диалогов представляет собой вспомогательную таблицу, в которой хранятся сведения об идентификаторах Dialogid для сеансов peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="656e9-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="656e9-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="656e9-105">**Column**</span></span>|<span data-ttu-id="656e9-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="656e9-106">**Data Type**</span></span>|<span data-ttu-id="656e9-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="656e9-107">**Key/Index**</span></span>|<span data-ttu-id="656e9-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="656e9-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="656e9-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="656e9-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="656e9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="656e9-110">datetime</span></span>  <br/> |<span data-ttu-id="656e9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="656e9-111">Primary</span></span>  <br/> |<span data-ttu-id="656e9-112">Время запроса сеанса; используется совместно с SessionIDSeq для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="656e9-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="656e9-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="656e9-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="656e9-114">целое</span><span class="sxs-lookup"><span data-stu-id="656e9-114">int</span></span>  <br/> |<span data-ttu-id="656e9-115">Primary</span><span class="sxs-lookup"><span data-stu-id="656e9-115">Primary</span></span>  <br/> |<span data-ttu-id="656e9-116">Номер идентификатора для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="656e9-116">ID number to identify the session.</span></span> <span data-ttu-id="656e9-117">Используется в сочетании с SessionIDTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="656e9-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="656e9-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="656e9-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="656e9-119">целое</span><span class="sxs-lookup"><span data-stu-id="656e9-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="656e9-120">Контрольная сумма ExternalID.</span><span class="sxs-lookup"><span data-stu-id="656e9-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="656e9-121">Это поле используется для повышения скорости поиска по базе данных.</span><span class="sxs-lookup"><span data-stu-id="656e9-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="656e9-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="656e9-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="656e9-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="656e9-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="656e9-124">SIP-идентификатор диалогового окна, сохраненной в качестве двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="656e9-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="656e9-125">Имеет формат двоичного файла:</span><span class="sxs-lookup"><span data-stu-id="656e9-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="656e9-126">диалоговое окно, из тега; для тега</span><span class="sxs-lookup"><span data-stu-id="656e9-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="656e9-127">Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="656e9-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

