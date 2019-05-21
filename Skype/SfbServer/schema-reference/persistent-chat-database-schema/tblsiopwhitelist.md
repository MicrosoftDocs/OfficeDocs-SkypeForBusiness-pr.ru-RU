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
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295176"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="786b7-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="786b7-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="786b7-104">Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.</span><span class="sxs-lookup"><span data-stu-id="786b7-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="786b7-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="786b7-105">**Columns**</span></span>

|<span data-ttu-id="786b7-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="786b7-106">**Column**</span></span>|<span data-ttu-id="786b7-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="786b7-107">**Type**</span></span>|<span data-ttu-id="786b7-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="786b7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="786b7-109">Сиопид</span><span class="sxs-lookup"><span data-stu-id="786b7-109">siopID</span></span>  <br/> |<span data-ttu-id="786b7-110">GUID, а не NULL</span><span class="sxs-lookup"><span data-stu-id="786b7-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="786b7-111">Идентификатор GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="786b7-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="786b7-112">Сиопнаме</span><span class="sxs-lookup"><span data-stu-id="786b7-112">siopName</span></span>  <br/> |<span data-ttu-id="786b7-113">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="786b7-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="786b7-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="786b7-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="786b7-115">Сиопурл</span><span class="sxs-lookup"><span data-stu-id="786b7-115">siopUrl</span></span>  <br/> |<span data-ttu-id="786b7-116">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="786b7-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="786b7-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="786b7-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="786b7-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="786b7-118">**Key**</span></span>

|<span data-ttu-id="786b7-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="786b7-119">**Column**</span></span>|<span data-ttu-id="786b7-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="786b7-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="786b7-121">Сиопид</span><span class="sxs-lookup"><span data-stu-id="786b7-121">siopID</span></span>  <br/> |<span data-ttu-id="786b7-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="786b7-122">Primary key.</span></span>  <br/> |
   

