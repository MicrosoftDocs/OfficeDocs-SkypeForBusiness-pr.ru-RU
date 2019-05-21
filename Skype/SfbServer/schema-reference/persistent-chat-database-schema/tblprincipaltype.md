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
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: ТблпринЦипалтипе содержит основные типы для классификации содержимого в таблице ТблпринЦипал.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295246"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="6c091-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="6c091-103">tblPrincipalType</span></span>
 
<span data-ttu-id="6c091-104">ТблпринЦипалтипе содержит основные типы для классификации содержимого в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="6c091-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="6c091-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="6c091-105">**Columns**</span></span>

|<span data-ttu-id="6c091-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6c091-106">**Column**</span></span>|<span data-ttu-id="6c091-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6c091-107">**Type**</span></span>|<span data-ttu-id="6c091-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6c091-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c091-109">Птипеид</span><span class="sxs-lookup"><span data-stu-id="6c091-109">ptypeID</span></span>  <br/> |<span data-ttu-id="6c091-110">smallint, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6c091-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="6c091-111">Идентификатор типа участника.</span><span class="sxs-lookup"><span data-stu-id="6c091-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="6c091-112">Птипедеск</span><span class="sxs-lookup"><span data-stu-id="6c091-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="6c091-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6c091-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="6c091-114">Описание типа.</span><span class="sxs-lookup"><span data-stu-id="6c091-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="6c091-115">Птипеиссистемусер</span><span class="sxs-lookup"><span data-stu-id="6c091-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="6c091-116">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6c091-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6c091-117">Значение true, если тип соответствует участникам, которые используются для внутренних целей.</span><span class="sxs-lookup"><span data-stu-id="6c091-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="6c091-118">Птипеисусер</span><span class="sxs-lookup"><span data-stu-id="6c091-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="6c091-119">bit, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6c091-119">bit, not null</span></span>  <br/> |<span data-ttu-id="6c091-120">Значение true, если тип является пользовательским типом.</span><span class="sxs-lookup"><span data-stu-id="6c091-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="6c091-121">**Ключ**</span><span class="sxs-lookup"><span data-stu-id="6c091-121">**Key**</span></span>

|<span data-ttu-id="6c091-122">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="6c091-122">**Column**</span></span>|<span data-ttu-id="6c091-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6c091-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c091-124">Птипеид</span><span class="sxs-lookup"><span data-stu-id="6c091-124">ptypeID</span></span>  <br/> |<span data-ttu-id="6c091-125">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="6c091-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="6c091-126">**Основные значения**</span><span class="sxs-lookup"><span data-stu-id="6c091-126">**Principal Values**</span></span>

|<span data-ttu-id="6c091-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="6c091-127">**ID**</span></span>|<span data-ttu-id="6c091-128">**Роль**</span><span class="sxs-lookup"><span data-stu-id="6c091-128">**Role**</span></span>|<span data-ttu-id="6c091-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6c091-129">**Description**</span></span>|<span data-ttu-id="6c091-130">**User**</span><span class="sxs-lookup"><span data-stu-id="6c091-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6c091-131">1</span><span class="sxs-lookup"><span data-stu-id="6c091-131">1</span></span>  <br/> |<span data-ttu-id="6c091-132">Любой</span><span class="sxs-lookup"><span data-stu-id="6c091-132">Any</span></span>  <br/> |<span data-ttu-id="6c091-133">Универсальный принципал без известного типа.</span><span class="sxs-lookup"><span data-stu-id="6c091-133">Generic principal with no known type.</span></span> <span data-ttu-id="6c091-134">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="6c091-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="6c091-135">2</span><span class="sxs-lookup"><span data-stu-id="6c091-135">2</span></span>  <br/> |<span data-ttu-id="6c091-136">Анюсер</span><span class="sxs-lookup"><span data-stu-id="6c091-136">AnyUser</span></span>  <br/> |<span data-ttu-id="6c091-137">Универсальный принципал для типа пользователя.</span><span class="sxs-lookup"><span data-stu-id="6c091-137">Generic principal of user type.</span></span> <span data-ttu-id="6c091-138">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="6c091-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="6c091-139">Да</span><span class="sxs-lookup"><span data-stu-id="6c091-139">Yes</span></span>  <br/> |
|<span data-ttu-id="6c091-140">3</span><span class="sxs-lookup"><span data-stu-id="6c091-140">3</span></span>  <br/> |<span data-ttu-id="6c091-141">Аниграуп</span><span class="sxs-lookup"><span data-stu-id="6c091-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="6c091-142">Универсальный принципал с семантикой группы.</span><span class="sxs-lookup"><span data-stu-id="6c091-142">Generic principal with group semantic.</span></span> <span data-ttu-id="6c091-143">Не используется в таблице ТблпринЦипал.</span><span class="sxs-lookup"><span data-stu-id="6c091-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="6c091-144">4</span><span class="sxs-lookup"><span data-stu-id="6c091-144">4</span></span>  <br/> |<span data-ttu-id="6c091-145">Системусер</span><span class="sxs-lookup"><span data-stu-id="6c091-145">SystemUser</span></span>  <br/> |<span data-ttu-id="6c091-146">Основной сервер, который используется для внутренних целей с помощью сохраняемого сервера чата.</span><span class="sxs-lookup"><span data-stu-id="6c091-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="6c091-147">5</span><span class="sxs-lookup"><span data-stu-id="6c091-147">5</span></span>  <br/> |<span data-ttu-id="6c091-148">Пользователь</span><span class="sxs-lookup"><span data-stu-id="6c091-148">User</span></span>  <br/> |<span data-ttu-id="6c091-149">Обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="6c091-149">Regular user.</span></span>  <br/> |<span data-ttu-id="6c091-150">Да</span><span class="sxs-lookup"><span data-stu-id="6c091-150">Yes</span></span>  <br/> |
|<span data-ttu-id="6c091-151">No8</span><span class="sxs-lookup"><span data-stu-id="6c091-151">8</span></span>  <br/> |<span data-ttu-id="6c091-152">NУДАЛЕННЫЙ</span><span class="sxs-lookup"><span data-stu-id="6c091-152">DC</span></span>  <br/> |<span data-ttu-id="6c091-153">Контроллер домена доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c091-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="6c091-154">@</span><span class="sxs-lookup"><span data-stu-id="6c091-154">9</span></span>  <br/> |<span data-ttu-id="6c091-155">Сгруппирован</span><span class="sxs-lookup"><span data-stu-id="6c091-155">Group</span></span>  <br/> |<span data-ttu-id="6c091-156">Группа безопасности Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c091-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="6c091-157">5-10</span><span class="sxs-lookup"><span data-stu-id="6c091-157">10</span></span>  <br/> |<span data-ttu-id="6c091-158">Нее</span><span class="sxs-lookup"><span data-stu-id="6c091-158">Folder</span></span>  <br/> |<span data-ttu-id="6c091-159">Контейнер Active Directory или подразделение.</span><span class="sxs-lookup"><span data-stu-id="6c091-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="6c091-160">См. также</span><span class="sxs-lookup"><span data-stu-id="6c091-160">See also</span></span>

[<span data-ttu-id="6c091-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="6c091-161">tblPrincipal</span></span>](tblprincipal.md)
