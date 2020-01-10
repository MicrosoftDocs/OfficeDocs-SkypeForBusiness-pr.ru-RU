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
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003349"
---
# <a name="get-ccversion"></a><span data-ttu-id="0f9ad-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="0f9ad-104">Get-CcVersion</span></span>
 
<span data-ttu-id="0f9ad-p102">Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="0f9ad-107">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="0f9ad-107">Detailed Description</span></span>

<span data-ttu-id="0f9ad-108">Возвращает версию устройства облачного соединителя, основанную на установленных сценариях PowerShell, файлах в каталоге устройства и виртуальных машинах, развернутых на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0f9ad-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f9ad-109">Parameters</span></span>

|<span data-ttu-id="0f9ad-110">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="0f9ad-110">**Parameter**</span></span>|<span data-ttu-id="0f9ad-111">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="0f9ad-111">**Required**</span></span>|<span data-ttu-id="0f9ad-112">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0f9ad-112">**Type**</span></span>|<span data-ttu-id="0f9ad-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0f9ad-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f9ad-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="0f9ad-114">VersionType</span></span>  <br/> |<span data-ttu-id="0f9ad-115">Необязательно</span><span class="sxs-lookup"><span data-stu-id="0f9ad-115">Optional</span></span>  <br/> |<span data-ttu-id="0f9ad-116">System.String</span><span class="sxs-lookup"><span data-stu-id="0f9ad-116">System.String</span></span>  <br/> |<span data-ttu-id="0f9ad-p103">Тип версии. Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию: RunningScripts. </span><span class="sxs-lookup"><span data-stu-id="0f9ad-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="0f9ad-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="0f9ad-120">Examples</span></span>
<span data-ttu-id="0f9ad-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9ad-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="0f9ad-122">Пример 1</span><span class="sxs-lookup"><span data-stu-id="0f9ad-122">Example 1</span></span>

<span data-ttu-id="0f9ad-123">В следующем примере показана версия облачного соединителя запущенного сценария на открытой консоли PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="0f9ad-124">Пример 2</span><span class="sxs-lookup"><span data-stu-id="0f9ad-124">Example 2</span></span>

<span data-ttu-id="0f9ad-125">В следующем примере показана версия облачного соединителя для исполняемых в данный момент двоичных файлов, развернутых на виртуальных машинах.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="0f9ad-126">Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="0f9ad-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="0f9ad-127">Input Types</span></span>
<span data-ttu-id="0f9ad-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9ad-128"></span></span>

<span data-ttu-id="0f9ad-p105">Нет. Командлет Get-CcVersion не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0f9ad-131">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="0f9ad-131">Return Types</span></span>
<span data-ttu-id="0f9ad-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9ad-132"></span></span>

<span data-ttu-id="0f9ad-133">Нет. </span><span class="sxs-lookup"><span data-stu-id="0f9ad-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0f9ad-134">См. также</span><span class="sxs-lookup"><span data-stu-id="0f9ad-134">See also</span></span>
<span data-ttu-id="0f9ad-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9ad-135"></span></span>

<span data-ttu-id="0f9ad-136">Нет.</span><span class="sxs-lookup"><span data-stu-id="0f9ad-136">None.</span></span>
  

