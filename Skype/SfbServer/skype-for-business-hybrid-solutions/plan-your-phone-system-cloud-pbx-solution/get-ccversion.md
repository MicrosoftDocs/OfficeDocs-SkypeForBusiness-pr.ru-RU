---
title: Get-CcVersion
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
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a><span data-ttu-id="21fbe-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="21fbe-104">Get-CcVersion</span></span>
 
<span data-ttu-id="21fbe-105">Возвращает версию устройства Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="21fbe-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="21fbe-106">Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="21fbe-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="21fbe-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="21fbe-107">Detailed Description</span></span>

<span data-ttu-id="21fbe-108">Возвращает номер версии соединителя облачных устройства для обеспечения связи на основании скриптов PowerShell установлен, файлы в каталоге Appliance и виртуальных машин, развернутых на хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="21fbe-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="21fbe-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="21fbe-109">Parameters</span></span>

|<span data-ttu-id="21fbe-110">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="21fbe-110">**Parameter**</span></span>|<span data-ttu-id="21fbe-111">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="21fbe-111">**Required**</span></span>|<span data-ttu-id="21fbe-112">**Тип**</span><span class="sxs-lookup"><span data-stu-id="21fbe-112">**Type**</span></span>|<span data-ttu-id="21fbe-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="21fbe-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21fbe-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="21fbe-114">VersionType</span></span>  <br/> |<span data-ttu-id="21fbe-115">Необязательно</span><span class="sxs-lookup"><span data-stu-id="21fbe-115">Optional</span></span>  <br/> |<span data-ttu-id="21fbe-116">System.String</span><span class="sxs-lookup"><span data-stu-id="21fbe-116">System.String</span></span>  <br/> |<span data-ttu-id="21fbe-117">Тип версии.</span><span class="sxs-lookup"><span data-stu-id="21fbe-117">Type of version.</span></span> <span data-ttu-id="21fbe-118">Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All.</span><span class="sxs-lookup"><span data-stu-id="21fbe-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="21fbe-119">Значение по умолчанию: RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="21fbe-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="21fbe-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="21fbe-120">Examples</span></span>
<span data-ttu-id="21fbe-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="21fbe-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="21fbe-122">Пример 1</span><span class="sxs-lookup"><span data-stu-id="21fbe-122">Example 1</span></span>

<span data-ttu-id="21fbe-123">В следующем примере показано версии облачных соединителя запущенные в настоящий момент скрипта в открыть консоль PowerShell:</span><span class="sxs-lookup"><span data-stu-id="21fbe-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="21fbe-124">Пример 2</span><span class="sxs-lookup"><span data-stu-id="21fbe-124">Example 2</span></span>

<span data-ttu-id="21fbe-125">В следующем примере показано версии облачных соединителя запущенные в настоящий момент двоичные файлы, развертывание виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="21fbe-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="21fbe-126">Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="21fbe-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="21fbe-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="21fbe-127">Input Types</span></span>
<span data-ttu-id="21fbe-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="21fbe-128"></span></span>

<span data-ttu-id="21fbe-129">Нет.</span><span class="sxs-lookup"><span data-stu-id="21fbe-129">None.</span></span> <span data-ttu-id="21fbe-130">Командлет Get-CcVersion не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="21fbe-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="21fbe-131">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="21fbe-131">Return Types</span></span>
<span data-ttu-id="21fbe-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="21fbe-132"></span></span>

<span data-ttu-id="21fbe-133">Нет.</span><span class="sxs-lookup"><span data-stu-id="21fbe-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="21fbe-134">См. также</span><span class="sxs-lookup"><span data-stu-id="21fbe-134">See also</span></span>
<span data-ttu-id="21fbe-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="21fbe-135"></span></span>

<span data-ttu-id="21fbe-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="21fbe-136">None.</span></span>
  

