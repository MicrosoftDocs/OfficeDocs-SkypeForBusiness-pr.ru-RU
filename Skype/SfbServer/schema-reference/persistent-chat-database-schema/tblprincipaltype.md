---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831539"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="782a1-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="782a1-103">tblPrincipalType</span></span>
 
<span data-ttu-id="782a1-104">Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.</span><span class="sxs-lookup"><span data-stu-id="782a1-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="782a1-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="782a1-105">**Columns**</span></span>

|<span data-ttu-id="782a1-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="782a1-106">**Column**</span></span>|<span data-ttu-id="782a1-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="782a1-107">**Type**</span></span>|<span data-ttu-id="782a1-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="782a1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="782a1-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="782a1-109">ptypeID</span></span>  <br/> |<span data-ttu-id="782a1-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="782a1-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="782a1-111">Идентификатор типа субъекта.</span><span class="sxs-lookup"><span data-stu-id="782a1-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="782a1-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="782a1-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="782a1-113">nvarchar (256), не может быть null</span><span class="sxs-lookup"><span data-stu-id="782a1-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="782a1-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="782a1-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="782a1-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="782a1-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="782a1-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="782a1-116">bit, not null</span></span>  <br/> |<span data-ttu-id="782a1-117">Имеет значение True, если тип соответствует субъектам, которые используются во внутренних целях.</span><span class="sxs-lookup"><span data-stu-id="782a1-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="782a1-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="782a1-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="782a1-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="782a1-119">bit, not null</span></span>  <br/> |<span data-ttu-id="782a1-120">Имеет значение True, если тип соответствует пользователям.</span><span class="sxs-lookup"><span data-stu-id="782a1-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="782a1-121">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="782a1-121">**Key**</span></span>

|<span data-ttu-id="782a1-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="782a1-122">**Column**</span></span>|<span data-ttu-id="782a1-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="782a1-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="782a1-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="782a1-124">ptypeID</span></span>  <br/> |<span data-ttu-id="782a1-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="782a1-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="782a1-126">**Значения субъектов**</span><span class="sxs-lookup"><span data-stu-id="782a1-126">**Principal Values**</span></span>

|<span data-ttu-id="782a1-127">**ИД**</span><span class="sxs-lookup"><span data-stu-id="782a1-127">**ID**</span></span>|<span data-ttu-id="782a1-128">**Роль**</span><span class="sxs-lookup"><span data-stu-id="782a1-128">**Role**</span></span>|<span data-ttu-id="782a1-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="782a1-129">**Description**</span></span>|<span data-ttu-id="782a1-130">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="782a1-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="782a1-131">1 </span><span class="sxs-lookup"><span data-stu-id="782a1-131">1</span></span>  <br/> |<span data-ttu-id="782a1-132">Любой</span><span class="sxs-lookup"><span data-stu-id="782a1-132">Any</span></span>  <br/> |<span data-ttu-id="782a1-p101">Общий субъект неизвестного типа. Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="782a1-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="782a1-135">2 </span><span class="sxs-lookup"><span data-stu-id="782a1-135">2</span></span>  <br/> |<span data-ttu-id="782a1-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="782a1-136">AnyUser</span></span>  <br/> |<span data-ttu-id="782a1-p102">Общий субъект типа "пользователь". Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="782a1-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="782a1-139">Да</span><span class="sxs-lookup"><span data-stu-id="782a1-139">Yes</span></span>  <br/> |
|<span data-ttu-id="782a1-140">3 </span><span class="sxs-lookup"><span data-stu-id="782a1-140">3</span></span>  <br/> |<span data-ttu-id="782a1-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="782a1-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="782a1-p103">Общий субъект типа "группа". Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="782a1-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="782a1-144">4 </span><span class="sxs-lookup"><span data-stu-id="782a1-144">4</span></span>  <br/> |<span data-ttu-id="782a1-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="782a1-145">SystemUser</span></span>  <br/> |<span data-ttu-id="782a1-146">Основной, используемый внутренним сервером сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="782a1-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="782a1-147">5 </span><span class="sxs-lookup"><span data-stu-id="782a1-147">5</span></span>  <br/> |<span data-ttu-id="782a1-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="782a1-148">User</span></span>  <br/> |<span data-ttu-id="782a1-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="782a1-149">Regular user.</span></span>  <br/> |<span data-ttu-id="782a1-150">Да</span><span class="sxs-lookup"><span data-stu-id="782a1-150">Yes</span></span>  <br/> |
|<span data-ttu-id="782a1-151">8 </span><span class="sxs-lookup"><span data-stu-id="782a1-151">8</span></span>  <br/> |<span data-ttu-id="782a1-152">DC</span><span class="sxs-lookup"><span data-stu-id="782a1-152">DC</span></span>  <br/> |<span data-ttu-id="782a1-153">Контроллер домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="782a1-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="782a1-154">9 </span><span class="sxs-lookup"><span data-stu-id="782a1-154">9</span></span>  <br/> |<span data-ttu-id="782a1-155">Group</span><span class="sxs-lookup"><span data-stu-id="782a1-155">Group</span></span>  <br/> |<span data-ttu-id="782a1-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="782a1-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="782a1-157">10 </span><span class="sxs-lookup"><span data-stu-id="782a1-157">10</span></span>  <br/> |<span data-ttu-id="782a1-158">Folder</span><span class="sxs-lookup"><span data-stu-id="782a1-158">Folder</span></span>  <br/> |<span data-ttu-id="782a1-159">Контейнер или подразделение Active Directory.</span><span class="sxs-lookup"><span data-stu-id="782a1-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="782a1-160">См. также</span><span class="sxs-lookup"><span data-stu-id="782a1-160">See also</span></span>

[<span data-ttu-id="782a1-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="782a1-161">tblPrincipal</span></span>](tblprincipal.md)
