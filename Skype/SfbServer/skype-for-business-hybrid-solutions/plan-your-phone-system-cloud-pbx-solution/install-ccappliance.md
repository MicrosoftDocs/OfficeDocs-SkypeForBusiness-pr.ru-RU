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
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Командлет Install-CcAppliance устанавливает на сервер узла устройство Skype для бизнеса Cloud Connector Edition, включая виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера.
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287274"
---
# <a name="install-ccappliance"></a><span data-ttu-id="da875-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="da875-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="da875-104">Командлет Install-CcAppliance устанавливает на сервер узла устройство Skype для бизнеса Cloud Connector Edition, включая виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="da875-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="da875-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="da875-105">Examples</span></span>
<span data-ttu-id="da875-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="da875-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="da875-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="da875-107">Example 1</span></span>

<span data-ttu-id="da875-108">В следующем примере показано, как установить новое управляющее устройство облачного соединителя на сервере узла:</span><span class="sxs-lookup"><span data-stu-id="da875-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="da875-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="da875-109">Example 2</span></span>

<span data-ttu-id="da875-110">Следующий пример обновляет облачный соединитель до последней версии:</span><span class="sxs-lookup"><span data-stu-id="da875-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="da875-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="da875-111">Example 3</span></span>

<span data-ttu-id="da875-112">Следующий пример удаляет все учетные данные облачного соединителя, кэшированные на сервере узла, предложит пользователю снова указать все учетные данные, а затем установит облачный соединитель:</span><span class="sxs-lookup"><span data-stu-id="da875-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="da875-113">Пример 4</span><span class="sxs-lookup"><span data-stu-id="da875-113">Example 4</span></span>

<span data-ttu-id="da875-114">В следующем примере в консоли PowerShell выводятся все шаги по развертыванию:</span><span class="sxs-lookup"><span data-stu-id="da875-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="da875-115">Параметр -ShowStepsOnly используется только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="da875-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="da875-116">Пример 5</span><span class="sxs-lookup"><span data-stu-id="da875-116">Example 5</span></span>

<span data-ttu-id="da875-117">В следующем примере создаются файлы конфигурации для каждого шага развертывания на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="da875-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="da875-118">Файлы конфигурации сохраняются в \<папке апплианцерут\>\инстанцес\\_лт_версион\>-дефаулт\експортедконфиг на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="da875-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="da875-119">Чтобы определить корневой каталог устройства, выполните командлет Get-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="da875-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="da875-120">Пример 6</span><span class="sxs-lookup"><span data-stu-id="da875-120">Example 6</span></span>

<span data-ttu-id="da875-p102">В следующем примере Cloud Connector выполняет шаги развертывания 1, 2 и 3, создавая виртуальные коммутаторы и виртуальные машины Active Directory, после чего устанавливая службу домена на сервер Active Directory. Если шаг уже был выполнен ранее, он пропускается:</span><span class="sxs-lookup"><span data-stu-id="da875-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="da875-123">Вместе с параметром Steps необходимо использовать параметр SkipExistingObjects.</span><span class="sxs-lookup"><span data-stu-id="da875-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da875-124">Параметр Steps используется только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="da875-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="da875-125">Не используйте этот параметр для развертывания нового или обновления работающего устройства.</span><span class="sxs-lookup"><span data-stu-id="da875-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="da875-126">Чтобы определить шаги развертывания, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="da875-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="da875-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="da875-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="da875-128">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="da875-128">Detailed Description</span></span>
<span data-ttu-id="da875-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="da875-129"></span></span>

