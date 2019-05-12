---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929921"
---
# <a name="tblpreference"></a><span data-ttu-id="507e9-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="507e9-104">tblPreference</span></span>

<span data-ttu-id="507e9-105">tblPreference содержит параметры клиента пользователей.</span><span class="sxs-lookup"><span data-stu-id="507e9-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="507e9-106">Обычно используется клиентами предшествующих Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="507e9-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="507e9-107">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="507e9-107">**Columns**</span></span>


| <span data-ttu-id="507e9-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="507e9-108">**Column**</span></span>            | <span data-ttu-id="507e9-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="507e9-109">**Type**</span></span>                        | <span data-ttu-id="507e9-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="507e9-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="507e9-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="507e9-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="507e9-112">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="507e9-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="507e9-113">Метка имеет формат, таких как: \<uri sip пользователя\></span><span class="sxs-lookup"><span data-stu-id="507e9-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="507e9-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="507e9-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="507e9-115">int, не null</span><span class="sxs-lookup"><span data-stu-id="507e9-115">int, not null</span></span>  <br/>            | <span data-ttu-id="507e9-116">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="507e9-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="507e9-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="507e9-117">prefContent</span></span>  <br/>    | <span data-ttu-id="507e9-118">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="507e9-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="507e9-119">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="507e9-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="507e9-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="507e9-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="507e9-121">int, не null</span><span class="sxs-lookup"><span data-stu-id="507e9-121">int, not null</span></span>  <br/>            | <span data-ttu-id="507e9-122">Идентификатор субъекта, обновившего.</span><span class="sxs-lookup"><span data-stu-id="507e9-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="507e9-123">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="507e9-123">**Key**</span></span>

|<span data-ttu-id="507e9-124">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="507e9-124">**Column**</span></span>|<span data-ttu-id="507e9-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="507e9-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="507e9-126">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="507e9-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="507e9-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="507e9-127">Primary key.</span></span>  <br/> |


