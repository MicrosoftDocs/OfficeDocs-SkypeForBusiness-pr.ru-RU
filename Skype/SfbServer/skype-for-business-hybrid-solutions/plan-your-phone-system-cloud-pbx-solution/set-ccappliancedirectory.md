---
title: SET-CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Командлет Set-CcApplianceDirectory задает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.
ms.openlocfilehash: 67fda4f1ef7da0f9a7e61b1099c7edb3b96ad62c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="ea357-104">SET-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="ea357-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="ea357-p102">Командлет Set-CcApplianceDirectory задает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.</span><span class="sxs-lookup"><span data-stu-id="ea357-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="ea357-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="ea357-107">Examples</span></span>
<span data-ttu-id="ea357-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ea357-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="ea357-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="ea357-109">Example 1</span></span>

<span data-ttu-id="ea357-110">В следующем примере задается рабочий каталог на сервере узла: c:\cloudconnector\applianceroot.</span><span class="sxs-lookup"><span data-stu-id="ea357-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="ea357-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea357-111">Parameters</span></span>
<span data-ttu-id="ea357-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ea357-112"></span></span>

|<span data-ttu-id="ea357-113">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="ea357-113">**Parameter**</span></span>|<span data-ttu-id="ea357-114">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="ea357-114">**Required**</span></span>|<span data-ttu-id="ea357-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="ea357-115">**Type**</span></span>|<span data-ttu-id="ea357-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ea357-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ea357-117">Путь</span><span class="sxs-lookup"><span data-stu-id="ea357-117">Path</span></span> <br/> | <span data-ttu-id="ea357-118">Обязательно</span><span class="sxs-lookup"><span data-stu-id="ea357-118">Required</span></span> <br/> |<span data-ttu-id="ea357-119">System.String</span><span class="sxs-lookup"><span data-stu-id="ea357-119">System.String</span></span>  <br/> | <span data-ttu-id="ea357-120"> Указывает путь к каталогу, где будут храниться все файлы развертывания.</span><span class="sxs-lookup"><span data-stu-id="ea357-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ea357-121">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="ea357-121">Input Types</span></span>
<span data-ttu-id="ea357-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ea357-122"></span></span>

<span data-ttu-id="ea357-p103">Отсутствуют. Set-CcApplianceDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="ea357-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ea357-125">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="ea357-125">Return Types</span></span>
<span data-ttu-id="ea357-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ea357-126"></span></span>

<span data-ttu-id="ea357-127">Нет</span><span class="sxs-lookup"><span data-stu-id="ea357-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea357-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ea357-128">See also</span></span>
<span data-ttu-id="ea357-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ea357-129"></span></span>

<span data-ttu-id="ea357-130">Нет</span><span class="sxs-lookup"><span data-stu-id="ea357-130">None</span></span>
  