<span data-ttu-id="da875-130">Командлет Install-Ккапплианце используется для развертывания облачного соединителя на новом устройстве или для обновления существующего устройства до последней версии.</span><span class="sxs-lookup"><span data-stu-id="da875-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="da875-131">При наличии нового устройства убедитесь в том, что сначала нужно подготовить среду для работы с облаком, а затем выполните командлет Register-Ккапплианце для регистрации устройства, а затем запустите командлет Install-Ккапплианце.</span><span class="sxs-lookup"><span data-stu-id="da875-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="da875-132">Дополнительные сведения можно найти [в разделе Развертывание одного сайта в облачном соединителе](deploy-a-single-site-in-cloud-connector.md) и [развертывание нескольких сайтов в облачном соединителе](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="da875-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="da875-133">Если у вас есть существующее развертывание облачного соединителя и вы хотите обновить его, выполните инструкции в разделе [обновление до новой версии облачного соединителя](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="da875-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="da875-134">Параметры</span><span class="sxs-lookup"><span data-stu-id="da875-134">Parameters</span></span>
<span data-ttu-id="da875-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="da875-135"></span></span>

|<span data-ttu-id="da875-136">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="da875-136">**Parameter**</span></span>|<span data-ttu-id="da875-137">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="da875-137">**Required**</span></span>|<span data-ttu-id="da875-138">**Тип**</span><span class="sxs-lookup"><span data-stu-id="da875-138">**Type**</span></span>|<span data-ttu-id="da875-139">**Описание**</span><span class="sxs-lookup"><span data-stu-id="da875-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da875-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="da875-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="da875-141">Необязательно</span><span class="sxs-lookup"><span data-stu-id="da875-141">Optional</span></span>  <br/> |<span data-ttu-id="da875-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="da875-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="da875-p105">Создает файлы конфигурации для каждого шага развертывания. Этот параметр используется только для устранения неполадок. </span><span class="sxs-lookup"><span data-stu-id="da875-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="da875-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="da875-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="da875-146">Необязательно</span><span class="sxs-lookup"><span data-stu-id="da875-146">Optional</span></span>  <br/> |<span data-ttu-id="da875-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="da875-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="da875-p106">Отображает только названия шагов развертывания. Этот параметр используется только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="da875-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="da875-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="da875-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="da875-151">Необязательно</span><span class="sxs-lookup"><span data-stu-id="da875-151">Optional</span></span>  <br/> |<span data-ttu-id="da875-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="da875-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="da875-p107">Этот параметр используется вместе с параметром Steps. Этот параметр используется только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="da875-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="da875-155">Steps</span><span class="sxs-lookup"><span data-stu-id="da875-155">Steps</span></span>  <br/> |<span data-ttu-id="da875-156">Необязательно </span><span class="sxs-lookup"><span data-stu-id="da875-156">Optional</span></span>  <br/> |<span data-ttu-id="da875-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="da875-157">System.Array</span></span>  <br/> |<span data-ttu-id="da875-p108">Выполняет шаги развертывания. Этот параметр используется только для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="da875-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="da875-160">Upgrade</span><span class="sxs-lookup"><span data-stu-id="da875-160">Upgrade</span></span>  <br/> |<span data-ttu-id="da875-161">Необязательно</span><span class="sxs-lookup"><span data-stu-id="da875-161">Optional</span></span>  <br/> |<span data-ttu-id="da875-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="da875-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="da875-163">Обновляет существующее развертывание Cloud Connector до последней версии.</span><span class="sxs-lookup"><span data-stu-id="da875-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="da875-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="da875-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="da875-165">Необязательно</span><span class="sxs-lookup"><span data-stu-id="da875-165">Optional</span></span>  <br/> |<span data-ttu-id="da875-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="da875-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="da875-167">Удалите все учетные данные облачного соединителя из кэша.</span><span class="sxs-lookup"><span data-stu-id="da875-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="da875-168">Отображает запрос для ввода пользователем новых учетных данных для установки.</span><span class="sxs-lookup"><span data-stu-id="da875-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="da875-169">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="da875-169">Input Types</span></span>
<span data-ttu-id="da875-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="da875-170"></span></span>

<span data-ttu-id="da875-p110">Нет. Командлет Install-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="da875-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="da875-173">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="da875-173">Return Types</span></span>
<span data-ttu-id="da875-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="da875-174"></span></span>

<span data-ttu-id="da875-175">Нет</span><span class="sxs-lookup"><span data-stu-id="da875-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da875-176">См. также</span><span class="sxs-lookup"><span data-stu-id="da875-176">See also</span></span>
<span data-ttu-id="da875-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="da875-177"></span></span>

[<span data-ttu-id="da875-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="da875-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="da875-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="da875-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="da875-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="da875-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="da875-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="da875-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

