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
description: Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799849"
---
# <a name="get-ccversion"></a><span data-ttu-id="d04c9-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="d04c9-104">Get-CcVersion</span></span>
 
<span data-ttu-id="d04c9-p102">Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d04c9-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="d04c9-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d04c9-107">Detailed Description</span></span>

<span data-ttu-id="d04c9-108">Возвращает версию устройства облачного соединителя, основанную на установленных сценариях PowerShell, файлах в каталоге устройства и виртуальных машинах, развернутых на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="d04c9-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d04c9-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="d04c9-109">Parameters</span></span>

|<span data-ttu-id="d04c9-110">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="d04c9-110">**Parameter**</span></span>|<span data-ttu-id="d04c9-111">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="d04c9-111">**Required**</span></span>|<span data-ttu-id="d04c9-112">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d04c9-112">**Type**</span></span>|<span data-ttu-id="d04c9-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d04c9-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d04c9-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="d04c9-114">VersionType</span></span>  <br/> |<span data-ttu-id="d04c9-115">Необязательно</span><span class="sxs-lookup"><span data-stu-id="d04c9-115">Optional</span></span>  <br/> |<span data-ttu-id="d04c9-116">System.String</span><span class="sxs-lookup"><span data-stu-id="d04c9-116">System.String</span></span>  <br/> |<span data-ttu-id="d04c9-p103">Тип версии. Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию: RunningScripts. </span><span class="sxs-lookup"><span data-stu-id="d04c9-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="d04c9-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="d04c9-120">Examples</span></span>
<span data-ttu-id="d04c9-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d04c9-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d04c9-122">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d04c9-122">Example 1</span></span>

<span data-ttu-id="d04c9-123">В следующем примере показана версия облачного соединителя запущенного сценария на открытой консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d04c9-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="d04c9-124">Пример 2</span><span class="sxs-lookup"><span data-stu-id="d04c9-124">Example 2</span></span>

<span data-ttu-id="d04c9-125">В следующем примере показана версия облачного соединителя для исполняемых в данный момент двоичных файлов, развернутых на виртуальных машинах.</span><span class="sxs-lookup"><span data-stu-id="d04c9-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="d04c9-126">Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="d04c9-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="d04c9-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="d04c9-127">Input Types</span></span>
<span data-ttu-id="d04c9-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d04c9-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="d04c9-p105">Нет. Командлет Get-CcVersion не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="d04c9-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d04c9-131">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d04c9-131">Return Types</span></span>
<span data-ttu-id="d04c9-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d04c9-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="d04c9-133">Нет. </span><span class="sxs-lookup"><span data-stu-id="d04c9-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d04c9-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d04c9-134">See also</span></span>
<span data-ttu-id="d04c9-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d04c9-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="d04c9-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="d04c9-136">None.</span></span>
  

