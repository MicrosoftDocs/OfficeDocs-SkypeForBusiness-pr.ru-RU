---
title: Таблица расположения в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например на вызов E9-1-1.
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876946"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="83753-103">Таблица расположения в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="83753-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="83753-104">Каждая запись представляет одну ссылку на расположение в экстренном звонке, например на вызов E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="83753-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="83753-105">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="83753-105">**Column**</span></span>|<span data-ttu-id="83753-106">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="83753-106">**Data Type**</span></span>|<span data-ttu-id="83753-107">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="83753-107">**Key/Index**</span></span>|<span data-ttu-id="83753-108">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="83753-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83753-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="83753-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="83753-110">datetime</span><span class="sxs-lookup"><span data-stu-id="83753-110">datetime</span></span>  <br/> |<span data-ttu-id="83753-111">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="83753-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="83753-112">Время запроса сеанса.</span><span class="sxs-lookup"><span data-stu-id="83753-112">Time of session request.</span></span> <span data-ttu-id="83753-113">Используется совместно с **SessionIdSeq** для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="83753-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="83753-114">В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="83753-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="83753-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="83753-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="83753-116">целое</span><span class="sxs-lookup"><span data-stu-id="83753-116">int</span></span>  <br/> |<span data-ttu-id="83753-117">Основной, внешний</span><span class="sxs-lookup"><span data-stu-id="83753-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="83753-118">Номер идентификатора для идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="83753-118">ID number to identify the session.</span></span> <span data-ttu-id="83753-119">Используется в сочетании с **SessionIdTime** для уникальной идентификации сеанса.</span><span class="sxs-lookup"><span data-stu-id="83753-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="83753-120">В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="83753-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="83753-121">**Расположение**</span><span class="sxs-lookup"><span data-stu-id="83753-121">**Location**</span></span> <br/> |<span data-ttu-id="83753-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="83753-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="83753-123">Расположение экстренного звонка.</span><span class="sxs-lookup"><span data-stu-id="83753-123">Location of emergency call.</span></span>  <br/> |
   

