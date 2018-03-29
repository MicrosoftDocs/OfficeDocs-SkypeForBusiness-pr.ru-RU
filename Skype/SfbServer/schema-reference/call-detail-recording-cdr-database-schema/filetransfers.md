---
title: Представление FileTransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Просмотр FileTranfer сохранение информации о сеансах с передачей файлов peer-to-peer. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a><span data-ttu-id="8b203-104">Представление FileTransfers</span><span class="sxs-lookup"><span data-stu-id="8b203-104">FileTransfers view</span></span>
 
<span data-ttu-id="8b203-105">Просмотр FileTranfer сохранение информации о сеансах с передачей файлов peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="8b203-105">The FileTranfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="8b203-106">В этом представлении была введена в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b203-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b203-107">Представление FileTransfers содержит все столбцы [SessionDetails view](sessiondetails-0.md) в дополнение к этому столбцов, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="8b203-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="8b203-108">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="8b203-108">**Column**</span></span>|<span data-ttu-id="8b203-109">**Тип данных**</span><span class="sxs-lookup"><span data-stu-id="8b203-109">**Data Type**</span></span>|<span data-ttu-id="8b203-110">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="8b203-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b203-111">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="8b203-111">**FileName**</span></span> <br/> |<span data-ttu-id="8b203-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b203-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8b203-113">Имя файла, передан.</span><span class="sxs-lookup"><span data-stu-id="8b203-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="8b203-114">**Файл cookie**</span><span class="sxs-lookup"><span data-stu-id="8b203-114">**Cookie**</span></span> <br/> |<span data-ttu-id="8b203-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8b203-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="8b203-116">Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.</span><span class="sxs-lookup"><span data-stu-id="8b203-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="8b203-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="8b203-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="8b203-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="8b203-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="8b203-119">Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.</span><span class="sxs-lookup"><span data-stu-id="8b203-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="8b203-120">**Прием**</span><span class="sxs-lookup"><span data-stu-id="8b203-120">**Accept**</span></span> <br/> |<span data-ttu-id="8b203-121">бит</span><span class="sxs-lookup"><span data-stu-id="8b203-121">bit</span></span>  <br/> |<span data-ttu-id="8b203-122">Может быть значение TRUE или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="8b203-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="8b203-123">Если значение TRUE, затем Отклонить и Отмена будет NULL.</span><span class="sxs-lookup"><span data-stu-id="8b203-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="8b203-124">**Отклонение**</span><span class="sxs-lookup"><span data-stu-id="8b203-124">**Reject**</span></span> <br/> |<span data-ttu-id="8b203-125">бит</span><span class="sxs-lookup"><span data-stu-id="8b203-125">bit</span></span>  <br/> |<span data-ttu-id="8b203-126">Может быть значение TRUE или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="8b203-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="8b203-127">Если значение TRUE, затем принять и Отмена будет NULL.</span><span class="sxs-lookup"><span data-stu-id="8b203-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="8b203-128">**Отмена**.</span><span class="sxs-lookup"><span data-stu-id="8b203-128">**Cancel**</span></span> <br/> |<span data-ttu-id="8b203-129">бит</span><span class="sxs-lookup"><span data-stu-id="8b203-129">bit</span></span>  <br/> |<span data-ttu-id="8b203-130">Может быть значение TRUE или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="8b203-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="8b203-131">Если значение TRUE, то принятия и отклонения будет NULL.</span><span class="sxs-lookup"><span data-stu-id="8b203-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

