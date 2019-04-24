---
title: Представление FileTransfers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Просмотр FileTransfer сохранение информации о сеансах с передачей файлов peer-to-peer. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213090"
---
# <a name="filetransfers-view"></a><span data-ttu-id="f8abe-104">Представление FileTransfers</span><span class="sxs-lookup"><span data-stu-id="f8abe-104">FileTransfers view</span></span>
 
<span data-ttu-id="f8abe-105">Просмотр FileTransfer сохранение информации о сеансах с передачей файлов peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f8abe-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="f8abe-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8abe-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8abe-107">Представление FileTransfers содержит все столбцы [SessionDetails view](sessiondetails-0.md) в дополнение к этому столбцов, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="f8abe-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="f8abe-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="f8abe-108">**Column**</span></span>|<span data-ttu-id="f8abe-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="f8abe-109">**Data Type**</span></span>|<span data-ttu-id="f8abe-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="f8abe-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f8abe-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="f8abe-111">**FileName**</span></span> <br/> |<span data-ttu-id="f8abe-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f8abe-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f8abe-113">Имя файла, передан.</span><span class="sxs-lookup"><span data-stu-id="f8abe-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="f8abe-114">**Файл cookie**</span><span class="sxs-lookup"><span data-stu-id="f8abe-114">**Cookie**</span></span> <br/> |<span data-ttu-id="f8abe-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="f8abe-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="f8abe-116">Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="f8abe-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="f8abe-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="f8abe-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="f8abe-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="f8abe-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="f8abe-119">Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.</span><span class="sxs-lookup"><span data-stu-id="f8abe-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="f8abe-120">**Прием**</span><span class="sxs-lookup"><span data-stu-id="f8abe-120">**Accept**</span></span> <br/> |<span data-ttu-id="f8abe-121">бит</span><span class="sxs-lookup"><span data-stu-id="f8abe-121">bit</span></span>  <br/> |<span data-ttu-id="f8abe-122">Может быть значение TRUE или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f8abe-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="f8abe-123">Если значение TRUE, затем Отклонить и Отмена будет NULL.</span><span class="sxs-lookup"><span data-stu-id="f8abe-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f8abe-124">**Отклонение**</span><span class="sxs-lookup"><span data-stu-id="f8abe-124">**Reject**</span></span> <br/> |<span data-ttu-id="f8abe-125">бит</span><span class="sxs-lookup"><span data-stu-id="f8abe-125">bit</span></span>  <br/> |<span data-ttu-id="f8abe-126">Может быть значение TRUE или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f8abe-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="f8abe-127">Если значение TRUE, затем принять и Отмена будет NULL.</span><span class="sxs-lookup"><span data-stu-id="f8abe-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f8abe-128">**Отмена**.</span><span class="sxs-lookup"><span data-stu-id="f8abe-128">**Cancel**</span></span> <br/> |<span data-ttu-id="f8abe-129">бит</span><span class="sxs-lookup"><span data-stu-id="f8abe-129">bit</span></span>  <br/> |<span data-ttu-id="f8abe-130">Может быть значение TRUE или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="f8abe-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="f8abe-131">Если значение TRUE, то принятия и отклонения будет NULL.</span><span class="sxs-lookup"><span data-stu-id="f8abe-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

