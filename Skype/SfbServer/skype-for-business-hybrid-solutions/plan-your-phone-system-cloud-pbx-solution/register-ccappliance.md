---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Этот Register-CcAppliance регистрирует сведения об устройстве на сайте STN в конфигурации интерактивного клиента. Прежде чем развертывать устройство и управлять им с помощью службы управления Skype для бизнеса Cloud Connector Edition, необходимо зарегистрировать его.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824305"
---
# <a name="register-ccappliance"></a><span data-ttu-id="83295-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="83295-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="83295-105">Этот Register-CcAppliance регистрирует сведения об устройстве на сайте STN в конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="83295-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="83295-106">Прежде чем развертывать устройство и управлять им с помощью службы управления Skype для бизнеса Cloud Connector Edition, необходимо зарегистрировать его.</span><span class="sxs-lookup"><span data-stu-id="83295-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="83295-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="83295-107">Examples</span></span>
<span data-ttu-id="83295-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="83295-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="83295-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="83295-109">Example 1</span></span>

<span data-ttu-id="83295-110">В следующем примере сведения о текущем устройстве регистрируются в конфигурации интерактивного клиента:</span><span class="sxs-lookup"><span data-stu-id="83295-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="83295-111">Пример 2</span><span class="sxs-lookup"><span data-stu-id="83295-111">Example 2</span></span>

<span data-ttu-id="83295-112">В следующем примере проверяется локализованная регистрация без подключения к конфигурации интерактивного клиента:</span><span class="sxs-lookup"><span data-stu-id="83295-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="83295-113">Пример 3</span><span class="sxs-lookup"><span data-stu-id="83295-113">Example 3</span></span>

