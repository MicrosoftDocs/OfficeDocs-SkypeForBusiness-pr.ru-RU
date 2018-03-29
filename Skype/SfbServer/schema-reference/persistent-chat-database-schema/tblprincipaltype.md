---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Таблица tblPrincipalType содержит типы субъектов для возможности в таблице tblPrincipal.
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a><span data-ttu-id="8b196-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="8b196-103">tblPrincipalType</span></span>
 
<span data-ttu-id="8b196-104">Таблица tblPrincipalType содержит типы субъектов для возможности в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8b196-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="8b196-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="8b196-105">**Columns**</span></span>

|<span data-ttu-id="8b196-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8b196-106">**Column**</span></span>|<span data-ttu-id="8b196-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8b196-107">**Type**</span></span>|<span data-ttu-id="8b196-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8b196-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b196-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="8b196-109">ptypeID</span></span>  <br/> |<span data-ttu-id="8b196-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="8b196-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="8b196-111">Идентификатор типа субъекта.</span><span class="sxs-lookup"><span data-stu-id="8b196-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="8b196-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="8b196-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="8b196-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="8b196-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="8b196-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="8b196-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="8b196-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="8b196-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="8b196-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="8b196-116">bit, not null</span></span>  <br/> |<span data-ttu-id="8b196-117">Значение true, если тип соответствует субъектам, которые используются для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="8b196-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="8b196-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="8b196-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="8b196-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="8b196-119">bit, not null</span></span>  <br/> |<span data-ttu-id="8b196-120">Значение true, если тип соответствует пользователям.</span><span class="sxs-lookup"><span data-stu-id="8b196-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="8b196-121">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="8b196-121">**Key**</span></span>

|<span data-ttu-id="8b196-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8b196-122">**Column**</span></span>|<span data-ttu-id="8b196-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8b196-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8b196-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="8b196-124">ptypeID</span></span>  <br/> |<span data-ttu-id="8b196-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="8b196-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="8b196-126">**Значения субъектов**</span><span class="sxs-lookup"><span data-stu-id="8b196-126">**Principal Values**</span></span>

|<span data-ttu-id="8b196-127">**ИДЕНТИФИКАТОР**</span><span class="sxs-lookup"><span data-stu-id="8b196-127">**ID**</span></span>|<span data-ttu-id="8b196-128">**Role (Роль)**</span><span class="sxs-lookup"><span data-stu-id="8b196-128">**Role**</span></span>|<span data-ttu-id="8b196-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8b196-129">**Description**</span></span>|<span data-ttu-id="8b196-130">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="8b196-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b196-131">1</span><span class="sxs-lookup"><span data-stu-id="8b196-131">1</span></span>  <br/> |<span data-ttu-id="8b196-132">Любой</span><span class="sxs-lookup"><span data-stu-id="8b196-132">Any</span></span>  <br/> |<span data-ttu-id="8b196-133">Универсальный участника без известных типа.</span><span class="sxs-lookup"><span data-stu-id="8b196-133">Generic principal with no known type.</span></span> <span data-ttu-id="8b196-134">Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8b196-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="8b196-135">2</span><span class="sxs-lookup"><span data-stu-id="8b196-135">2</span></span>  <br/> |<span data-ttu-id="8b196-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="8b196-136">AnyUser</span></span>  <br/> |<span data-ttu-id="8b196-137">Универсальный участника пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="8b196-137">Generic principal of user type.</span></span> <span data-ttu-id="8b196-138">Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8b196-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="8b196-139">Да</span><span class="sxs-lookup"><span data-stu-id="8b196-139">Yes</span></span>  <br/> |
|<span data-ttu-id="8b196-140">3</span><span class="sxs-lookup"><span data-stu-id="8b196-140">3</span></span>  <br/> |<span data-ttu-id="8b196-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="8b196-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="8b196-142">Универсальный участника с группой семантических.</span><span class="sxs-lookup"><span data-stu-id="8b196-142">Generic principal with group semantic.</span></span> <span data-ttu-id="8b196-143">Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8b196-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="8b196-144">4</span><span class="sxs-lookup"><span data-stu-id="8b196-144">4</span></span>  <br/> |<span data-ttu-id="8b196-145">Системного пользователя</span><span class="sxs-lookup"><span data-stu-id="8b196-145">SystemUser</span></span>  <br/> |<span data-ttu-id="8b196-146">Используемое во внутренней сети с сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="8b196-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="8b196-147">5</span><span class="sxs-lookup"><span data-stu-id="8b196-147">5</span></span>  <br/> |<span data-ttu-id="8b196-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="8b196-148">User</span></span>  <br/> |<span data-ttu-id="8b196-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="8b196-149">Regular user.</span></span>  <br/> |<span data-ttu-id="8b196-150">Да</span><span class="sxs-lookup"><span data-stu-id="8b196-150">Yes</span></span>  <br/> |
|<span data-ttu-id="8b196-151">8</span><span class="sxs-lookup"><span data-stu-id="8b196-151">8</span></span>  <br/> |<span data-ttu-id="8b196-152">КОНТРОЛЛЕР ДОМЕНА</span><span class="sxs-lookup"><span data-stu-id="8b196-152">DC</span></span>  <br/> |<span data-ttu-id="8b196-153">Контроллер домена Active Directory доменных служб.</span><span class="sxs-lookup"><span data-stu-id="8b196-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="8b196-154">9</span><span class="sxs-lookup"><span data-stu-id="8b196-154">9</span></span>  <br/> |<span data-ttu-id="8b196-155">Группа</span><span class="sxs-lookup"><span data-stu-id="8b196-155">Group</span></span>  <br/> |<span data-ttu-id="8b196-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8b196-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="8b196-157">10</span><span class="sxs-lookup"><span data-stu-id="8b196-157">10</span></span>  <br/> |<span data-ttu-id="8b196-158">Папка</span><span class="sxs-lookup"><span data-stu-id="8b196-158">Folder</span></span>  <br/> |<span data-ttu-id="8b196-159">Active Directory контейнер или подразделение.</span><span class="sxs-lookup"><span data-stu-id="8b196-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="8b196-160">См. также</span><span class="sxs-lookup"><span data-stu-id="8b196-160">See also</span></span>

#### 

[<span data-ttu-id="8b196-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="8b196-161">tblPrincipal</span></span>](tblprincipal.md)

