---
title: Таблица Клиентверсионс в Skype для бизнеса Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815407"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="524e1-104">Таблица Клиентверсионс в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="524e1-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="524e1-105">Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="524e1-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="524e1-106">Каждая запись в таблице представляет одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="524e1-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="524e1-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="524e1-107">**Column**</span></span>|<span data-ttu-id="524e1-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="524e1-108">**Data Type**</span></span>|<span data-ttu-id="524e1-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="524e1-109">**Key/Index**</span></span>|<span data-ttu-id="524e1-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="524e1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="524e1-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="524e1-111">**VersionId**</span></span> <br/> |<span data-ttu-id="524e1-112">**целое**</span><span class="sxs-lookup"><span data-stu-id="524e1-112">**int**</span></span> <br/> |<span data-ttu-id="524e1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="524e1-113">Primary</span></span>  <br/> |<span data-ttu-id="524e1-114">Уникальный номер, показывающий этот тип клиента и версию.</span><span class="sxs-lookup"><span data-stu-id="524e1-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="524e1-115">**Версия**</span><span class="sxs-lookup"><span data-stu-id="524e1-115">**Version**</span></span> <br/> |<span data-ttu-id="524e1-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="524e1-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="524e1-117">Название версии.</span><span class="sxs-lookup"><span data-stu-id="524e1-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="524e1-118">**клиенттипе**</span><span class="sxs-lookup"><span data-stu-id="524e1-118">**ClientType**</span></span> <br/> |<span data-ttu-id="524e1-119">целое</span><span class="sxs-lookup"><span data-stu-id="524e1-119">int</span></span>  <br/> ||<span data-ttu-id="524e1-120">Указывает тип клиента, используемого в сеансе.</span><span class="sxs-lookup"><span data-stu-id="524e1-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="524e1-121">Для получения дополнительных сведений ознакомьтесь с [таблицей усеражентдеф](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="524e1-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="524e1-122">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="524e1-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

