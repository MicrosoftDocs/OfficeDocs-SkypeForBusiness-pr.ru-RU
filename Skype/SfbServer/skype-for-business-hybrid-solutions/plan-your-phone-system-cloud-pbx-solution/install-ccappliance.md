---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Этот Install-CcAppliance устанавливает на сервере хост-сервера устройство Skype для бизнеса Cloud Connector Edition, в том числе виртуальные машины AD, центрального банка управления, сервера-посредника и сервера-посредника.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799879"
---
# <a name="install-ccappliance"></a><span data-ttu-id="32ee3-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="32ee3-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="32ee3-104">Этот Install-CcAppliance устанавливает на сервере хост-сервера устройство Skype для бизнеса Cloud Connector Edition, в том числе виртуальные машины AD, центрального банка управления, сервера-посредника и сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="32ee3-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="32ee3-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="32ee3-105">Examples</span></span>
<span data-ttu-id="32ee3-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="32ee3-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="32ee3-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="32ee3-107">Example 1</span></span>

<span data-ttu-id="32ee3-108">В следующем примере на сервере хост-сервера устанавливается новое устройство Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="32ee3-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="32ee3-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="32ee3-109">Example 2</span></span>

<span data-ttu-id="32ee3-110">В следующем примере Cloud Connector обновляется до последней версии:</span><span class="sxs-lookup"><span data-stu-id="32ee3-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="32ee3-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="32ee3-111">Example 3</span></span>

<span data-ttu-id="32ee3-112">В следующем примере удаляются все учетные данные Cloud Connector, кэшные на сервере, пользователь снова указывает все учетные данные, а затем устанавливает Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="32ee3-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="32ee3-113">Пример 4</span><span class="sxs-lookup"><span data-stu-id="32ee3-113">Example 4</span></span>

<span data-ttu-id="32ee3-114">В следующем примере показаны все этапы развертывания в консоли PowerShell:</span><span class="sxs-lookup"><span data-stu-id="32ee3-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="32ee3-115">Параметр -ShowStepsOnly можно только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="32ee3-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="32ee3-116">Пример 5</span><span class="sxs-lookup"><span data-stu-id="32ee3-116">Example 5</span></span>

<span data-ttu-id="32ee3-117">В следующем примере создаются файлы конфигурации для каждого шага развертывания на сервере размещения.</span><span class="sxs-lookup"><span data-stu-id="32ee3-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="32ee3-118">Файлы конфигурации сохраняются в папке \< ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig на сервере хост-сервера:</span><span class="sxs-lookup"><span data-stu-id="32ee3-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="32ee3-119">Чтобы определить корень устройства, запустите Get-CcApplianceDirectory устройства.</span><span class="sxs-lookup"><span data-stu-id="32ee3-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="32ee3-120">Пример 6</span><span class="sxs-lookup"><span data-stu-id="32ee3-120">Example 6</span></span>

