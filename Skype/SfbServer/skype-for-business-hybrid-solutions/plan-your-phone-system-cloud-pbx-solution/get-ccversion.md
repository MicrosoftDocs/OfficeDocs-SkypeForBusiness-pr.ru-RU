---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Возвращает версию устройства Cloud Connector. Get-CCVersion можно использовать только на хост-компьютере Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799849"
---
# <a name="get-ccversion"></a><span data-ttu-id="45909-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="45909-104">Get-CcVersion</span></span>
 
<span data-ttu-id="45909-105">Возвращает версию устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="45909-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="45909-106">Get-CCVersion можно использовать только на хост-компьютере Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="45909-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="45909-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="45909-107">Detailed Description</span></span>

<span data-ttu-id="45909-108">Возвращает версию устройства Cloud Connector на основе установленных сценариев PowerShell, файлов в каталоге устройства и виртуальных машин, развернутых на сервере размещения.</span><span class="sxs-lookup"><span data-stu-id="45909-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="45909-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="45909-109">Parameters</span></span>

|<span data-ttu-id="45909-110">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="45909-110">**Parameter**</span></span>|<span data-ttu-id="45909-111">**Required**</span><span class="sxs-lookup"><span data-stu-id="45909-111">**Required**</span></span>|<span data-ttu-id="45909-112">**Тип**</span><span class="sxs-lookup"><span data-stu-id="45909-112">**Type**</span></span>|<span data-ttu-id="45909-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="45909-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45909-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="45909-114">VersionType</span></span>  <br/> |<span data-ttu-id="45909-115">Необязательный</span><span class="sxs-lookup"><span data-stu-id="45909-115">Optional</span></span>  <br/> |<span data-ttu-id="45909-116">System.String</span><span class="sxs-lookup"><span data-stu-id="45909-116">System.String</span></span>  <br/> |<span data-ttu-id="45909-117">Тип версии.</span><span class="sxs-lookup"><span data-stu-id="45909-117">Type of version.</span></span> <span data-ttu-id="45909-118">Значение параметра может быть RunningScripts, RunningBits, BackupBits или All.</span><span class="sxs-lookup"><span data-stu-id="45909-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="45909-119">Значение по умолчанию — RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="45909-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="45909-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="45909-120">Examples</span></span>
<span data-ttu-id="45909-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45909-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="45909-122">Пример 1</span><span class="sxs-lookup"><span data-stu-id="45909-122">Example 1</span></span>

<span data-ttu-id="45909-123">В следующем примере показана версия Cloud Connector для запущенного сценария в открытой консоли PowerShell:</span><span class="sxs-lookup"><span data-stu-id="45909-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="45909-124">Пример 2</span><span class="sxs-lookup"><span data-stu-id="45909-124">Example 2</span></span>

<span data-ttu-id="45909-125">В следующем примере показана версия Cloud Connector запущенных в настоящее время binaries, развернутых на виртуальных машинах.</span><span class="sxs-lookup"><span data-stu-id="45909-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="45909-126">Вы можете увидеть версию в именах работающих виртуальных машин в диспетчере Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="45909-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="45909-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="45909-127">Input Types</span></span>
<span data-ttu-id="45909-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45909-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="45909-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="45909-129">None.</span></span> <span data-ttu-id="45909-130">Этот Get-CcVersion не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="45909-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="45909-131">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="45909-131">Return Types</span></span>
<span data-ttu-id="45909-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45909-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="45909-133">Нет.</span><span class="sxs-lookup"><span data-stu-id="45909-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="45909-134">См. также</span><span class="sxs-lookup"><span data-stu-id="45909-134">See also</span></span>
<span data-ttu-id="45909-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="45909-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="45909-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="45909-136">None.</span></span>
  

