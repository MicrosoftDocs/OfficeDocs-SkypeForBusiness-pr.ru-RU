---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504854"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="ea68d-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="ea68d-103">tblLastInviteId</span></span>
 
<span data-ttu-id="ea68d-104">Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ea68d-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="ea68d-105">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="ea68d-105">**Columns**</span></span>

|<span data-ttu-id="ea68d-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ea68d-106">**Column**</span></span>|<span data-ttu-id="ea68d-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ea68d-107">**Type**</span></span>|<span data-ttu-id="ea68d-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ea68d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea68d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ea68d-109">prinID</span></span>  <br/> |<span data-ttu-id="ea68d-110">int, не null</span><span class="sxs-lookup"><span data-stu-id="ea68d-110">int, not null</span></span>  <br/> |<span data-ttu-id="ea68d-111">Идентификатор субъекта.</span><span class="sxs-lookup"><span data-stu-id="ea68d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ea68d-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="ea68d-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="ea68d-113">int, не null</span><span class="sxs-lookup"><span data-stu-id="ea68d-113">int, not null</span></span>  <br/> |<span data-ttu-id="ea68d-114">Последний использованный код приглашения.</span><span class="sxs-lookup"><span data-stu-id="ea68d-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="ea68d-115">**Ключи**</span><span class="sxs-lookup"><span data-stu-id="ea68d-115">**Keys**</span></span>

|<span data-ttu-id="ea68d-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="ea68d-116">**Column**</span></span>|<span data-ttu-id="ea68d-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ea68d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea68d-118">prinID</span><span class="sxs-lookup"><span data-stu-id="ea68d-118">prinID</span></span>  <br/> |<span data-ttu-id="ea68d-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="ea68d-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ea68d-120">prinID</span><span class="sxs-lookup"><span data-stu-id="ea68d-120">prinID</span></span>  <br/> |<span data-ttu-id="ea68d-121">Внешний ключ с подстановкой в таблице tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ea68d-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ea68d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ea68d-122">See also</span></span>

[<span data-ttu-id="ea68d-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="ea68d-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)