---
title: Представление Филетрансферс
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: В представлении Филетрансфер хранятся сведения о одноранговых сеансах передачи файлов. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296240"
---
# <a name="filetransfers-view"></a><span data-ttu-id="98a96-104">Представление Филетрансферс</span><span class="sxs-lookup"><span data-stu-id="98a96-104">FileTransfers view</span></span>
 
<span data-ttu-id="98a96-105">В представлении Филетрансфер хранятся сведения о одноранговых сеансах передачи файлов.</span><span class="sxs-lookup"><span data-stu-id="98a96-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="98a96-106">Это представление было представлено в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="98a96-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98a96-107">В представлении Филетрансферс содержатся все столбцы в [представлении "сессиондетаилс](sessiondetails-0.md) " в дополнение к столбцам, перечисленным ниже.</span><span class="sxs-lookup"><span data-stu-id="98a96-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="98a96-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="98a96-108">**Column**</span></span>|<span data-ttu-id="98a96-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="98a96-109">**Data Type**</span></span>|<span data-ttu-id="98a96-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="98a96-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98a96-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="98a96-111">**FileName**</span></span> <br/> |<span data-ttu-id="98a96-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="98a96-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="98a96-113">Имя перенесенного файла.</span><span class="sxs-lookup"><span data-stu-id="98a96-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="98a96-114">**Файлах**</span><span class="sxs-lookup"><span data-stu-id="98a96-114">**Cookie**</span></span> <br/> |<span data-ttu-id="98a96-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="98a96-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="98a96-116">Используется для идентификации каждого сообщения к исполнению, связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="98a96-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="98a96-117">**Филеидентити**</span><span class="sxs-lookup"><span data-stu-id="98a96-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="98a96-118">идентификатора</span><span class="sxs-lookup"><span data-stu-id="98a96-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="98a96-119">Уникальный идентификатор, позволяющий отличать передачу файлов с одним и тем же именем файла.</span><span class="sxs-lookup"><span data-stu-id="98a96-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="98a96-120">**Отвечать**</span><span class="sxs-lookup"><span data-stu-id="98a96-120">**Accept**</span></span> <br/> |<span data-ttu-id="98a96-121">бит</span><span class="sxs-lookup"><span data-stu-id="98a96-121">bit</span></span>  <br/> |<span data-ttu-id="98a96-122">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="98a96-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="98a96-123">Если значение равно TRUE, то значение "отклонить" и "Отмена" будет равно NULL.</span><span class="sxs-lookup"><span data-stu-id="98a96-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="98a96-124">**Отклонил**</span><span class="sxs-lookup"><span data-stu-id="98a96-124">**Reject**</span></span> <br/> |<span data-ttu-id="98a96-125">бит</span><span class="sxs-lookup"><span data-stu-id="98a96-125">bit</span></span>  <br/> |<span data-ttu-id="98a96-126">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="98a96-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="98a96-127">Если значение равно TRUE, то "принимать" и "Отмена" будут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="98a96-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="98a96-128">**Отмена**.</span><span class="sxs-lookup"><span data-stu-id="98a96-128">**Cancel**</span></span> <br/> |<span data-ttu-id="98a96-129">бит</span><span class="sxs-lookup"><span data-stu-id="98a96-129">bit</span></span>  <br/> |<span data-ttu-id="98a96-130">Может иметь значение истина или NULL.</span><span class="sxs-lookup"><span data-stu-id="98a96-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="98a96-131">Если значение равно TRUE, то принять и отклонить будет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="98a96-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