<span data-ttu-id="83295-114">В следующем примере текущее устройство с именем Appliance1 регистрируется на сайте STN "Site1":</span><span class="sxs-lookup"><span data-stu-id="83295-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="83295-115">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="83295-115">Detailed Description</span></span>
<span data-ttu-id="83295-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="83295-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="83295-117">Необходимо вводить имя и пароль учетной записи администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="83295-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="83295-118">Используйте учетную запись, созданную для управления Cloud Connector в Интернете.</span><span class="sxs-lookup"><span data-stu-id="83295-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="83295-119">В выпуске 1.4.2 и более ранних версиях следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль администратора безопасного режима, пароль администратора домена и пароль администратора ВМ.</span><span class="sxs-lookup"><span data-stu-id="83295-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="83295-120">В выпуске 2.0 и более поздних версиях следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль CceService и пароль CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="83295-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="83295-121">По завершении регистрации перезапустите службу управления Cloud Connector и войдите в службы под учетной записью CceService.</span><span class="sxs-lookup"><span data-stu-id="83295-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="83295-122">SiteName в сочетании с внешним FQDN edge Server в CloudConnector.ini файле считается удостоверением сайта STN.</span><span class="sxs-lookup"><span data-stu-id="83295-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="83295-123">Если для регистрации сайта не использовались ни имя сайта, ни внешнее имя FQDN edge Server, для этого устройства будет создан новый сайт в конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="83295-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="83295-124">При обнаружении удостоверения сайта STN сайт STN будет использовать это удостоверение, и устройство будет зарегистрировано на этом сайте STN.</span><span class="sxs-lookup"><span data-stu-id="83295-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="83295-125">В следующей ситуации сбой при этом указывает на то, что site1 уже зарегистрирован:</span><span class="sxs-lookup"><span data-stu-id="83295-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="83295-126">SiteName — site1, а внешнее имя FQDN edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="83295-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="83295-127">Сайт STN, имя которого siteName — Site1, а внешнее имя FQDN edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="83295-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="83295-128">Сайт STN, имя сайта которого — NewSite, а внешнее edgserver1.contoso.com зарегистрируется.</span><span class="sxs-lookup"><span data-stu-id="83295-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="83295-129">ApplianceName в сочетании с FQDN сервера-CloudConnector.ini в файле устройства считается удостоверением устройства.</span><span class="sxs-lookup"><span data-stu-id="83295-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="83295-130">Если для регистрации устройства не использовались ни имя устройства, ни FQDN сервера-посредника, в конфигурации интерактивного клиента будет создано новое устройство.</span><span class="sxs-lookup"><span data-stu-id="83295-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="83295-131">Если устройство уже зарегистрировано, то он не будет работать.</span><span class="sxs-lookup"><span data-stu-id="83295-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="83295-132">В следующей ситуации сбой при этом указывает на то, что устройство уже зарегистрировано:</span><span class="sxs-lookup"><span data-stu-id="83295-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="83295-133">ApplianceName — это Appliance1, а сервер-посредник — ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="83295-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="83295-134">На текущем сайте STN, если устройство с именем Appliance1 и FQDN сервера-посредника ms.vdomain.com или устройство с именем NewAppliance и FQDN сервера-ms1.vdomain.com было зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="83295-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="83295-135">Параметры</span><span class="sxs-lookup"><span data-stu-id="83295-135">Parameters</span></span>
<span data-ttu-id="83295-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="83295-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="83295-137">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="83295-137">**Parameter**</span></span>|<span data-ttu-id="83295-138">**Required**</span><span class="sxs-lookup"><span data-stu-id="83295-138">**Required**</span></span>|<span data-ttu-id="83295-139">**Тип**</span><span class="sxs-lookup"><span data-stu-id="83295-139">**Type**</span></span>|<span data-ttu-id="83295-140">**Описание**</span><span class="sxs-lookup"><span data-stu-id="83295-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83295-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="83295-141">SiteName</span></span>  <br/> |<span data-ttu-id="83295-142">Необязательный</span><span class="sxs-lookup"><span data-stu-id="83295-142">Optional</span></span>  <br/> |<span data-ttu-id="83295-143">System.String</span><span class="sxs-lookup"><span data-stu-id="83295-143">System.String</span></span>  <br/> |<span data-ttu-id="83295-144">Имя сайта STN, на котором зарегистрировано устройство.</span><span class="sxs-lookup"><span data-stu-id="83295-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="83295-145">Значение по умолчанию — SiteName в CloudConnector.ini файле.</span><span class="sxs-lookup"><span data-stu-id="83295-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="83295-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="83295-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="83295-147">Необязательный</span><span class="sxs-lookup"><span data-stu-id="83295-147">Optional</span></span>  <br/> |<span data-ttu-id="83295-148">System.String</span><span class="sxs-lookup"><span data-stu-id="83295-148">System.String</span></span>  <br/> |<span data-ttu-id="83295-149">Имя текущего устройства.</span><span class="sxs-lookup"><span data-stu-id="83295-149">Name of the current appliance.</span></span> <span data-ttu-id="83295-150">Значение по умолчанию — имя компьютера хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="83295-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="83295-151">Локальный</span><span class="sxs-lookup"><span data-stu-id="83295-151">Local</span></span>  <br/> |<span data-ttu-id="83295-152">Необязательный</span><span class="sxs-lookup"><span data-stu-id="83295-152">Optional</span></span>  <br/> |<span data-ttu-id="83295-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="83295-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="83295-154">Проверьте конфигурации регистрации локально, не подключаясь к конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="83295-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="83295-155">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="83295-155">Input Types</span></span>
<span data-ttu-id="83295-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83295-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="83295-157">Нет.</span><span class="sxs-lookup"><span data-stu-id="83295-157">None.</span></span> <span data-ttu-id="83295-158">Этот Register-CcAppliance не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="83295-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="83295-159">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="83295-159">Return Types</span></span>
<span data-ttu-id="83295-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83295-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="83295-161">Нет</span><span class="sxs-lookup"><span data-stu-id="83295-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="83295-162">См. также</span><span class="sxs-lookup"><span data-stu-id="83295-162">See also</span></span>
<span data-ttu-id="83295-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="83295-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="83295-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="83295-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="83295-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="83295-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="83295-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="83295-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="83295-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="83295-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

