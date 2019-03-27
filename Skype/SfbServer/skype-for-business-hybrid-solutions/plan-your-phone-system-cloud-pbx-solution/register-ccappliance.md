---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Командлет Register-CcAppliance регистрирует сведения об устройстве на сайте ТСОП в конфигурации интерактивного клиента. Прежде чем развертывать устройство и управлять им с помощью службы управления Skype для бизнеса Cloud Connector Edition, необходимо зарегистрировать его.
ms.openlocfilehash: e753f92c84b880da6aac060b65726bda5f9ba1ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892275"
---
# <a name="register-ccappliance"></a><span data-ttu-id="8c6cd-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8c6cd-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="8c6cd-105">Командлет Register-CcAppliance регистрирует сведения об устройстве на сайте ТСОП в конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="8c6cd-106">Прежде чем развертывать устройство и управлять им с помощью службы управления Skype для бизнеса Cloud Connector Edition, необходимо зарегистрировать его.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="8c6cd-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="8c6cd-107">Examples</span></span>
<span data-ttu-id="8c6cd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8c6cd-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="8c6cd-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="8c6cd-109">Example 1</span></span>

<span data-ttu-id="8c6cd-110">В следующем примере сведения о текущем устройстве регистрируются в конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="8c6cd-111">Пример 2</span><span class="sxs-lookup"><span data-stu-id="8c6cd-111">Example 2</span></span>

<span data-ttu-id="8c6cd-112">В следующем примере выполняется локальная проверка регистрации без подключения к конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="8c6cd-113">Пример 3</span><span class="sxs-lookup"><span data-stu-id="8c6cd-113">Example 3</span></span>

<span data-ttu-id="8c6cd-114">В следующем примере текущее устройство с именем "Appliance1" регистрируется на сайте ТСОП "Site1".</span><span class="sxs-lookup"><span data-stu-id="8c6cd-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="8c6cd-115">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="8c6cd-115">Detailed Description</span></span>
<span data-ttu-id="8c6cd-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8c6cd-116"></span></span>

<span data-ttu-id="8c6cd-117">Необходимо указать учетную запись и пароль администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="8c6cd-118">Используйте учетную запись, созданную для управления Cloud Connector через Интернет.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="8c6cd-119">В выпуске 1.4.2 и более ранних версий, следуйте инструкциям, чтобы предоставить пароль внешний сертификат, пароль администратора безопасного режима, пароль администратора домена и пароль администратора виртуальной Машины.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="8c6cd-120">В выпуске 2.0 и более поздних выпусках выполните инструкции по указанию пароля внешнего сертификата, а также паролей CceService и CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="8c6cd-121">В конце регистрации перезапустите соединителя облачной службы управления и войдите в систему служб CceService учетной записью.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="8c6cd-p104">В качестве удостоверения сайта ТСОП выступает имя сайта в сочетании с внешним полным доменным именем пограничного сервера в файле CloudConnector.ini. Если при регистрации сайта не использовались ни имя сайта, ни внешнее полное доменное имя пограничного сервера, для устройства создается новый сайт в конфигурации интерактивного клиента. Если найдено удостоверение сайта ТСОП, будет использоваться это удостоверение, а устройство будет зарегистрировано для этого сайта ТСОП. </span><span class="sxs-lookup"><span data-stu-id="8c6cd-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="8c6cd-125">В следующей ситуации командлет завершится сбоем и будут возвращены сведения о том, что сайт Site1 уже зарегистрирован. </span><span class="sxs-lookup"><span data-stu-id="8c6cd-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="8c6cd-126">	Имя сайта: Site1. Внешнее FQDN пограничного сервера: edgserver1.contoso.com. </span><span class="sxs-lookup"><span data-stu-id="8c6cd-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="8c6cd-127">Имя сайта ТСОП: Site1. Внешнее полное доменное имя пограничного сервера: edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="8c6cd-128">Имя сайта ТСОП: NewSite. Зарегистрированное внешнее FQDN пограничного сервера: edgserver1.contoso. </span><span class="sxs-lookup"><span data-stu-id="8c6cd-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="8c6cd-p105">В качестве удостоверения устройства выступает имя устройства в сочетании с внешним полным доменным именем сервера-посредника в файле CloudConnector.ini. Если при регистрации устройства не использовались ни имя устройства, ни внешнее полное доменное имя сервера-посредника, в конфигурации интерактивного клиента создается новое устройство. Если устройство уже создано, командлет завершается сбоем.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="8c6cd-132">В следующей ситуации командлет завершится сбоем и будут возвращены сведения о том, что устройство уже зарегистрировано. </span><span class="sxs-lookup"><span data-stu-id="8c6cd-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="8c6cd-133">Имя устройства: Appliance1. Полное доменное имя сервера-посредника: ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="8c6cd-134">Для текущего сайта ТСОП регистрируется устройство с именем Appliance1 и полным доменным именем сервера-посредника ms.vdomain.com, либо устройство с именем NewAppliance и полным доменным именем сервера-посредника ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="8c6cd-135">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c6cd-135">Parameters</span></span>
<span data-ttu-id="8c6cd-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8c6cd-136"></span></span>

