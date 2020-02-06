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
description: Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824183"
---
# <a name="start-ccdownload"></a><span data-ttu-id="f3118-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="f3118-103">Start-CcDownload</span></span>
 
<span data-ttu-id="f3118-104">Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="f3118-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="f3118-105">В Cloud Connector версии 2.0 и более поздних также можно задать параметр DownloadBitsOnly.</span><span class="sxs-lookup"><span data-stu-id="f3118-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="f3118-106">Примеры</span><span class="sxs-lookup"><span data-stu-id="f3118-106">Examples</span></span>
<span data-ttu-id="f3118-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f3118-107"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="f3118-108">Пример 1</span><span class="sxs-lookup"><span data-stu-id="f3118-108">Example 1</span></span>

<span data-ttu-id="f3118-109">В следующем примере синхронизирующие биты и MSI-файл загружаются синхронно из общедоступного сайта скачивания облачного соединителя:</span><span class="sxs-lookup"><span data-stu-id="f3118-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="f3118-110">Пример 2</span><span class="sxs-lookup"><span data-stu-id="f3118-110">Example 2</span></span>

<span data-ttu-id="f3118-111">В следующем примере синхронизирующие биты и MSI-файл загружаются синхронно из закрытого сайта скачивания.</span><span class="sxs-lookup"><span data-stu-id="f3118-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="f3118-112">Пример 3</span><span class="sxs-lookup"><span data-stu-id="f3118-112">Example 3</span></span>

<span data-ttu-id="f3118-113">В третьем примере синхронно скачиваются файлы BITS и MSI Cloud Connector с закрытого сайта для скачивания.</span><span class="sxs-lookup"><span data-stu-id="f3118-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="f3118-114">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f3118-114">Detailed Description</span></span>
<span data-ttu-id="f3118-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f3118-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="f3118-116">Если на сайте загрузки доступна новая версия, запустите-Ккдовнлоад, чтобы скачать и установить MSI-файл с сайта загрузки, а затем синхронно Скачайте биты из облака.</span><span class="sxs-lookup"><span data-stu-id="f3118-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="f3118-117">Если новая версия MSI-файла отсутствует, командлет Start-CcDownload скачает только BITS-файл Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f3118-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="f3118-118">Если BITS-файл Cloud Connector уже скачан, командлет Start-CcDownload не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f3118-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f3118-119">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3118-119">Parameters</span></span>
<span data-ttu-id="f3118-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f3118-120"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="f3118-121">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="f3118-121">**Parameter**</span></span>|<span data-ttu-id="f3118-122">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="f3118-122">**Required**</span></span>|<span data-ttu-id="f3118-123">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f3118-123">**Type**</span></span>|<span data-ttu-id="f3118-124">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f3118-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3118-125">DownloadUrlRoot </span><span class="sxs-lookup"><span data-stu-id="f3118-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="f3118-126"> Необязательно</span><span class="sxs-lookup"><span data-stu-id="f3118-126">Optional</span></span> <br/> |<span data-ttu-id="f3118-127">System.String</span><span class="sxs-lookup"><span data-stu-id="f3118-127">System.String</span></span>  <br/> | <span data-ttu-id="f3118-128">Полный URL-адрес конкретной версии облачного соединителя на закрытом сайте скачивания.</span><span class="sxs-lookup"><span data-stu-id="f3118-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="f3118-129">Используйте этот параметр с осторожностью, убедитесь, что вы знаете, какую версию облачного соединителя вы скачиваете.</span><span class="sxs-lookup"><span data-stu-id="f3118-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="f3118-130">DownloadBitsOnly </span><span class="sxs-lookup"><span data-stu-id="f3118-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="f3118-131">Необязательно</span><span class="sxs-lookup"><span data-stu-id="f3118-131">Optional</span></span>  <br/> |<span data-ttu-id="f3118-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f3118-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="f3118-133">Пропустите скачивание и установку MSI-файла с сайта для скачивания. Скачайте только BITS-файл Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f3118-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f3118-134">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="f3118-134">Input Types</span></span>
<span data-ttu-id="f3118-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3118-135"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="f3118-p103">Нет. Командлет Start-CcDownload не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f3118-p103">None. The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f3118-138">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="f3118-138">Return Types</span></span>
<span data-ttu-id="f3118-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3118-139"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f3118-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f3118-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f3118-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f3118-141">See also</span></span>
<span data-ttu-id="f3118-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3118-142"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="f3118-143">Нет</span><span class="sxs-lookup"><span data-stu-id="f3118-143">None</span></span>
  

