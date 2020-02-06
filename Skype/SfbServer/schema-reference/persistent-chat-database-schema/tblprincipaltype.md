---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: ТблпринЦипалтипе содержит основные типы для классификации содержимого в таблице ТблпринЦипал.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812937"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="32898-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="32898-103">tblPrincipalType</span></span>
 
<span data-ttu-id="32898-104">ТблпринЦипалтипе содержит основные типы для классификации содержимого в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="32898-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="32898-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="32898-105">**Columns**</span></span>

|<span data-ttu-id="32898-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="32898-106">**Column**</span></span>|<span data-ttu-id="32898-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="32898-107">**Type**</span></span>|<span data-ttu-id="32898-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="32898-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32898-109">птипеид</span><span class="sxs-lookup"><span data-stu-id="32898-109">ptypeID</span></span>  <br/> |<span data-ttu-id="32898-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="32898-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="32898-111">Идентификатор типа участника.</span><span class="sxs-lookup"><span data-stu-id="32898-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="32898-112">птипедеск</span><span class="sxs-lookup"><span data-stu-id="32898-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="32898-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="32898-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="32898-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="32898-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="32898-115">птипеиссистемусер</span><span class="sxs-lookup"><span data-stu-id="32898-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="32898-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="32898-116">bit, not null</span></span>  <br/> |<span data-ttu-id="32898-117">Значение true, если тип соответствует участникам, которые используются для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="32898-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="32898-118">птипеисусер</span><span class="sxs-lookup"><span data-stu-id="32898-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="32898-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="32898-119">bit, not null</span></span>  <br/> |<span data-ttu-id="32898-120">Значение true, если тип является пользовательским типом.</span><span class="sxs-lookup"><span data-stu-id="32898-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="32898-121">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="32898-121">**Key**</span></span>

|<span data-ttu-id="32898-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="32898-122">**Column**</span></span>|<span data-ttu-id="32898-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="32898-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="32898-124">птипеид</span><span class="sxs-lookup"><span data-stu-id="32898-124">ptypeID</span></span>  <br/> |<span data-ttu-id="32898-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="32898-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="32898-126">**Основные значения**</span><span class="sxs-lookup"><span data-stu-id="32898-126">**Principal Values**</span></span>

|<span data-ttu-id="32898-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="32898-127">**ID**</span></span>|<span data-ttu-id="32898-128">**Роль**</span><span class="sxs-lookup"><span data-stu-id="32898-128">**Role**</span></span>|<span data-ttu-id="32898-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="32898-129">**Description**</span></span>|<span data-ttu-id="32898-130">**User**</span><span class="sxs-lookup"><span data-stu-id="32898-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32898-131">1</span><span class="sxs-lookup"><span data-stu-id="32898-131">1</span></span>  <br/> |<span data-ttu-id="32898-132">Любой</span><span class="sxs-lookup"><span data-stu-id="32898-132">Any</span></span>  <br/> |<span data-ttu-id="32898-133">Универсальный принципал без известного типа.</span><span class="sxs-lookup"><span data-stu-id="32898-133">Generic principal with no known type.</span></span> <span data-ttu-id="32898-134">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="32898-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="32898-135">2</span><span class="sxs-lookup"><span data-stu-id="32898-135">2</span></span>  <br/> |<span data-ttu-id="32898-136">анюсер</span><span class="sxs-lookup"><span data-stu-id="32898-136">AnyUser</span></span>  <br/> |<span data-ttu-id="32898-137">Универсальный принципал для типа пользователя.</span><span class="sxs-lookup"><span data-stu-id="32898-137">Generic principal of user type.</span></span> <span data-ttu-id="32898-138">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="32898-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="32898-139">Да</span><span class="sxs-lookup"><span data-stu-id="32898-139">Yes</span></span>  <br/> |
|<span data-ttu-id="32898-140">3</span><span class="sxs-lookup"><span data-stu-id="32898-140">3</span></span>  <br/> |<span data-ttu-id="32898-141">аниграуп</span><span class="sxs-lookup"><span data-stu-id="32898-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="32898-142">Универсальный принципал с семантикой группы.</span><span class="sxs-lookup"><span data-stu-id="32898-142">Generic principal with group semantic.</span></span> <span data-ttu-id="32898-143">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="32898-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="32898-144">4</span><span class="sxs-lookup"><span data-stu-id="32898-144">4</span></span>  <br/> |<span data-ttu-id="32898-145">системусер</span><span class="sxs-lookup"><span data-stu-id="32898-145">SystemUser</span></span>  <br/> |<span data-ttu-id="32898-146">Основной сервер, который используется для внутренних целей с помощью сохраняемого сервера чата.</span><span class="sxs-lookup"><span data-stu-id="32898-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="32898-147">5</span><span class="sxs-lookup"><span data-stu-id="32898-147">5</span></span>  <br/> |<span data-ttu-id="32898-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="32898-148">User</span></span>  <br/> |<span data-ttu-id="32898-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="32898-149">Regular user.</span></span>  <br/> |<span data-ttu-id="32898-150">Да</span><span class="sxs-lookup"><span data-stu-id="32898-150">Yes</span></span>  <br/> |
|<span data-ttu-id="32898-151">No8</span><span class="sxs-lookup"><span data-stu-id="32898-151">8</span></span>  <br/> |<span data-ttu-id="32898-152">NУДАЛЕННЫЙ</span><span class="sxs-lookup"><span data-stu-id="32898-152">DC</span></span>  <br/> |<span data-ttu-id="32898-153">Контроллер домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32898-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="32898-154">@</span><span class="sxs-lookup"><span data-stu-id="32898-154">9</span></span>  <br/> |<span data-ttu-id="32898-155">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="32898-155">Group</span></span>  <br/> |<span data-ttu-id="32898-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32898-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="32898-157">5-10</span><span class="sxs-lookup"><span data-stu-id="32898-157">10</span></span>  <br/> |<span data-ttu-id="32898-158">Нее</span><span class="sxs-lookup"><span data-stu-id="32898-158">Folder</span></span>  <br/> |<span data-ttu-id="32898-159">Контейнер Active Directory или подразделение.</span><span class="sxs-lookup"><span data-stu-id="32898-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="32898-160">См. также</span><span class="sxs-lookup"><span data-stu-id="32898-160">See also</span></span>

[<span data-ttu-id="32898-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="32898-161">tblPrincipal</span></span>](tblprincipal.md)
