---
title: tblsiopwhitelist —
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="7c0cb-103">tblsiopwhitelist —</span><span class="sxs-lookup"><span data-stu-id="7c0cb-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="7c0cb-104">tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.</span><span class="sxs-lookup"><span data-stu-id="7c0cb-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="7c0cb-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-105">**Columns**</span></span>

|<span data-ttu-id="7c0cb-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-106">**Column**</span></span>|<span data-ttu-id="7c0cb-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-107">**Type**</span></span>|<span data-ttu-id="7c0cb-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7c0cb-109">siopID</span><span class="sxs-lookup"><span data-stu-id="7c0cb-109">siopID</span></span>  <br/> |<span data-ttu-id="7c0cb-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="7c0cb-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7c0cb-111">GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="7c0cb-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7c0cb-112">siopName</span><span class="sxs-lookup"><span data-stu-id="7c0cb-112">siopName</span></span>  <br/> |<span data-ttu-id="7c0cb-113">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7c0cb-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="7c0cb-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="7c0cb-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7c0cb-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="7c0cb-115">siopUrl</span></span>  <br/> |<span data-ttu-id="7c0cb-116">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7c0cb-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7c0cb-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="7c0cb-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="7c0cb-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-118">**Key**</span></span>

|<span data-ttu-id="7c0cb-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-119">**Column**</span></span>|<span data-ttu-id="7c0cb-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7c0cb-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c0cb-121">siopID</span><span class="sxs-lookup"><span data-stu-id="7c0cb-121">siopID</span></span>  <br/> |<span data-ttu-id="7c0cb-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7c0cb-122">Primary key.</span></span>  <br/> |
   

