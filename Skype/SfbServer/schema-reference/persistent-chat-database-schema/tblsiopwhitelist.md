---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924775"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="7178b-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="7178b-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="7178b-104">tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.</span><span class="sxs-lookup"><span data-stu-id="7178b-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="7178b-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="7178b-105">**Columns**</span></span>

|<span data-ttu-id="7178b-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7178b-106">**Column**</span></span>|<span data-ttu-id="7178b-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7178b-107">**Type**</span></span>|<span data-ttu-id="7178b-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7178b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7178b-109">siopID</span><span class="sxs-lookup"><span data-stu-id="7178b-109">siopID</span></span>  <br/> |<span data-ttu-id="7178b-110">Идентификатор GUID, не может быть null</span><span class="sxs-lookup"><span data-stu-id="7178b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7178b-111">GUID надстройки.</span><span class="sxs-lookup"><span data-stu-id="7178b-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7178b-112">siopName</span><span class="sxs-lookup"><span data-stu-id="7178b-112">siopName</span></span>  <br/> |<span data-ttu-id="7178b-113">nvarchar (50), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7178b-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="7178b-114">Отображаемое имя надстройки.</span><span class="sxs-lookup"><span data-stu-id="7178b-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7178b-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="7178b-115">siopUrl</span></span>  <br/> |<span data-ttu-id="7178b-116">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7178b-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7178b-117">URL-адрес надстройки.</span><span class="sxs-lookup"><span data-stu-id="7178b-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="7178b-118">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="7178b-118">**Key**</span></span>

|<span data-ttu-id="7178b-119">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7178b-119">**Column**</span></span>|<span data-ttu-id="7178b-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7178b-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7178b-121">siopID</span><span class="sxs-lookup"><span data-stu-id="7178b-121">siopID</span></span>  <br/> |<span data-ttu-id="7178b-122">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7178b-122">Primary key.</span></span>  <br/> |
   

