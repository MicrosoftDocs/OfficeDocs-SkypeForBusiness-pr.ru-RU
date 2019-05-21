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
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295155"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="40a1d-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="40a1d-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="40a1d-104">Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).</span><span class="sxs-lookup"><span data-stu-id="40a1d-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="40a1d-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="40a1d-105">**Columns**</span></span>

|<span data-ttu-id="40a1d-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="40a1d-106">**Column**</span></span>|<span data-ttu-id="40a1d-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="40a1d-107">**Type**</span></span>|<span data-ttu-id="40a1d-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="40a1d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40a1d-109">Принид</span><span class="sxs-lookup"><span data-stu-id="40a1d-109">prinID</span></span>  <br/> |<span data-ttu-id="40a1d-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40a1d-110">int, not null</span></span>  <br/> |<span data-ttu-id="40a1d-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="40a1d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="40a1d-112">Аффдескриптион</span><span class="sxs-lookup"><span data-stu-id="40a1d-112">affDescription</span></span>  <br/> |<span data-ttu-id="40a1d-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40a1d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="40a1d-114">Строка, указывающая на принадлежность.</span><span class="sxs-lookup"><span data-stu-id="40a1d-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="40a1d-115">Формат: GUID: _{0}_ URI: _{1}__гт_ ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="40a1d-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="40a1d-116">Упдатедби</span><span class="sxs-lookup"><span data-stu-id="40a1d-116">updatedBy</span></span>  <br/> |<span data-ttu-id="40a1d-117">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="40a1d-117">int, not null</span></span>  <br/> |<span data-ttu-id="40a1d-118">Идентификатор участника, который обновил эту строку.</span><span class="sxs-lookup"><span data-stu-id="40a1d-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="40a1d-119">Это всегда 1 (Системный пользователь), так как служба каталогов Active Directory — это единственный источник этих записей.</span><span class="sxs-lookup"><span data-stu-id="40a1d-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="40a1d-120">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="40a1d-120">**Keys**</span></span>

|<span data-ttu-id="40a1d-121">**Столбцы (-ы)**</span><span class="sxs-lookup"><span data-stu-id="40a1d-121">**Column(s)**</span></span>|<span data-ttu-id="40a1d-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="40a1d-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40a1d-123">\<Принид, Аффдескриптион\></span><span class="sxs-lookup"><span data-stu-id="40a1d-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="40a1d-124">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="40a1d-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="40a1d-125">Принид</span><span class="sxs-lookup"><span data-stu-id="40a1d-125">prinID</span></span>  <br/> |<span data-ttu-id="40a1d-126">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="40a1d-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

