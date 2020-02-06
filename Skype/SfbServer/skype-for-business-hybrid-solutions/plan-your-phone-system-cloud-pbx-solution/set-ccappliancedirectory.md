---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Командлет Set-CcApplianceDirectory задает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.
ms.openlocfilehash: a410d20c41fbb0bfef88449aaac96be727218add
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824225"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="5985f-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="5985f-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="5985f-p102">Командлет Set-CcApplianceDirectory задает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.</span><span class="sxs-lookup"><span data-stu-id="5985f-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="5985f-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="5985f-107">Examples</span></span>
<span data-ttu-id="5985f-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5985f-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5985f-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="5985f-109">Example 1</span></span>

<span data-ttu-id="5985f-110">В следующем примере задается рабочий каталог на сервере узла: c:\cloudconnector\applianceroot.</span><span class="sxs-lookup"><span data-stu-id="5985f-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="5985f-111">Параметры</span><span class="sxs-lookup"><span data-stu-id="5985f-111">Parameters</span></span>
<span data-ttu-id="5985f-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5985f-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="5985f-113">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="5985f-113">**Parameter**</span></span>|<span data-ttu-id="5985f-114">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="5985f-114">**Required**</span></span>|<span data-ttu-id="5985f-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5985f-115">**Type**</span></span>|<span data-ttu-id="5985f-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5985f-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="5985f-117">Путь</span><span class="sxs-lookup"><span data-stu-id="5985f-117">Path</span></span> <br/> | <span data-ttu-id="5985f-118">Обязательно</span><span class="sxs-lookup"><span data-stu-id="5985f-118">Required</span></span> <br/> |<span data-ttu-id="5985f-119">System.String</span><span class="sxs-lookup"><span data-stu-id="5985f-119">System.String</span></span>  <br/> | <span data-ttu-id="5985f-120"> Указывает путь к каталогу, где будут храниться все файлы развертывания.</span><span class="sxs-lookup"><span data-stu-id="5985f-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5985f-121">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="5985f-121">Input Types</span></span>
<span data-ttu-id="5985f-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5985f-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5985f-p103">Отсутствуют. Set-CcApplianceDirectory не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="5985f-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5985f-125">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="5985f-125">Return Types</span></span>
<span data-ttu-id="5985f-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5985f-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5985f-127">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5985f-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5985f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5985f-128">See also</span></span>
<span data-ttu-id="5985f-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5985f-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5985f-130">Нет</span><span class="sxs-lookup"><span data-stu-id="5985f-130">None</span></span>
  

