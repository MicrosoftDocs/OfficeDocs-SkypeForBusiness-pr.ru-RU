---
title: Таблица "расположения" в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296121"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6450d-103">Таблица "расположения" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6450d-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6450d-104">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="6450d-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="6450d-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6450d-105">**Column**</span></span>|<span data-ttu-id="6450d-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="6450d-106">**Data Type**</span></span>|<span data-ttu-id="6450d-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="6450d-107">**Key/Index**</span></span>|<span data-ttu-id="6450d-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="6450d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6450d-109">**Сессионидтиме**</span><span class="sxs-lookup"><span data-stu-id="6450d-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="6450d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6450d-110">datetime</span></span>  <br/> |<span data-ttu-id="6450d-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="6450d-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6450d-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="6450d-112">Time of session request.</span></span> <span data-ttu-id="6450d-113">Используется в сочетании с **сессионидсек** для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="6450d-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="6450d-114">Дополнительные сведения приведены [в таблице диалоговые окна в Skype для бизнеса Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="6450d-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6450d-115">**Сессионидсек**</span><span class="sxs-lookup"><span data-stu-id="6450d-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="6450d-116">целое</span><span class="sxs-lookup"><span data-stu-id="6450d-116">int</span></span>  <br/> |<span data-ttu-id="6450d-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="6450d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6450d-118">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="6450d-118">ID number to identify the session.</span></span> <span data-ttu-id="6450d-119">Используется в сочетании с **сессионидтиме** для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="6450d-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="6450d-120">Дополнительные сведения приведены [в таблице диалоговые окна в Skype для бизнеса Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="6450d-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6450d-121">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="6450d-121">**Location**</span></span> <br/> |<span data-ttu-id="6450d-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6450d-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="6450d-123">Место вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="6450d-123">Location of emergency call.</span></span>  <br/> |
   

