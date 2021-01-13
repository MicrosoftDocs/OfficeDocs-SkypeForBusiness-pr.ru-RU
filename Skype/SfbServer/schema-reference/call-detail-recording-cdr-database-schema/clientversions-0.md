---
title: Представление ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: В представлении ClientVersions сохраняются сведения о различных типах клиентов и версиях, которые участвовали в сеансах, зарегистрированных в базе данных. Каждая запись в этом представлении относится к одной версии клиента. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813359"
---
# <a name="clientversions-view"></a><span data-ttu-id="74ca9-105">Представление ClientVersions</span><span class="sxs-lookup"><span data-stu-id="74ca9-105">ClientVersions view</span></span>
 
<span data-ttu-id="74ca9-106">В представлении ClientVersions сохраняются сведения о различных типах клиентов и версиях, которые участвовали в сеансах, зарегистрированных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="74ca9-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="74ca9-107">Каждая запись в этом представлении относится к одной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="74ca9-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="74ca9-108">Это представление впервые было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74ca9-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74ca9-109">Возможно наличие нескольких записей для определенных столбцов.</span><span class="sxs-lookup"><span data-stu-id="74ca9-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="74ca9-110">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="74ca9-110">**Column**</span></span>|<span data-ttu-id="74ca9-111">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="74ca9-111">**Data Type**</span></span>|<span data-ttu-id="74ca9-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="74ca9-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="74ca9-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="74ca9-113">**VersionId**</span></span> <br/> |<span data-ttu-id="74ca9-114">int</span><span class="sxs-lookup"><span data-stu-id="74ca9-114">int</span></span>  <br/> |<span data-ttu-id="74ca9-115">Уникальный номер, идентифицирующий данный тип клиента и его версию.</span><span class="sxs-lookup"><span data-stu-id="74ca9-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="74ca9-116">**Версия**</span><span class="sxs-lookup"><span data-stu-id="74ca9-116">**Version**</span></span> <br/> |<span data-ttu-id="74ca9-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="74ca9-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="74ca9-118">Служит для указания агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="74ca9-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="74ca9-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="74ca9-119">**ClientType**</span></span> <br/> |<span data-ttu-id="74ca9-120">int</span><span class="sxs-lookup"><span data-stu-id="74ca9-120">int</span></span>  <br/> |<span data-ttu-id="74ca9-121">Тип клиента.</span><span class="sxs-lookup"><span data-stu-id="74ca9-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="74ca9-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="74ca9-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="74ca9-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="74ca9-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="74ca9-p103">Категория, к которой относится клиент. Например, клиент Conferencing_Attendant_1.0 относится к категории ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="74ca9-p103">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

