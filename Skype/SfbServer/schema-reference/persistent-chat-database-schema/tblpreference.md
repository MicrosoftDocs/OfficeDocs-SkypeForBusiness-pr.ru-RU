---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит настройки клиента пользователей. Обычно это используется клиентами, предшествующими Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815909"
---
# <a name="tblpreference"></a><span data-ttu-id="0f969-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="0f969-104">tblPreference</span></span>

<span data-ttu-id="0f969-105">tblPreference содержит настройки клиента пользователей.</span><span class="sxs-lookup"><span data-stu-id="0f969-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="0f969-106">Обычно это используется клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0f969-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="0f969-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="0f969-107">**Columns**</span></span>


| <span data-ttu-id="0f969-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0f969-108">**Column**</span></span>            | <span data-ttu-id="0f969-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0f969-109">**Type**</span></span>                        | <span data-ttu-id="0f969-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0f969-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="0f969-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="0f969-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="0f969-112">nvarchar (255), не равно null</span><span class="sxs-lookup"><span data-stu-id="0f969-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="0f969-113">Метка в таком формате, как: \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="0f969-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="0f969-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="0f969-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="0f969-115">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="0f969-115">int, not null</span></span>  <br/>            | <span data-ttu-id="0f969-116">Порядковый номер (каждой отдельной метки) для управления версиями.</span><span class="sxs-lookup"><span data-stu-id="0f969-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="0f969-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="0f969-117">prefContent</span></span>  <br/>    | <span data-ttu-id="0f969-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="0f969-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="0f969-119">Зашифрованное содержимое.</span><span class="sxs-lookup"><span data-stu-id="0f969-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="0f969-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="0f969-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="0f969-121">int, не равно null</span><span class="sxs-lookup"><span data-stu-id="0f969-121">int, not null</span></span>  <br/>            | <span data-ttu-id="0f969-122">Идентификатор субъекта, обновившего параметр.</span><span class="sxs-lookup"><span data-stu-id="0f969-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="0f969-123">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="0f969-123">**Key**</span></span>

|<span data-ttu-id="0f969-124">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="0f969-124">**Column**</span></span>|<span data-ttu-id="0f969-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0f969-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="0f969-126">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="0f969-126">Primary key.</span></span>  <br/> |


