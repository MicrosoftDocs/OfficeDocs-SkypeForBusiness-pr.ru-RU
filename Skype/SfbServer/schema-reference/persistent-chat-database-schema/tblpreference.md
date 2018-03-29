---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="7ff55-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="7ff55-104">tblPreference</span></span>
 
<span data-ttu-id="7ff55-105">tblPreference содержит параметры клиента пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ff55-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="7ff55-106">Обычно используется клиентами предшествующих Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7ff55-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="7ff55-107">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="7ff55-107">**Columns**</span></span>

|<span data-ttu-id="7ff55-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7ff55-108">**Column**</span></span>|<span data-ttu-id="7ff55-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="7ff55-109">**Type**</span></span>|<span data-ttu-id="7ff55-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7ff55-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ff55-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="7ff55-111">prefLabel</span></span>  <br/> |<span data-ttu-id="7ff55-112">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="7ff55-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7ff55-113">Метка имеет формат, таких как: \<uri sip пользователя\></span><span class="sxs-lookup"><span data-stu-id="7ff55-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="7ff55-114">имя пользователя. \<набор установок\>.</span><span class="sxs-lookup"><span data-stu-id="7ff55-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="7ff55-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="7ff55-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="7ff55-116">int, не null</span><span class="sxs-lookup"><span data-stu-id="7ff55-116">int, not null</span></span>  <br/> |<span data-ttu-id="7ff55-117">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="7ff55-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="7ff55-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="7ff55-118">prefContent</span></span>  <br/> |<span data-ttu-id="7ff55-119">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="7ff55-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="7ff55-120">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="7ff55-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="7ff55-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="7ff55-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="7ff55-122">int, не null</span><span class="sxs-lookup"><span data-stu-id="7ff55-122">int, not null</span></span>  <br/> |<span data-ttu-id="7ff55-123">Идентификатор субъекта, обновившего.</span><span class="sxs-lookup"><span data-stu-id="7ff55-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="7ff55-124">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="7ff55-124">**Key**</span></span>

|<span data-ttu-id="7ff55-125">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="7ff55-125">**Column**</span></span>|<span data-ttu-id="7ff55-126">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7ff55-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7ff55-127">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="7ff55-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="7ff55-128">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="7ff55-128">Primary key.</span></span>  <br/> |
   

