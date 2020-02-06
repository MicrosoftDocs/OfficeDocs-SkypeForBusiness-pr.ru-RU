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
description: Командлет Unregister-CcAppliance отменяет регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition для сайта ТСОП в конфигурации интерактивного клиента.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824133"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="e4e1c-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e4e1c-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="e4e1c-104">Командлет Unregister-CcAppliance отменяет регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition для сайта ТСОП в конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="e4e1c-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="e4e1c-105">Examples</span></span>
<span data-ttu-id="e4e1c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e4e1c-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e4e1c-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="e4e1c-107">Example 1</span></span>

<span data-ttu-id="e4e1c-108">В следующем примере отменяется регистрация текущего устройства в конфигурации интерактивного клиента:</span><span class="sxs-lookup"><span data-stu-id="e4e1c-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="e4e1c-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="e4e1c-109">Example 2</span></span>

<span data-ttu-id="e4e1c-110">В следующем примере выполняется локальная проверка отмены регистрации без подключения к конфигурации интерактивного клиента:</span><span class="sxs-lookup"><span data-stu-id="e4e1c-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="e4e1c-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="e4e1c-111">Example 3</span></span>

<span data-ttu-id="e4e1c-112">В следующем примере отменяется регистрация текущего устройства с именем "Appliance1" на сайте ТСОП "Site1":</span><span class="sxs-lookup"><span data-stu-id="e4e1c-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="e4e1c-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="e4e1c-113">Detailed Description</span></span>
<span data-ttu-id="e4e1c-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e4e1c-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e4e1c-p101">Как и в случае с командлетом Register-CcAppliance, в качестве удостоверения сайта ТСОП выступает имя сайта в сочетании с внешним полным доменным именем пограничного сервера в файле CloudConnector.ini. Аналогичным образом, в качестве удостоверения устройства выступает имя устройства в сочетании с внешним полным доменным именем сервера-посредника в файле CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="e4e1c-117">После отмены регистрации устройства перезапустите службу управления облачными соединителями и войдите в нее с учетной записью NetworkService.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e4e1c-118">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4e1c-118">Parameters</span></span>
<span data-ttu-id="e4e1c-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e4e1c-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="e4e1c-120">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-120">**Parameter**</span></span>|<span data-ttu-id="e4e1c-121">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-121">**Required**</span></span>|<span data-ttu-id="e4e1c-122">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-122">**Type**</span></span>|<span data-ttu-id="e4e1c-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e4e1c-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="e4e1c-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="e4e1c-124">SiteName</span></span> <br/> |<span data-ttu-id="e4e1c-125">Необязательно </span><span class="sxs-lookup"><span data-stu-id="e4e1c-125">Optional</span></span>  <br/> |<span data-ttu-id="e4e1c-126">System.String</span><span class="sxs-lookup"><span data-stu-id="e4e1c-126">System.String</span></span>  <br/> |<span data-ttu-id="e4e1c-p102">Имя сайта ТСОП, на котором регистрируется устройство. В качестве значения по умолчанию принимается значение SiteName в файле CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="e4e1c-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="e4e1c-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="e4e1c-130">Необязательно </span><span class="sxs-lookup"><span data-stu-id="e4e1c-130">Optional</span></span>  <br/> |<span data-ttu-id="e4e1c-131">System.String</span><span class="sxs-lookup"><span data-stu-id="e4e1c-131">System.String</span></span>  <br/> |<span data-ttu-id="e4e1c-p103">Имя текущего устройства В качестве значения по умолчанию принимается имя компьютера, присвоенное серверу узла.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="e4e1c-134">Локально</span><span class="sxs-lookup"><span data-stu-id="e4e1c-134">Local</span></span>  <br/> |<span data-ttu-id="e4e1c-135">Необязательно</span><span class="sxs-lookup"><span data-stu-id="e4e1c-135">Optional</span></span>  <br/> |<span data-ttu-id="e4e1c-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e4e1c-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="e4e1c-137">Локальная проверка конфигурации регистрации без подключения к конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e4e1c-138">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="e4e1c-138">Input Types</span></span>
<span data-ttu-id="e4e1c-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e4e1c-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e4e1c-p104">Нет. Командлет Unregister-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="e4e1c-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e4e1c-142">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="e4e1c-142">Return Types</span></span>
<span data-ttu-id="e4e1c-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e4e1c-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e4e1c-144">Нет</span><span class="sxs-lookup"><span data-stu-id="e4e1c-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e4e1c-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e4e1c-145">See also</span></span>
<span data-ttu-id="e4e1c-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e4e1c-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e4e1c-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e4e1c-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="e4e1c-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e4e1c-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="e4e1c-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e4e1c-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="e4e1c-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="e4e1c-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

