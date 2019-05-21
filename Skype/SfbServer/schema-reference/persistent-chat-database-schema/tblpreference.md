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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295344"
---
# <a name="tblpreference"></a><span data-ttu-id="fcdda-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="fcdda-104">tblPreference</span></span>

<span data-ttu-id="fcdda-105">Тблпреференце включает клиентские настройки пользователей.</span><span class="sxs-lookup"><span data-stu-id="fcdda-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="fcdda-106">Обычно используется клиентами, предшествующими Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fcdda-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="fcdda-107">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="fcdda-107">**Columns**</span></span>


| <span data-ttu-id="fcdda-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fcdda-108">**Column**</span></span>            | <span data-ttu-id="fcdda-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fcdda-109">**Type**</span></span>                        | <span data-ttu-id="fcdda-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fcdda-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="fcdda-111">Префлабел</span><span class="sxs-lookup"><span data-stu-id="fcdda-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="fcdda-112">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fcdda-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="fcdda-113">Метка с таким же форматом, \<как URL-адрес пользователя SIP\></span><span class="sxs-lookup"><span data-stu-id="fcdda-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="fcdda-114">Префсекид</span><span class="sxs-lookup"><span data-stu-id="fcdda-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="fcdda-115">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fcdda-115">int, not null</span></span>  <br/>            | <span data-ttu-id="fcdda-116">Последовательный номер (на метку) для целей управления версиями.</span><span class="sxs-lookup"><span data-stu-id="fcdda-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="fcdda-117">Префконтент</span><span class="sxs-lookup"><span data-stu-id="fcdda-117">prefContent</span></span>  <br/>    | <span data-ttu-id="fcdda-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="fcdda-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="fcdda-119">Закодированное содержимое.</span><span class="sxs-lookup"><span data-stu-id="fcdda-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="fcdda-120">Ластмодифиедби</span><span class="sxs-lookup"><span data-stu-id="fcdda-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="fcdda-121">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="fcdda-121">int, not null</span></span>  <br/>            | <span data-ttu-id="fcdda-122">Идентификатор участника, который обновил предпочтение.</span><span class="sxs-lookup"><span data-stu-id="fcdda-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="fcdda-123">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="fcdda-123">**Key**</span></span>

|<span data-ttu-id="fcdda-124">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="fcdda-124">**Column**</span></span>|<span data-ttu-id="fcdda-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fcdda-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fcdda-126">\<Префлабел, Префсекид\></span><span class="sxs-lookup"><span data-stu-id="fcdda-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="fcdda-127">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="fcdda-127">Primary key.</span></span>  <br/> |