<span data-ttu-id="32ee3-121">В следующем примере Cloud Connector выполняет шаги развертывания 1, 2 и 3 для создания виртуальных коммутаторов, создания виртуальной машины AD и установки службы домена на сервере AD.</span><span class="sxs-lookup"><span data-stu-id="32ee3-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="32ee3-122">Если шаг уже выполнен, он пропускает этот шаг:</span><span class="sxs-lookup"><span data-stu-id="32ee3-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="32ee3-123">Параметр SkipExistingObjects необходимо использовать вместе с параметром Steps.</span><span class="sxs-lookup"><span data-stu-id="32ee3-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="32ee3-124">Параметр Steps предназначен только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="32ee3-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="32ee3-125">Не используйте этот параметр для развертывания устройства или обновления устройства, которое находится в службе.</span><span class="sxs-lookup"><span data-stu-id="32ee3-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="32ee3-126">Чтобы определить этапы развертывания, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="32ee3-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="32ee3-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="32ee3-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="32ee3-128">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="32ee3-128">Detailed Description</span></span>
<span data-ttu-id="32ee3-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="32ee3-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="32ee3-130">Этот Install-CcAppliance используется для развертывания Cloud Connector на новом устройстве или обновления существующего устройства до последней версии.</span><span class="sxs-lookup"><span data-stu-id="32ee3-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="32ee3-131">Если у вас новое устройство, обязательно прочитайте статью "Подготовка среды для Cloud Connector", запустите Register-CcAppliance для регистрации устройства, а затем запустите Install-CcAppliance-</span><span class="sxs-lookup"><span data-stu-id="32ee3-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="32ee3-132">Дополнительные сведения см. в сведениях о развертывании одного сайта в [Cloud Connector](deploy-a-single-site-in-cloud-connector.md) и развертывании нескольких сайтов [в Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="32ee3-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="32ee3-133">Если у вас есть существующее развертывание Cloud Connector и вы хотите обновить его, следуйте инструкциям в окне "Обновление до новой версии [Cloud Connector".](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="32ee3-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="32ee3-134">Параметры</span><span class="sxs-lookup"><span data-stu-id="32ee3-134">Parameters</span></span>
<span data-ttu-id="32ee3-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="32ee3-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="32ee3-136">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="32ee3-136">**Parameter**</span></span>|<span data-ttu-id="32ee3-137">**Required**</span><span class="sxs-lookup"><span data-stu-id="32ee3-137">**Required**</span></span>|<span data-ttu-id="32ee3-138">**Тип**</span><span class="sxs-lookup"><span data-stu-id="32ee3-138">**Type**</span></span>|<span data-ttu-id="32ee3-139">**Описание**</span><span class="sxs-lookup"><span data-stu-id="32ee3-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32ee3-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="32ee3-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="32ee3-141">Необязательный</span><span class="sxs-lookup"><span data-stu-id="32ee3-141">Optional</span></span>  <br/> |<span data-ttu-id="32ee3-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="32ee3-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="32ee3-143">Создание файлов конфигурации для каждого шага развертывания.</span><span class="sxs-lookup"><span data-stu-id="32ee3-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="32ee3-144">Этот параметр только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="32ee3-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="32ee3-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="32ee3-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="32ee3-146">Необязательный</span><span class="sxs-lookup"><span data-stu-id="32ee3-146">Optional</span></span>  <br/> |<span data-ttu-id="32ee3-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="32ee3-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="32ee3-148">Отображает только имена этапов развертывания.</span><span class="sxs-lookup"><span data-stu-id="32ee3-148">Display deployment step names only.</span></span> <span data-ttu-id="32ee3-149">Этот параметр только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="32ee3-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="32ee3-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="32ee3-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="32ee3-151">Необязательный</span><span class="sxs-lookup"><span data-stu-id="32ee3-151">Optional</span></span>  <br/> |<span data-ttu-id="32ee3-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="32ee3-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="32ee3-153">Этот параметр необходимо использовать вместе с параметром Steps.</span><span class="sxs-lookup"><span data-stu-id="32ee3-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="32ee3-154">Этот параметр только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="32ee3-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="32ee3-155">Действия</span><span class="sxs-lookup"><span data-stu-id="32ee3-155">Steps</span></span>  <br/> |<span data-ttu-id="32ee3-156">Необязательна</span><span class="sxs-lookup"><span data-stu-id="32ee3-156">Optional</span></span>  <br/> |<span data-ttu-id="32ee3-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="32ee3-157">System.Array</span></span>  <br/> |<span data-ttu-id="32ee3-158">Запустите этапы развертывания.</span><span class="sxs-lookup"><span data-stu-id="32ee3-158">Run the deployment steps.</span></span> <span data-ttu-id="32ee3-159">Этот параметр только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="32ee3-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="32ee3-160">Обновление</span><span class="sxs-lookup"><span data-stu-id="32ee3-160">Upgrade</span></span>  <br/> |<span data-ttu-id="32ee3-161">Необязательный</span><span class="sxs-lookup"><span data-stu-id="32ee3-161">Optional</span></span>  <br/> |<span data-ttu-id="32ee3-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="32ee3-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="32ee3-163">Обновите существующий Cloud Connector до последней версии.</span><span class="sxs-lookup"><span data-stu-id="32ee3-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="32ee3-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="32ee3-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="32ee3-165">Необязательный</span><span class="sxs-lookup"><span data-stu-id="32ee3-165">Optional</span></span>  <br/> |<span data-ttu-id="32ee3-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="32ee3-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="32ee3-167">Удалите все учетные данные Cloud Connector в кэше.</span><span class="sxs-lookup"><span data-stu-id="32ee3-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="32ee3-168">Запрос пользователя на указание новых учетных данных для установки.</span><span class="sxs-lookup"><span data-stu-id="32ee3-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="32ee3-169">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="32ee3-169">Input Types</span></span>
<span data-ttu-id="32ee3-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="32ee3-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="32ee3-171">Нет.</span><span class="sxs-lookup"><span data-stu-id="32ee3-171">None.</span></span> <span data-ttu-id="32ee3-172">Этот Install-CcAppliance не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="32ee3-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="32ee3-173">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="32ee3-173">Return Types</span></span>
<span data-ttu-id="32ee3-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="32ee3-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="32ee3-175">Нет</span><span class="sxs-lookup"><span data-stu-id="32ee3-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="32ee3-176">См. также</span><span class="sxs-lookup"><span data-stu-id="32ee3-176">See also</span></span>
<span data-ttu-id="32ee3-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="32ee3-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="32ee3-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="32ee3-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="32ee3-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="32ee3-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="32ee3-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="32ee3-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="32ee3-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="32ee3-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

