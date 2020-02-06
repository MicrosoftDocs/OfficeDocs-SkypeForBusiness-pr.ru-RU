---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Тблластинвитеид — это последний идентификатор приглашения, созданный (и использованный в таблице ТблпринЦипалинвитес) для каждого пользователя.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814577"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="9c8c2-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="9c8c2-103">tblLastInviteId</span></span>
 
<span data-ttu-id="9c8c2-104">Тблластинвитеид — это последний идентификатор приглашения, созданный (и использованный в таблице ТблпринЦипалинвитес) для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9c8c2-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="9c8c2-105">**Столбцов**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-105">**Columns**</span></span>

|<span data-ttu-id="9c8c2-106">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-106">**Column**</span></span>|<span data-ttu-id="9c8c2-107">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-107">**Type**</span></span>|<span data-ttu-id="9c8c2-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c8c2-109">принид</span><span class="sxs-lookup"><span data-stu-id="9c8c2-109">prinID</span></span>  <br/> |<span data-ttu-id="9c8c2-110">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9c8c2-110">int, not null</span></span>  <br/> |<span data-ttu-id="9c8c2-111">Идентификатор участника.</span><span class="sxs-lookup"><span data-stu-id="9c8c2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9c8c2-112">ластинвитеид</span><span class="sxs-lookup"><span data-stu-id="9c8c2-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="9c8c2-113">int, NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9c8c2-113">int, not null</span></span>  <br/> |<span data-ttu-id="9c8c2-114">Идентификатор приглашения последнего использован.</span><span class="sxs-lookup"><span data-stu-id="9c8c2-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="9c8c2-115">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-115">**Keys**</span></span>

|<span data-ttu-id="9c8c2-116">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-116">**Column**</span></span>|<span data-ttu-id="9c8c2-117">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9c8c2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9c8c2-118">принид</span><span class="sxs-lookup"><span data-stu-id="9c8c2-118">prinID</span></span>  <br/> |<span data-ttu-id="9c8c2-119">Первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="9c8c2-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9c8c2-120">принид</span><span class="sxs-lookup"><span data-stu-id="9c8c2-120">prinID</span></span>  <br/> |<span data-ttu-id="9c8c2-121">Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.</span><span class="sxs-lookup"><span data-stu-id="9c8c2-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9c8c2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9c8c2-122">See also</span></span>

[<span data-ttu-id="9c8c2-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="9c8c2-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
