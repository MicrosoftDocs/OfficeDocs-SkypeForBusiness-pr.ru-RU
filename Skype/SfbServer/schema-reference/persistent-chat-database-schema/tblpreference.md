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
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375945"
---
# <a name="tblpreference"></a><span data-ttu-id="73482-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="73482-104">tblPreference</span></span>

<span data-ttu-id="73482-105">tblPreference содержит параметры клиента пользователей.</span><span class="sxs-lookup"><span data-stu-id="73482-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="73482-106">Обычно используется клиентами предшествующих Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="73482-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="73482-107">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="73482-107">**Columns**</span></span>


| <span data-ttu-id="73482-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="73482-108">**Column**</span></span>            | <span data-ttu-id="73482-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="73482-109">**Type**</span></span>                        | <span data-ttu-id="73482-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="73482-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="73482-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="73482-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="73482-112">nvarchar (255), отлично от null</span><span class="sxs-lookup"><span data-stu-id="73482-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="73482-113">Метка имеет формат, таких как: \<uri sip пользователя\></span><span class="sxs-lookup"><span data-stu-id="73482-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="73482-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="73482-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="73482-115">int, не null</span><span class="sxs-lookup"><span data-stu-id="73482-115">int, not null</span></span>  <br/>            | <span data-ttu-id="73482-116">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="73482-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="73482-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="73482-117">prefContent</span></span>  <br/>    | <span data-ttu-id="73482-118">nvarchar (максимум)</span><span class="sxs-lookup"><span data-stu-id="73482-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="73482-119">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="73482-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="73482-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="73482-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="73482-121">int, не null</span><span class="sxs-lookup"><span data-stu-id="73482-121">int, not null</span></span>  <br/>            | <span data-ttu-id="73482-122">Идентификатор субъекта, обновившего.</span><span class="sxs-lookup"><span data-stu-id="73482-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="73482-123">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="73482-123">**Key**</span></span>

|<span data-ttu-id="73482-124">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="73482-124">**Column**</span></span>|<span data-ttu-id="73482-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="73482-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73482-126">\<prefLabel prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="73482-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="73482-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="73482-127">Primary key.</span></span>  <br/> |


