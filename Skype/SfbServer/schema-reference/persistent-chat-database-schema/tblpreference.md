---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814557"
---
# <a name="tblpreference"></a><span data-ttu-id="00cdc-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="00cdc-104">tblPreference</span></span>

<span data-ttu-id="00cdc-105">Тблпреференце включает клиентские настройки пользователей.</span><span class="sxs-lookup"><span data-stu-id="00cdc-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="00cdc-106">Обычно используется клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="00cdc-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="00cdc-107">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="00cdc-107">**Columns**</span></span>


| <span data-ttu-id="00cdc-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="00cdc-108">**Column**</span></span>            | <span data-ttu-id="00cdc-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="00cdc-109">**Type**</span></span>                        | <span data-ttu-id="00cdc-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="00cdc-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="00cdc-111">префлабел</span><span class="sxs-lookup"><span data-stu-id="00cdc-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="00cdc-112">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="00cdc-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="00cdc-113">Метка с таким же форматом, \<как URL-адрес пользователя SIP\></span><span class="sxs-lookup"><span data-stu-id="00cdc-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="00cdc-114">префсекид</span><span class="sxs-lookup"><span data-stu-id="00cdc-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="00cdc-115">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="00cdc-115">int, not null</span></span>  <br/>            | <span data-ttu-id="00cdc-116">Последовательный номер (на метку) для целей управления версиями.</span><span class="sxs-lookup"><span data-stu-id="00cdc-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="00cdc-117">префконтент</span><span class="sxs-lookup"><span data-stu-id="00cdc-117">prefContent</span></span>  <br/>    | <span data-ttu-id="00cdc-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="00cdc-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="00cdc-119">Закодированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="00cdc-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="00cdc-120">ластмодифиедби</span><span class="sxs-lookup"><span data-stu-id="00cdc-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="00cdc-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="00cdc-121">int, not null</span></span>  <br/>            | <span data-ttu-id="00cdc-122">Идентификатор участника, который обновил предпочтение.</span><span class="sxs-lookup"><span data-stu-id="00cdc-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="00cdc-123">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="00cdc-123">**Key**</span></span>

|<span data-ttu-id="00cdc-124">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="00cdc-124">**Column**</span></span>|<span data-ttu-id="00cdc-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="00cdc-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00cdc-126">\<Префлабел, Префсекид\></span><span class="sxs-lookup"><span data-stu-id="00cdc-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="00cdc-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="00cdc-127">Primary key.</span></span>  <br/> |


