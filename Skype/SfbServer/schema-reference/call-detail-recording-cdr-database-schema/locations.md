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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815117"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="65395-103">Таблица "расположения" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="65395-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="65395-104">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="65395-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="65395-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="65395-105">**Column**</span></span>|<span data-ttu-id="65395-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="65395-106">**Data Type**</span></span>|<span data-ttu-id="65395-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="65395-107">**Key/Index**</span></span>|<span data-ttu-id="65395-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="65395-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65395-109">**сессионидтиме**</span><span class="sxs-lookup"><span data-stu-id="65395-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="65395-110">datetime</span><span class="sxs-lookup"><span data-stu-id="65395-110">datetime</span></span>  <br/> |<span data-ttu-id="65395-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="65395-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="65395-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="65395-112">Time of session request.</span></span> <span data-ttu-id="65395-113">Используется в сочетании с **сессионидсек** для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="65395-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="65395-114">Дополнительные сведения приведены [в таблице диалоговые окна в Skype для бизнеса Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="65395-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="65395-115">**сессионидсек**</span><span class="sxs-lookup"><span data-stu-id="65395-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="65395-116">целое</span><span class="sxs-lookup"><span data-stu-id="65395-116">int</span></span>  <br/> |<span data-ttu-id="65395-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="65395-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="65395-118">ИДЕНТИФИКАЦИОНный номер для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="65395-118">ID number to identify the session.</span></span> <span data-ttu-id="65395-119">Используется в сочетании с **сессионидтиме** для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="65395-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="65395-120">Дополнительные сведения приведены [в таблице диалоговые окна в Skype для бизнеса Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="65395-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="65395-121">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="65395-121">**Location**</span></span> <br/> |<span data-ttu-id="65395-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="65395-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="65395-123">Место вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="65395-123">Location of emergency call.</span></span>  <br/> |
   

