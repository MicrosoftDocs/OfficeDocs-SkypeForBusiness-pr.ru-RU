---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894239"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="689f8-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="689f8-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="689f8-104">Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="689f8-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="689f8-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="689f8-105">Examples</span></span>
<span data-ttu-id="689f8-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="689f8-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="689f8-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="689f8-107">Example 1</span></span>

<span data-ttu-id="689f8-108">В следующем примере в параметре Path задается полный путь к файлу и выполняется экспорт конфигураций в этот файл.</span><span class="sxs-lookup"><span data-stu-id="689f8-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="689f8-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="689f8-109">Detailed Description</span></span>
<span data-ttu-id="689f8-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="689f8-110"></span></span>

<span data-ttu-id="689f8-p101">С помощью командлета Export-CcConfiguration можно сохранить конфигурацию Cloud Connector в файл по указанному пути. Эта команда была представлена в Cloud Connector Edition версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="689f8-p101">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path. This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="689f8-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="689f8-113">Parameters</span></span>
<span data-ttu-id="689f8-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="689f8-114"></span></span>

|<span data-ttu-id="689f8-115">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="689f8-115">**Parameter**</span></span>|<span data-ttu-id="689f8-116">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="689f8-116">**Required**</span></span>|<span data-ttu-id="689f8-117">**Тип**</span><span class="sxs-lookup"><span data-stu-id="689f8-117">**Type**</span></span>|<span data-ttu-id="689f8-118">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="689f8-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="689f8-119">Путь</span><span class="sxs-lookup"><span data-stu-id="689f8-119">Path</span></span>  <br/> |<span data-ttu-id="689f8-120">Обязательно</span><span class="sxs-lookup"><span data-stu-id="689f8-120">Required</span></span>  <br/> |<span data-ttu-id="689f8-121">System.String</span><span class="sxs-lookup"><span data-stu-id="689f8-121">System.String</span></span>  <br/> |<span data-ttu-id="689f8-122">Полный путь к файлу, в котором будут храниться конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="689f8-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="689f8-123">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="689f8-123">Input Types</span></span>
<span data-ttu-id="689f8-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="689f8-124"></span></span>

<span data-ttu-id="689f8-p102">Нет. Командлет Export-CcConfiguration не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="689f8-p102">None. The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="689f8-127">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="689f8-127">Return Types</span></span>
<span data-ttu-id="689f8-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="689f8-128"></span></span>

<span data-ttu-id="689f8-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="689f8-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="689f8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="689f8-130">See also</span></span>
<span data-ttu-id="689f8-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="689f8-131"></span></span>

<span data-ttu-id="689f8-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="689f8-132">Import-CcConfiguration</span></span>
  

