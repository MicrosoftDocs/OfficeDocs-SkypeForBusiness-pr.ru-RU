---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812117"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="9e434-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="9e434-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="9e434-104">Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.</span><span class="sxs-lookup"><span data-stu-id="9e434-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="9e434-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="9e434-105">**Columns**</span></span>

|<span data-ttu-id="9e434-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9e434-106">**Column**</span></span>|<span data-ttu-id="9e434-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9e434-107">**Type**</span></span>|<span data-ttu-id="9e434-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9e434-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9e434-109">сиопид</span><span class="sxs-lookup"><span data-stu-id="9e434-109">siopID</span></span>  <br/> |<span data-ttu-id="9e434-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="9e434-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="9e434-111">Идентификатор GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="9e434-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="9e434-112">сиопнаме</span><span class="sxs-lookup"><span data-stu-id="9e434-112">siopName</span></span>  <br/> |<span data-ttu-id="9e434-113">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9e434-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="9e434-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="9e434-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="9e434-115">сиопурл</span><span class="sxs-lookup"><span data-stu-id="9e434-115">siopUrl</span></span>  <br/> |<span data-ttu-id="9e434-116">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9e434-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="9e434-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="9e434-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="9e434-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="9e434-118">**Key**</span></span>

|<span data-ttu-id="9e434-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9e434-119">**Column**</span></span>|<span data-ttu-id="9e434-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9e434-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e434-121">сиопид</span><span class="sxs-lookup"><span data-stu-id="9e434-121">siopID</span></span>  <br/> |<span data-ttu-id="9e434-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="9e434-122">Primary key.</span></span>  <br/> |
   

