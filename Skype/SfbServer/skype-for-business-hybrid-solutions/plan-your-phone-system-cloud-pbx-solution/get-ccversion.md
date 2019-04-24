---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233759"
---
# <a name="get-ccversion"></a><span data-ttu-id="9d6c1-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="9d6c1-104">Get-CcVersion</span></span>
 
<span data-ttu-id="9d6c1-p102">Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="9d6c1-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="9d6c1-107">Detailed Description</span></span>

<span data-ttu-id="9d6c1-108">Возвращает номер версии соединителя облачных устройства для обеспечения связи на основании скриптов PowerShell установлен, файлы в каталоге Appliance и виртуальных машин, развернутых на хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9d6c1-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d6c1-109">Parameters</span></span>

|<span data-ttu-id="9d6c1-110">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-110">**Parameter**</span></span>|<span data-ttu-id="9d6c1-111">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-111">**Required**</span></span>|<span data-ttu-id="9d6c1-112">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-112">**Type**</span></span>|<span data-ttu-id="9d6c1-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9d6c1-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d6c1-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="9d6c1-114">VersionType</span></span>  <br/> |<span data-ttu-id="9d6c1-115">Необязательно</span><span class="sxs-lookup"><span data-stu-id="9d6c1-115">Optional</span></span>  <br/> |<span data-ttu-id="9d6c1-116">System.String</span><span class="sxs-lookup"><span data-stu-id="9d6c1-116">System.String</span></span>  <br/> |<span data-ttu-id="9d6c1-p103">Тип версии. Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию: RunningScripts. </span><span class="sxs-lookup"><span data-stu-id="9d6c1-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="9d6c1-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="9d6c1-120">Examples</span></span>
<span data-ttu-id="9d6c1-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9d6c1-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="9d6c1-122">Пример 1</span><span class="sxs-lookup"><span data-stu-id="9d6c1-122">Example 1</span></span>

<span data-ttu-id="9d6c1-123">В следующем примере показано версии облачных соединителя запущенные в настоящий момент скрипта в открыть консоль PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9d6c1-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="9d6c1-124">Пример 2</span><span class="sxs-lookup"><span data-stu-id="9d6c1-124">Example 2</span></span>

<span data-ttu-id="9d6c1-125">В следующем примере показано версии облачных соединителя запущенные в настоящий момент двоичные файлы, развертывание виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="9d6c1-126">Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="9d6c1-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="9d6c1-127">Input Types</span></span>
<span data-ttu-id="9d6c1-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9d6c1-128"></span></span>

<span data-ttu-id="9d6c1-p105">Нет. Командлет Get-CcVersion не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9d6c1-131">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="9d6c1-131">Return Types</span></span>
<span data-ttu-id="9d6c1-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9d6c1-132"></span></span>

<span data-ttu-id="9d6c1-133">Нет. </span><span class="sxs-lookup"><span data-stu-id="9d6c1-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d6c1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9d6c1-134">See also</span></span>
<span data-ttu-id="9d6c1-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9d6c1-135"></span></span>

<span data-ttu-id="9d6c1-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-136">None.</span></span>
  

