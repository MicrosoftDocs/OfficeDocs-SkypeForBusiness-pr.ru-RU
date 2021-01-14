---
title: Таблица Locations в Skype для бизнеса Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например звонке E9-1-1.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821519"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="81496-103">Таблица Locations в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="81496-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="81496-104">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например звонке E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="81496-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="81496-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="81496-105">**Column**</span></span>|<span data-ttu-id="81496-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="81496-106">**Data Type**</span></span>|<span data-ttu-id="81496-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="81496-107">**Key/Index**</span></span>|<span data-ttu-id="81496-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="81496-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81496-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="81496-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="81496-110">datetime</span><span class="sxs-lookup"><span data-stu-id="81496-110">datetime</span></span>  <br/> |<span data-ttu-id="81496-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="81496-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="81496-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="81496-112">Time of session request.</span></span> <span data-ttu-id="81496-113">В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="81496-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="81496-114">Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="81496-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="81496-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="81496-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="81496-116">int</span><span class="sxs-lookup"><span data-stu-id="81496-116">int</span></span>  <br/> |<span data-ttu-id="81496-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="81496-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="81496-118">Идентификатор для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="81496-118">ID number to identify the session.</span></span> <span data-ttu-id="81496-119">В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом.</span><span class="sxs-lookup"><span data-stu-id="81496-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="81496-120">Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="81496-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="81496-121">**Location**</span><span class="sxs-lookup"><span data-stu-id="81496-121">**Location**</span></span> <br/> |<span data-ttu-id="81496-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="81496-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="81496-123">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="81496-123">Location of emergency call.</span></span>  <br/> |
   

