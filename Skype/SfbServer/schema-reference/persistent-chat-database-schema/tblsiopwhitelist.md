---
title: tblSiopWhiteList
ms.reviewer: ''
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
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212385"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="6b5fd-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="6b5fd-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="6b5fd-104">tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.</span><span class="sxs-lookup"><span data-stu-id="6b5fd-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="6b5fd-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-105">**Columns**</span></span>

|<span data-ttu-id="6b5fd-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-106">**Column**</span></span>|<span data-ttu-id="6b5fd-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-107">**Type**</span></span>|<span data-ttu-id="6b5fd-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6b5fd-109">siopID</span><span class="sxs-lookup"><span data-stu-id="6b5fd-109">siopID</span></span>  <br/> |<span data-ttu-id="6b5fd-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="6b5fd-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="6b5fd-111">GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="6b5fd-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="6b5fd-112">siopName</span><span class="sxs-lookup"><span data-stu-id="6b5fd-112">siopName</span></span>  <br/> |<span data-ttu-id="6b5fd-113">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="6b5fd-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="6b5fd-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="6b5fd-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="6b5fd-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="6b5fd-115">siopUrl</span></span>  <br/> |<span data-ttu-id="6b5fd-116">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="6b5fd-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="6b5fd-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="6b5fd-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="6b5fd-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-118">**Key**</span></span>

|<span data-ttu-id="6b5fd-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-119">**Column**</span></span>|<span data-ttu-id="6b5fd-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6b5fd-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b5fd-121">siopID</span><span class="sxs-lookup"><span data-stu-id="6b5fd-121">siopID</span></span>  <br/> |<span data-ttu-id="6b5fd-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="6b5fd-122">Primary key.</span></span>  <br/> |
   

