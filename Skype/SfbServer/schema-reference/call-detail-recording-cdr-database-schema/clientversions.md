---
title: Таблица ClientVersions в Skype для бизнеса Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813319"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="72a5c-104">Таблица ClientVersions в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="72a5c-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="72a5c-p102">Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="72a5c-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="72a5c-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="72a5c-107">**Column**</span></span>|<span data-ttu-id="72a5c-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="72a5c-108">**Data Type**</span></span>|<span data-ttu-id="72a5c-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="72a5c-109">**Key/Index**</span></span>|<span data-ttu-id="72a5c-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="72a5c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72a5c-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="72a5c-111">**VersionId**</span></span> <br/> |<span data-ttu-id="72a5c-112">**int**</span><span class="sxs-lookup"><span data-stu-id="72a5c-112">**int**</span></span> <br/> |<span data-ttu-id="72a5c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="72a5c-113">Primary</span></span>  <br/> |<span data-ttu-id="72a5c-114">Уникальный номер, идентифицирующий данный тип и версию клиента.</span><span class="sxs-lookup"><span data-stu-id="72a5c-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="72a5c-115">**Версия**</span><span class="sxs-lookup"><span data-stu-id="72a5c-115">**Version**</span></span> <br/> |<span data-ttu-id="72a5c-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="72a5c-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="72a5c-117">Название версии.</span><span class="sxs-lookup"><span data-stu-id="72a5c-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="72a5c-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="72a5c-118">**ClientType**</span></span> <br/> |<span data-ttu-id="72a5c-119">int</span><span class="sxs-lookup"><span data-stu-id="72a5c-119">int</span></span>  <br/> ||<span data-ttu-id="72a5c-120">Указывает тип клиента, используемого в этом сеансе.</span><span class="sxs-lookup"><span data-stu-id="72a5c-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="72a5c-121">Дополнительные сведения см. в таблице [UserAgentDef.](useragentdef.md)</span><span class="sxs-lookup"><span data-stu-id="72a5c-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="72a5c-122">Это поле было впервые введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72a5c-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

