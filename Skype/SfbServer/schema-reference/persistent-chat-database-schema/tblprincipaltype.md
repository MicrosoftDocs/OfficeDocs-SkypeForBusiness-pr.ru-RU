---
title: tblPrincipalType
ms.reviewer: ''
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
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887439"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="720af-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="720af-103">tblPrincipalType</span></span>
 
<span data-ttu-id="720af-104">Таблица tblPrincipalType содержит типы субъектов для возможности в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="720af-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="720af-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="720af-105">**Columns**</span></span>

|<span data-ttu-id="720af-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="720af-106">**Column**</span></span>|<span data-ttu-id="720af-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="720af-107">**Type**</span></span>|<span data-ttu-id="720af-108">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="720af-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="720af-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="720af-109">ptypeID</span></span>  <br/> |<span data-ttu-id="720af-110">smallint, не может быть null</span><span class="sxs-lookup"><span data-stu-id="720af-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="720af-111">Идентификатор типа субъекта.</span><span class="sxs-lookup"><span data-stu-id="720af-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="720af-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="720af-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="720af-113">nvarchar (256), отлично от null</span><span class="sxs-lookup"><span data-stu-id="720af-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="720af-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="720af-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="720af-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="720af-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="720af-116">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="720af-116">bit, not null</span></span>  <br/> |<span data-ttu-id="720af-117">Значение true, если тип соответствует субъектам, которые используются для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="720af-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="720af-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="720af-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="720af-119">bit, не может быть null</span><span class="sxs-lookup"><span data-stu-id="720af-119">bit, not null</span></span>  <br/> |<span data-ttu-id="720af-120">Значение true, если тип соответствует пользователям.</span><span class="sxs-lookup"><span data-stu-id="720af-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="720af-121">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="720af-121">**Key**</span></span>

|<span data-ttu-id="720af-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="720af-122">**Column**</span></span>|<span data-ttu-id="720af-123">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="720af-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="720af-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="720af-124">ptypeID</span></span>  <br/> |<span data-ttu-id="720af-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="720af-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="720af-126">**Значения субъектов**</span><span class="sxs-lookup"><span data-stu-id="720af-126">**Principal Values**</span></span>

|<span data-ttu-id="720af-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="720af-127">**ID**</span></span>|<span data-ttu-id="720af-128">**Роль**</span><span class="sxs-lookup"><span data-stu-id="720af-128">**Role**</span></span>|<span data-ttu-id="720af-129">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="720af-129">**Description**</span></span>|<span data-ttu-id="720af-130">**User**</span><span class="sxs-lookup"><span data-stu-id="720af-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="720af-131">1</span><span class="sxs-lookup"><span data-stu-id="720af-131">1</span></span>  <br/> |<span data-ttu-id="720af-132">Любой</span><span class="sxs-lookup"><span data-stu-id="720af-132">Any</span></span>  <br/> |<span data-ttu-id="720af-133">Универсальный участника без известных типа.</span><span class="sxs-lookup"><span data-stu-id="720af-133">Generic principal with no known type.</span></span> <span data-ttu-id="720af-134">Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="720af-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="720af-135">2</span><span class="sxs-lookup"><span data-stu-id="720af-135">2</span></span>  <br/> |<span data-ttu-id="720af-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="720af-136">AnyUser</span></span>  <br/> |<span data-ttu-id="720af-137">Универсальный участника пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="720af-137">Generic principal of user type.</span></span> <span data-ttu-id="720af-138">Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="720af-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="720af-139">Да</span><span class="sxs-lookup"><span data-stu-id="720af-139">Yes</span></span>  <br/> |
|<span data-ttu-id="720af-140">3</span><span class="sxs-lookup"><span data-stu-id="720af-140">3</span></span>  <br/> |<span data-ttu-id="720af-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="720af-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="720af-142">Универсальный участника с группой семантических.</span><span class="sxs-lookup"><span data-stu-id="720af-142">Generic principal with group semantic.</span></span> <span data-ttu-id="720af-143">Не используется в таблице tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="720af-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="720af-144">4</span><span class="sxs-lookup"><span data-stu-id="720af-144">4</span></span>  <br/> |<span data-ttu-id="720af-145">Системного пользователя</span><span class="sxs-lookup"><span data-stu-id="720af-145">SystemUser</span></span>  <br/> |<span data-ttu-id="720af-146">Используемое во внутренней сети с сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="720af-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="720af-147">5</span><span class="sxs-lookup"><span data-stu-id="720af-147">5</span></span>  <br/> |<span data-ttu-id="720af-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="720af-148">User</span></span>  <br/> |<span data-ttu-id="720af-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="720af-149">Regular user.</span></span>  <br/> |<span data-ttu-id="720af-150">Да</span><span class="sxs-lookup"><span data-stu-id="720af-150">Yes</span></span>  <br/> |
|<span data-ttu-id="720af-151">8</span><span class="sxs-lookup"><span data-stu-id="720af-151">8</span></span>  <br/> |<span data-ttu-id="720af-152">КОНТРОЛЛЕР ДОМЕНА</span><span class="sxs-lookup"><span data-stu-id="720af-152">DC</span></span>  <br/> |<span data-ttu-id="720af-153">Контроллер домена Active Directory доменных служб.</span><span class="sxs-lookup"><span data-stu-id="720af-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="720af-154">9</span><span class="sxs-lookup"><span data-stu-id="720af-154">9</span></span>  <br/> |<span data-ttu-id="720af-155">Группа</span><span class="sxs-lookup"><span data-stu-id="720af-155">Group</span></span>  <br/> |<span data-ttu-id="720af-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="720af-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="720af-157">10</span><span class="sxs-lookup"><span data-stu-id="720af-157">10</span></span>  <br/> |<span data-ttu-id="720af-158">Папка</span><span class="sxs-lookup"><span data-stu-id="720af-158">Folder</span></span>  <br/> |<span data-ttu-id="720af-159">Active Directory контейнер или подразделение.</span><span class="sxs-lookup"><span data-stu-id="720af-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="720af-160">См. также</span><span class="sxs-lookup"><span data-stu-id="720af-160">See also</span></span>

[<span data-ttu-id="720af-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="720af-161">tblPrincipal</span></span>](tblprincipal.md)
