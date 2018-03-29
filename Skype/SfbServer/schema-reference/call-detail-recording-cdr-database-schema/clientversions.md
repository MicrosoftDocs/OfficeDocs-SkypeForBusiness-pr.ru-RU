---
title: Таблица ClientVersions в Скайп для Business Server 2015
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
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="018d9-104">Таблица ClientVersions в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="018d9-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="018d9-105">Таблица ClientVersions — собой вспомогательную таблицу, в которой хранится список различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных.</span><span class="sxs-lookup"><span data-stu-id="018d9-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="018d9-106">Каждая запись в таблице представляет одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="018d9-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="018d9-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="018d9-107">**Column**</span></span>|<span data-ttu-id="018d9-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="018d9-108">**Data Type**</span></span>|<span data-ttu-id="018d9-109">**Ключ или индекс**</span><span class="sxs-lookup"><span data-stu-id="018d9-109">**Key/Index**</span></span>|<span data-ttu-id="018d9-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="018d9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="018d9-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="018d9-111">**VersionId**</span></span> <br/> |<span data-ttu-id="018d9-112">**int**</span><span class="sxs-lookup"><span data-stu-id="018d9-112">**int**</span></span> <br/> |<span data-ttu-id="018d9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="018d9-113">Primary</span></span>  <br/> |<span data-ttu-id="018d9-114">Уникальный номер, идентифицирующий этот тип и версию клиента.</span><span class="sxs-lookup"><span data-stu-id="018d9-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="018d9-115">**Версия**</span><span class="sxs-lookup"><span data-stu-id="018d9-115">**Version**</span></span> <br/> |<span data-ttu-id="018d9-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="018d9-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="018d9-117">Название версии.</span><span class="sxs-lookup"><span data-stu-id="018d9-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="018d9-118">**Типа клиента**</span><span class="sxs-lookup"><span data-stu-id="018d9-118">**ClientType**</span></span> <br/> |<span data-ttu-id="018d9-119">целое</span><span class="sxs-lookup"><span data-stu-id="018d9-119">int</span></span>  <br/> ||<span data-ttu-id="018d9-120">Указывает тип клиента, используемая в сеансе.</span><span class="sxs-lookup"><span data-stu-id="018d9-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="018d9-121">[Таблица useragentdef](useragentdef.md) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="018d9-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="018d9-122">В этом поле было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="018d9-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

