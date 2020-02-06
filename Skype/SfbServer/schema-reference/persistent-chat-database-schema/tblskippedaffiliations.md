---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812017"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="38d2e-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="38d2e-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="38d2e-104">Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="38d2e-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="38d2e-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="38d2e-105">**Columns**</span></span>

|<span data-ttu-id="38d2e-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="38d2e-106">**Column**</span></span>|<span data-ttu-id="38d2e-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="38d2e-107">**Type**</span></span>|<span data-ttu-id="38d2e-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="38d2e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38d2e-109">принид</span><span class="sxs-lookup"><span data-stu-id="38d2e-109">prinID</span></span>  <br/> |<span data-ttu-id="38d2e-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="38d2e-110">int, not null</span></span>  <br/> |<span data-ttu-id="38d2e-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="38d2e-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="38d2e-112">аффдескриптион</span><span class="sxs-lookup"><span data-stu-id="38d2e-112">affDescription</span></span>  <br/> |<span data-ttu-id="38d2e-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="38d2e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="38d2e-114">Строка, указывающая на принадлежность.</span><span class="sxs-lookup"><span data-stu-id="38d2e-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="38d2e-115">Формат: GUID: _{0}_ uri: _{1}_> ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="38d2e-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="38d2e-116">упдатедби</span><span class="sxs-lookup"><span data-stu-id="38d2e-116">updatedBy</span></span>  <br/> |<span data-ttu-id="38d2e-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="38d2e-117">int, not null</span></span>  <br/> |<span data-ttu-id="38d2e-118">Идентификатор участника, который обновил эту строку.</span><span class="sxs-lookup"><span data-stu-id="38d2e-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="38d2e-119">Это всегда 1 (Системный пользователь), так как служба каталогов Active Directory — это единственный источник этих записей.</span><span class="sxs-lookup"><span data-stu-id="38d2e-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="38d2e-120">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="38d2e-120">**Keys**</span></span>

|<span data-ttu-id="38d2e-121">**Столбцы (-ы)**</span><span class="sxs-lookup"><span data-stu-id="38d2e-121">**Column(s)**</span></span>|<span data-ttu-id="38d2e-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="38d2e-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38d2e-123">\<Принид, Аффдескриптион\></span><span class="sxs-lookup"><span data-stu-id="38d2e-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="38d2e-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="38d2e-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="38d2e-125">принид</span><span class="sxs-lookup"><span data-stu-id="38d2e-125">prinID</span></span>  <br/> |<span data-ttu-id="38d2e-126">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="38d2e-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

