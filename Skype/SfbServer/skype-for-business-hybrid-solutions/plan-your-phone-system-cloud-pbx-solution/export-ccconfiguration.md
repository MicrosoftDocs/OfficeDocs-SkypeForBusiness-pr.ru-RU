---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287421"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="a2e06-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2e06-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="a2e06-104">Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a2e06-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a2e06-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="a2e06-105">Examples</span></span>
<span data-ttu-id="a2e06-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a2e06-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="a2e06-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="a2e06-107">Example 1</span></span>

<span data-ttu-id="a2e06-108">В следующем примере в параметре Path задается полный путь к файлу и выполняется экспорт конфигураций в этот файл.</span><span class="sxs-lookup"><span data-stu-id="a2e06-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="a2e06-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="a2e06-109">Detailed Description</span></span>
<span data-ttu-id="a2e06-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a2e06-110"></span></span>

<span data-ttu-id="a2e06-p101">С помощью командлета Export-CcConfiguration можно сохранить конфигурацию Cloud Connector в файл по указанному пути. Эта команда была представлена в Cloud Connector Edition версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="a2e06-p101">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path. This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a2e06-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2e06-113">Parameters</span></span>
<span data-ttu-id="a2e06-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a2e06-114"></span></span>

|<span data-ttu-id="a2e06-115">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="a2e06-115">**Parameter**</span></span>|<span data-ttu-id="a2e06-116">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="a2e06-116">**Required**</span></span>|<span data-ttu-id="a2e06-117">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a2e06-117">**Type**</span></span>|<span data-ttu-id="a2e06-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a2e06-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a2e06-119">Путь</span><span class="sxs-lookup"><span data-stu-id="a2e06-119">Path</span></span>  <br/> |<span data-ttu-id="a2e06-120">Обязательно</span><span class="sxs-lookup"><span data-stu-id="a2e06-120">Required</span></span>  <br/> |<span data-ttu-id="a2e06-121">System.String</span><span class="sxs-lookup"><span data-stu-id="a2e06-121">System.String</span></span>  <br/> |<span data-ttu-id="a2e06-122">Полный путь к файлу, в котором будут храниться конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a2e06-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a2e06-123">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="a2e06-123">Input Types</span></span>
<span data-ttu-id="a2e06-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a2e06-124"></span></span>

<span data-ttu-id="a2e06-p102">Нет. Командлет Export-CcConfiguration не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="a2e06-p102">None. The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a2e06-127">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="a2e06-127">Return Types</span></span>
<span data-ttu-id="a2e06-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a2e06-128"></span></span>

<span data-ttu-id="a2e06-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="a2e06-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a2e06-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a2e06-130">See also</span></span>
<span data-ttu-id="a2e06-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a2e06-131"></span></span>

<span data-ttu-id="a2e06-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2e06-132">Import-CcConfiguration</span></span>
  

