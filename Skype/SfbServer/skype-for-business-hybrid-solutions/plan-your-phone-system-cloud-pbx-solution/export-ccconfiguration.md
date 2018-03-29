---
title: Export-CcConfiguration
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
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="47792-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="47792-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="47792-104">Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="47792-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="47792-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="47792-105">Examples</span></span>
<span data-ttu-id="47792-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47792-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="47792-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="47792-107">Example 1</span></span>

<span data-ttu-id="47792-108">В следующем примере в параметре Path задается полный путь к файлу и выполняется экспорт конфигураций в этот файл.</span><span class="sxs-lookup"><span data-stu-id="47792-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="47792-109">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="47792-109">Detailed Description</span></span>
<span data-ttu-id="47792-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47792-110"></span></span>

<span data-ttu-id="47792-111">С помощью командлета Export-CcConfiguration можно сохранить конфигурацию Cloud Connector в файл по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="47792-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="47792-112">Эта команда была представлена в Cloud Connector Edition версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="47792-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="47792-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="47792-113">Parameters</span></span>
<span data-ttu-id="47792-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47792-114"></span></span>

|<span data-ttu-id="47792-115">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="47792-115">**Parameter**</span></span>|<span data-ttu-id="47792-116">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="47792-116">**Required**</span></span>|<span data-ttu-id="47792-117">**Тип**</span><span class="sxs-lookup"><span data-stu-id="47792-117">**Type**</span></span>|<span data-ttu-id="47792-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="47792-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="47792-119">Путь</span><span class="sxs-lookup"><span data-stu-id="47792-119">Path</span></span>  <br/> |<span data-ttu-id="47792-120">Обязательно</span><span class="sxs-lookup"><span data-stu-id="47792-120">Required</span></span>  <br/> |<span data-ttu-id="47792-121">System.String</span><span class="sxs-lookup"><span data-stu-id="47792-121">System.String</span></span>  <br/> |<span data-ttu-id="47792-122">Полный путь к файлу, в котором будут храниться конфигурации Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="47792-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="47792-123">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="47792-123">Input Types</span></span>
<span data-ttu-id="47792-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47792-124"></span></span>

<span data-ttu-id="47792-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="47792-125">None.</span></span> <span data-ttu-id="47792-126">Командлет Export-CcConfiguration не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="47792-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="47792-127">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="47792-127">Return Types</span></span>
<span data-ttu-id="47792-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47792-128"></span></span>

<span data-ttu-id="47792-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="47792-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47792-130">См. также</span><span class="sxs-lookup"><span data-stu-id="47792-130">See also</span></span>
<span data-ttu-id="47792-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47792-131"></span></span>

<span data-ttu-id="47792-132">Импорт CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="47792-132">Import-CcConfiguration</span></span>
  

