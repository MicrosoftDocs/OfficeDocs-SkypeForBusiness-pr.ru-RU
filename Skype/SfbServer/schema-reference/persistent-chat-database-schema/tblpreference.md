---
title: tblPreference
ms.reviewer: ''
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
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879793"
---
# <a name="tblpreference"></a><span data-ttu-id="22758-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="22758-104">tblPreference</span></span>

<span data-ttu-id="22758-105">tblPreference содержит параметры клиента пользователей.</span><span class="sxs-lookup"><span data-stu-id="22758-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="22758-106">Обычно используется клиентами предшествующих Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="22758-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="22758-107">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="22758-107">**Columns**</span></span>


| <span data-ttu-id="22758-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="22758-108">**Column**</span></span>            | <span data-ttu-id="22758-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="22758-109">**Type**</span></span>                        | <span data-ttu-id="22758-110">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="22758-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="22758-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="22758-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="22758-112">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="22758-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="22758-113">Метка имеет формат, таких как: \<uri sip пользователя\></span><span class="sxs-lookup"><span data-stu-id="22758-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="22758-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="22758-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="22758-115">int, не null</span><span class="sxs-lookup"><span data-stu-id="22758-115">int, not null</span></span>  <br/>            | <span data-ttu-id="22758-116">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="22758-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="22758-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="22758-117">prefContent</span></span>  <br/>    | <span data-ttu-id="22758-118">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="22758-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="22758-119">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="22758-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="22758-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="22758-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="22758-121">int, не null</span><span class="sxs-lookup"><span data-stu-id="22758-121">int, not null</span></span>  <br/>            | <span data-ttu-id="22758-122">Идентификатор субъекта, обновившего.</span><span class="sxs-lookup"><span data-stu-id="22758-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="22758-123">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="22758-123">**Key**</span></span>

|<span data-ttu-id="22758-124">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="22758-124">**Column**</span></span>|<span data-ttu-id="22758-125">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="22758-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22758-126">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="22758-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="22758-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="22758-127">Primary key.</span></span>  <br/> |