|<span data-ttu-id="8c6cd-137">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="8c6cd-137">**Parameter**</span></span>|<span data-ttu-id="8c6cd-138">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="8c6cd-138">**Required**</span></span>|<span data-ttu-id="8c6cd-139">**Тип**</span><span class="sxs-lookup"><span data-stu-id="8c6cd-139">**Type**</span></span>|<span data-ttu-id="8c6cd-140">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8c6cd-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="8c6cd-141">SiteName</span></span>  <br/> |<span data-ttu-id="8c6cd-142">Необязательно </span><span class="sxs-lookup"><span data-stu-id="8c6cd-142">Optional</span></span>  <br/> |<span data-ttu-id="8c6cd-143">System.String</span><span class="sxs-lookup"><span data-stu-id="8c6cd-143">System.String</span></span>  <br/> |<span data-ttu-id="8c6cd-p106">Имя сайта ТСОП, на котором регистрируется устройство. В качестве значения по умолчанию принимается значение SiteName в файле CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="8c6cd-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="8c6cd-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="8c6cd-147">Необязательно </span><span class="sxs-lookup"><span data-stu-id="8c6cd-147">Optional</span></span>  <br/> |<span data-ttu-id="8c6cd-148">System.String</span><span class="sxs-lookup"><span data-stu-id="8c6cd-148">System.String</span></span>  <br/> |<span data-ttu-id="8c6cd-p107">Имя текущего устройства В качестве значения по умолчанию принимается имя компьютера, присвоенное серверу узла.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="8c6cd-151">Локально</span><span class="sxs-lookup"><span data-stu-id="8c6cd-151">Local</span></span>  <br/> |<span data-ttu-id="8c6cd-152">Необязательно</span><span class="sxs-lookup"><span data-stu-id="8c6cd-152">Optional</span></span>  <br/> |<span data-ttu-id="8c6cd-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8c6cd-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="8c6cd-154">Локальная проверка регистрации без подключения к конфигурации интерактивного клиента.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8c6cd-155">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="8c6cd-155">Input Types</span></span>
<span data-ttu-id="8c6cd-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8c6cd-156"></span></span>

<span data-ttu-id="8c6cd-p108">Нет. Командлет Register-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8c6cd-159">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="8c6cd-159">Return Types</span></span>
<span data-ttu-id="8c6cd-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8c6cd-160"></span></span>

<span data-ttu-id="8c6cd-161">Нет</span><span class="sxs-lookup"><span data-stu-id="8c6cd-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8c6cd-162">См. также</span><span class="sxs-lookup"><span data-stu-id="8c6cd-162">See also</span></span>
<span data-ttu-id="8c6cd-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8c6cd-163"></span></span>

[<span data-ttu-id="8c6cd-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8c6cd-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="8c6cd-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8c6cd-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="8c6cd-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8c6cd-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="8c6cd-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="8c6cd-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

