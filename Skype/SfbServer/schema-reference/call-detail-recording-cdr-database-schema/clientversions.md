---
title: Таблица ClientVersions в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица ClientVersions — собой вспомогательную таблицу, в которой хранится список различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898531"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e6b9a-104">Таблица ClientVersions в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6b9a-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e6b9a-105">Таблица ClientVersions — собой вспомогательную таблицу, в которой хранится список различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e6b9a-106">Каждая запись в таблице представляет одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="e6b9a-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-107">**Column**</span></span>|<span data-ttu-id="e6b9a-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-108">**Data Type**</span></span>|<span data-ttu-id="e6b9a-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-109">**Key/Index**</span></span>|<span data-ttu-id="e6b9a-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6b9a-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-111">**VersionId**</span></span> <br/> |<span data-ttu-id="e6b9a-112">**целое**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-112">**int**</span></span> <br/> |<span data-ttu-id="e6b9a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e6b9a-113">Primary</span></span>  <br/> |<span data-ttu-id="e6b9a-114">Уникальный номер, идентифицирующий этот тип и версию клиента.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="e6b9a-115">**Версия**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-115">**Version**</span></span> <br/> |<span data-ttu-id="e6b9a-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="e6b9a-117">Название версии.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="e6b9a-118">**Типа клиента**</span><span class="sxs-lookup"><span data-stu-id="e6b9a-118">**ClientType**</span></span> <br/> |<span data-ttu-id="e6b9a-119">целое</span><span class="sxs-lookup"><span data-stu-id="e6b9a-119">int</span></span>  <br/> ||<span data-ttu-id="e6b9a-120">Указывает тип клиента, используемая в сеансе.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="e6b9a-121">[Таблица useragentdef](useragentdef.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="e6b9a-122">В этом поле было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6b9a-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

