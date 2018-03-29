---
title: Start-CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a><span data-ttu-id="fd743-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="fd743-103">Start-CcDownload</span></span>
 
<span data-ttu-id="fd743-104">Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="fd743-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="fd743-105">В Cloud Connector версии 2.0 и более поздних также можно задать параметр DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="fd743-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="fd743-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="fd743-106">Examples</span></span>
<span data-ttu-id="fd743-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fd743-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="fd743-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="fd743-108">Example 1</span></span>

<span data-ttu-id="fd743-109">Следующий пример файлы для загрузки bits облачных соединителя и msi-файл синхронно с сайта загрузки облака соединителя</span><span class="sxs-lookup"><span data-stu-id="fd743-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="fd743-110">Пример 2</span><span class="sxs-lookup"><span data-stu-id="fd743-110">Example 2</span></span>

<span data-ttu-id="fd743-111">Следующий пример файлы для загрузки bits облачных соединителя и msi-файл синхронно с сайта закрытый файл для загрузки</span><span class="sxs-lookup"><span data-stu-id="fd743-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="fd743-112">Пример 3</span><span class="sxs-lookup"><span data-stu-id="fd743-112">Example 3</span></span>

<span data-ttu-id="fd743-113">В третьем примере синхронно скачиваются файлы BITS и MSI Cloud Connector с закрытого сайта для скачивания.</span><span class="sxs-lookup"><span data-stu-id="fd743-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="fd743-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="fd743-114">Detailed Description</span></span>
<span data-ttu-id="fd743-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fd743-115"></span></span>

<span data-ttu-id="fd743-116">При наличии новой версии доступны в узле загрузки, Start-CcDownload загрузить и установить msi-файл с сайта загрузки и синхронно Загрузите бит облачных соединителя.</span><span class="sxs-lookup"><span data-stu-id="fd743-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="fd743-117">Если новая версия MSI-файла отсутствует, командлет Start-CcDownload скачает только BITS-файл Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fd743-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="fd743-118">Если BITS-файл Cloud Connector уже скачан, командлет Start-CcDownload не выполняется.</span><span class="sxs-lookup"><span data-stu-id="fd743-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fd743-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd743-119">Parameters</span></span>
<span data-ttu-id="fd743-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fd743-120"></span></span>

|<span data-ttu-id="fd743-121">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="fd743-121">**Parameter**</span></span>|<span data-ttu-id="fd743-122">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="fd743-122">**Required**</span></span>|<span data-ttu-id="fd743-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="fd743-123">**Type**</span></span>|<span data-ttu-id="fd743-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fd743-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd743-125">DownloadUrlRoot</span><span class="sxs-lookup"><span data-stu-id="fd743-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="fd743-126"> Необязательно</span><span class="sxs-lookup"><span data-stu-id="fd743-126">Optional</span></span> <br/> |<span data-ttu-id="fd743-127">System.String</span><span class="sxs-lookup"><span data-stu-id="fd743-127">System.String</span></span>  <br/> | <span data-ttu-id="fd743-128">Полный URL-адрес определенной версии соединителя облака в частном Загрузите сайта.</span><span class="sxs-lookup"><span data-stu-id="fd743-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="fd743-129">Используйте этот параметр с осторожностью, убедитесь, что для загрузки версии облачных соединителя.</span><span class="sxs-lookup"><span data-stu-id="fd743-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="fd743-130">DownloadBitsOnly</span><span class="sxs-lookup"><span data-stu-id="fd743-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="fd743-131">Необязательно </span><span class="sxs-lookup"><span data-stu-id="fd743-131">Optional</span></span>  <br/> |<span data-ttu-id="fd743-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="fd743-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="fd743-133">Пропустите скачивание и установку MSI-файла с сайта для скачивания. Скачайте только BITS-файл Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fd743-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fd743-134">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="fd743-134">Input Types</span></span>
<span data-ttu-id="fd743-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fd743-135"></span></span>

<span data-ttu-id="fd743-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="fd743-136">None.</span></span> <span data-ttu-id="fd743-137">Командлет Start-CcDownload не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fd743-137">The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fd743-138">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="fd743-138">Return Types</span></span>
<span data-ttu-id="fd743-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fd743-139"></span></span>

<span data-ttu-id="fd743-140">Нет</span><span class="sxs-lookup"><span data-stu-id="fd743-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fd743-141">См. также</span><span class="sxs-lookup"><span data-stu-id="fd743-141">See also</span></span>
<span data-ttu-id="fd743-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fd743-142"></span></span>

<span data-ttu-id="fd743-143">Нет</span><span class="sxs-lookup"><span data-stu-id="fd743-143">None</span></span>
  

