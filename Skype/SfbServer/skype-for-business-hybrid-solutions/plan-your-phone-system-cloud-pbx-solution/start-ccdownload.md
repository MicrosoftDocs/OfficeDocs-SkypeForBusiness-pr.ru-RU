---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824183"
---
# <a name="start-ccdownload"></a><span data-ttu-id="d61d7-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="d61d7-103">Start-CcDownload</span></span>
 
<span data-ttu-id="d61d7-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span><span class="sxs-lookup"><span data-stu-id="d61d7-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="d61d7-105">В Cloud Connector версии 2.0 и более поздних версий можно также указать параметр DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="d61d7-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="d61d7-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="d61d7-106">Examples</span></span>
<span data-ttu-id="d61d7-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d61d7-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d61d7-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d61d7-108">Example 1</span></span>

<span data-ttu-id="d61d7-109">В следующем примере синхронно загружаются биты Cloud Connector и MSI-файл с общего сайта загрузки Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="d61d7-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="d61d7-110">Пример 2</span><span class="sxs-lookup"><span data-stu-id="d61d7-110">Example 2</span></span>

<span data-ttu-id="d61d7-111">Следующий пример синхронно скачивает биты Cloud Connector и MSI-файл с частного сайта загрузки:</span><span class="sxs-lookup"><span data-stu-id="d61d7-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="d61d7-112">Пример 3</span><span class="sxs-lookup"><span data-stu-id="d61d7-112">Example 3</span></span>

<span data-ttu-id="d61d7-113">Третий пример синхронно скачивает биты Cloud Connector и MSI-файл с частного сайта для скачивания.</span><span class="sxs-lookup"><span data-stu-id="d61d7-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="d61d7-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d61d7-114">Detailed Description</span></span>
<span data-ttu-id="d61d7-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d61d7-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d61d7-116">Если на сайте загрузки доступна новая версия, Start-CcDownload скачивает и устанавливает MSI-файл с сайта загрузки, а затем синхронно скачивает биты Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d61d7-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="d61d7-117">Если новая версия MSI-файла не существует, Start-CcDownload скачать только биты Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d61d7-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="d61d7-118">Если биты Cloud Connector уже загружены, Start-CcDownload не выполняется.</span><span class="sxs-lookup"><span data-stu-id="d61d7-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d61d7-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="d61d7-119">Parameters</span></span>
<span data-ttu-id="d61d7-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d61d7-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="d61d7-121">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="d61d7-121">**Parameter**</span></span>|<span data-ttu-id="d61d7-122">**Required**</span><span class="sxs-lookup"><span data-stu-id="d61d7-122">**Required**</span></span>|<span data-ttu-id="d61d7-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d61d7-123">**Type**</span></span>|<span data-ttu-id="d61d7-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d61d7-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d61d7-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="d61d7-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="d61d7-126">Необязательный</span><span class="sxs-lookup"><span data-stu-id="d61d7-126">Optional</span></span> <br/> |<span data-ttu-id="d61d7-127">System.String</span><span class="sxs-lookup"><span data-stu-id="d61d7-127">System.String</span></span>  <br/> | <span data-ttu-id="d61d7-128">Полный URL-адрес определенной версии Cloud Connector на частном сайте загрузки.</span><span class="sxs-lookup"><span data-stu-id="d61d7-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="d61d7-129">Используйте этот параметр с осторожностью— убедитесь, что вы знаете, какую версию Cloud Connector вы скачиваете.</span><span class="sxs-lookup"><span data-stu-id="d61d7-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="d61d7-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="d61d7-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="d61d7-131">Необязательный</span><span class="sxs-lookup"><span data-stu-id="d61d7-131">Optional</span></span>  <br/> |<span data-ttu-id="d61d7-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d61d7-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d61d7-133">Пропустите этот шаг, чтобы скачать и установить MSI с сайта загрузки, скачайте только биты Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d61d7-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d61d7-134">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="d61d7-134">Input Types</span></span>
<span data-ttu-id="d61d7-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d61d7-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d61d7-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="d61d7-136">None.</span></span> <span data-ttu-id="d61d7-137">Этот Start-CcDownload не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="d61d7-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d61d7-138">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d61d7-138">Return Types</span></span>
<span data-ttu-id="d61d7-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d61d7-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d61d7-140">Нет</span><span class="sxs-lookup"><span data-stu-id="d61d7-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d61d7-141">См. также</span><span class="sxs-lookup"><span data-stu-id="d61d7-141">See also</span></span>
<span data-ttu-id="d61d7-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d61d7-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d61d7-143">Нет</span><span class="sxs-lookup"><span data-stu-id="d61d7-143">None</span></span>
  

