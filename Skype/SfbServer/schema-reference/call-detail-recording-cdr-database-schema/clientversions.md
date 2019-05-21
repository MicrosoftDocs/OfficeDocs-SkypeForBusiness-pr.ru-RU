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
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296513"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8ace2-104">Таблица Клиентверсионс в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="8ace2-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8ace2-105">Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8ace2-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8ace2-106">Каждая запись в таблице представляет одну версию клиента.</span><span class="sxs-lookup"><span data-stu-id="8ace2-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="8ace2-107">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8ace2-107">**Column**</span></span>|<span data-ttu-id="8ace2-108">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8ace2-108">**Data Type**</span></span>|<span data-ttu-id="8ace2-109">**Ключ/индекс**</span><span class="sxs-lookup"><span data-stu-id="8ace2-109">**Key/Index**</span></span>|<span data-ttu-id="8ace2-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8ace2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ace2-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="8ace2-111">**VersionId**</span></span> <br/> |<span data-ttu-id="8ace2-112">**целое**</span><span class="sxs-lookup"><span data-stu-id="8ace2-112">**int**</span></span> <br/> |<span data-ttu-id="8ace2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8ace2-113">Primary</span></span>  <br/> |<span data-ttu-id="8ace2-114">Уникальный номер, показывающий этот тип клиента и версию.</span><span class="sxs-lookup"><span data-stu-id="8ace2-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="8ace2-115">**Версия**</span><span class="sxs-lookup"><span data-stu-id="8ace2-115">**Version**</span></span> <br/> |<span data-ttu-id="8ace2-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="8ace2-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="8ace2-117">Название версии.</span><span class="sxs-lookup"><span data-stu-id="8ace2-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="8ace2-118">**Клиенттипе**</span><span class="sxs-lookup"><span data-stu-id="8ace2-118">**ClientType**</span></span> <br/> |<span data-ttu-id="8ace2-119">целое</span><span class="sxs-lookup"><span data-stu-id="8ace2-119">int</span></span>  <br/> ||<span data-ttu-id="8ace2-120">Указывает тип клиента, используемого в сеансе.</span><span class="sxs-lookup"><span data-stu-id="8ace2-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="8ace2-121">Для получения дополнительных сведений ознакомьтесь с [таблицей усеражентдеф](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="8ace2-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="8ace2-122">Это поле было введено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ace2-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

