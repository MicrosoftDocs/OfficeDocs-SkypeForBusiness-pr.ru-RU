---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831489"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="a3cfe-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="a3cfe-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="a3cfe-104">tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="a3cfe-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-105">**Columns**</span></span>

|<span data-ttu-id="a3cfe-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-106">**Column**</span></span>|<span data-ttu-id="a3cfe-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-107">**Type**</span></span>|<span data-ttu-id="a3cfe-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a3cfe-109">siopID</span><span class="sxs-lookup"><span data-stu-id="a3cfe-109">siopID</span></span>  <br/> |<span data-ttu-id="a3cfe-110">GUID, отлично от null</span><span class="sxs-lookup"><span data-stu-id="a3cfe-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a3cfe-111">GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="a3cfe-112">siopName</span><span class="sxs-lookup"><span data-stu-id="a3cfe-112">siopName</span></span>  <br/> |<span data-ttu-id="a3cfe-113">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="a3cfe-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="a3cfe-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="a3cfe-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="a3cfe-115">siopUrl</span></span>  <br/> |<span data-ttu-id="a3cfe-116">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="a3cfe-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a3cfe-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="a3cfe-118">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-118">**Key**</span></span>

|<span data-ttu-id="a3cfe-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-119">**Column**</span></span>|<span data-ttu-id="a3cfe-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a3cfe-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3cfe-121">siopID</span><span class="sxs-lookup"><span data-stu-id="a3cfe-121">siopID</span></span>  <br/> |<span data-ttu-id="a3cfe-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="a3cfe-122">Primary key.</span></span>  <br/> |
   

