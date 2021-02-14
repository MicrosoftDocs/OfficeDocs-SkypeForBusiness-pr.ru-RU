---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Этот Unregister-CcAppliance регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition с сайта STN в конфигурации интерактивного клиента.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824133"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="71363-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="71363-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="71363-104">Этот Unregister-CcAppliance регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition с сайта STN в конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="71363-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="71363-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="71363-105">Examples</span></span>
<span data-ttu-id="71363-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="71363-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="71363-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="71363-107">Example 1</span></span>

<span data-ttu-id="71363-108">В следующем примере из конфигурации интерактивного клиента отрегистрировано текущее устройство:</span><span class="sxs-lookup"><span data-stu-id="71363-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="71363-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="71363-109">Example 2</span></span>

<span data-ttu-id="71363-110">В следующем примере конфигурация проверяется на наличие локальной регистрации без подключения к конфигурации интерактивного клиента:</span><span class="sxs-lookup"><span data-stu-id="71363-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="71363-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="71363-111">Example 3</span></span>

<span data-ttu-id="71363-112">В следующем примере текущее устройство с именем Appliance1 будет отрегистрировано на сайте STN "Site1":</span><span class="sxs-lookup"><span data-stu-id="71363-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="71363-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="71363-113">Detailed Description</span></span>
<span data-ttu-id="71363-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="71363-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="71363-115">Аналогично Register-CcAppliance, siteName в сочетании с внешним FQDN edge Server в CloudConnector.ini файле считается удостоверением сайта STN.</span><span class="sxs-lookup"><span data-stu-id="71363-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="71363-116">Аналогичным образом, applianceName в сочетании с FQDN сервера-CloudConnector.ini в файле CloudConnector.ini считается удостоверением устройства.</span><span class="sxs-lookup"><span data-stu-id="71363-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="71363-117">После регистрации устройства перезапустите службу управления Cloud Connector и войдите в систему под учетной записью NetworkService.</span><span class="sxs-lookup"><span data-stu-id="71363-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="71363-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="71363-118">Parameters</span></span>
<span data-ttu-id="71363-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="71363-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="71363-120">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="71363-120">**Parameter**</span></span>|<span data-ttu-id="71363-121">**Required**</span><span class="sxs-lookup"><span data-stu-id="71363-121">**Required**</span></span>|<span data-ttu-id="71363-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="71363-122">**Type**</span></span>|<span data-ttu-id="71363-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="71363-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="71363-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="71363-124">SiteName</span></span> <br/> |<span data-ttu-id="71363-125">Необязательный</span><span class="sxs-lookup"><span data-stu-id="71363-125">Optional</span></span>  <br/> |<span data-ttu-id="71363-126">System.String</span><span class="sxs-lookup"><span data-stu-id="71363-126">System.String</span></span>  <br/> |<span data-ttu-id="71363-127">Имя сайта STN, на котором зарегистрировано устройство.</span><span class="sxs-lookup"><span data-stu-id="71363-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="71363-128">Значение по умолчанию — SiteName в CloudConnector.ini файле.</span><span class="sxs-lookup"><span data-stu-id="71363-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="71363-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="71363-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="71363-130">Необязательный</span><span class="sxs-lookup"><span data-stu-id="71363-130">Optional</span></span>  <br/> |<span data-ttu-id="71363-131">System.String</span><span class="sxs-lookup"><span data-stu-id="71363-131">System.String</span></span>  <br/> |<span data-ttu-id="71363-132">Имя текущего устройства.</span><span class="sxs-lookup"><span data-stu-id="71363-132">Name of the current appliance.</span></span> <span data-ttu-id="71363-133">Значение по умолчанию — имя компьютера хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="71363-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="71363-134">Локальный</span><span class="sxs-lookup"><span data-stu-id="71363-134">Local</span></span>  <br/> |<span data-ttu-id="71363-135">Необязательный</span><span class="sxs-lookup"><span data-stu-id="71363-135">Optional</span></span>  <br/> |<span data-ttu-id="71363-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="71363-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="71363-137">Проверьте конфигурацию регистрации локально, не подключаясь к конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="71363-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="71363-138">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="71363-138">Input Types</span></span>
<span data-ttu-id="71363-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="71363-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="71363-140">Нет.</span><span class="sxs-lookup"><span data-stu-id="71363-140">None.</span></span> <span data-ttu-id="71363-141">Этот Unregister-CcAppliance не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="71363-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="71363-142">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="71363-142">Return Types</span></span>
<span data-ttu-id="71363-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="71363-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="71363-144">Нет</span><span class="sxs-lookup"><span data-stu-id="71363-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71363-145">См. также</span><span class="sxs-lookup"><span data-stu-id="71363-145">See also</span></span>
<span data-ttu-id="71363-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="71363-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="71363-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="71363-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="71363-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="71363-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="71363-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="71363-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="71363-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="71363-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

