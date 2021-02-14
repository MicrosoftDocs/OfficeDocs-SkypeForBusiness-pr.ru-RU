---
title: Таблица Dialogs в Skype для бизнеса Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица Dialogs — это вспомогательная таблица, в которую хранится информация о DialogID для одноранговых сеансов.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816049"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d0630-103">Таблица Dialogs в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d0630-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d0630-104">Таблица Dialogs — это вспомогательная таблица, в которую хранится информация о DialogID для одноранговых сеансов.</span><span class="sxs-lookup"><span data-stu-id="d0630-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="d0630-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="d0630-105">**Column**</span></span>|<span data-ttu-id="d0630-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="d0630-106">**Data Type**</span></span>|<span data-ttu-id="d0630-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="d0630-107">**Key/Index**</span></span>|<span data-ttu-id="d0630-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="d0630-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d0630-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="d0630-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="d0630-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d0630-110">datetime</span></span>  <br/> |<span data-ttu-id="d0630-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d0630-111">Primary</span></span>  <br/> |<span data-ttu-id="d0630-112">Время запроса сеанса; используется в сочетании с SessionIDSeq для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d0630-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="d0630-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="d0630-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="d0630-114">int</span><span class="sxs-lookup"><span data-stu-id="d0630-114">int</span></span>  <br/> |<span data-ttu-id="d0630-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d0630-115">Primary</span></span>  <br/> |<span data-ttu-id="d0630-116">Идентификатор сеанса.</span><span class="sxs-lookup"><span data-stu-id="d0630-116">ID number to identify the session.</span></span> <span data-ttu-id="d0630-117">Используется в сочетании с SessionIDTime для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="d0630-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="d0630-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="d0630-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="d0630-119">int</span><span class="sxs-lookup"><span data-stu-id="d0630-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="d0630-120">Контрольная контрольнаямбла ExternalID.</span><span class="sxs-lookup"><span data-stu-id="d0630-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="d0630-121">Это поле используется для повышения скорости поиска в базе данных.</span><span class="sxs-lookup"><span data-stu-id="d0630-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="d0630-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="d0630-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="d0630-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="d0630-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="d0630-124">Код диалога SIP, хранимый в двоичном файле.</span><span class="sxs-lookup"><span data-stu-id="d0630-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="d0630-125">Двоичный формат:</span><span class="sxs-lookup"><span data-stu-id="d0630-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="d0630-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="d0630-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="d0630-127">Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="d0630-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

