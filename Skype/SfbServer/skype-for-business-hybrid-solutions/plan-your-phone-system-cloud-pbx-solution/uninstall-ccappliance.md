---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003149"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="f0947-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f0947-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="f0947-104">Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла. </span><span class="sxs-lookup"><span data-stu-id="f0947-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="f0947-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="f0947-105">Examples</span></span>
<span data-ttu-id="f0947-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f0947-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="f0947-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="f0947-107">Example 1</span></span>

<span data-ttu-id="f0947-108">В следующем примере выполняется сток и удаление управляющего устройства облачного соединителя с хостового сервера.</span><span class="sxs-lookup"><span data-stu-id="f0947-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="f0947-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="f0947-109">Example 2</span></span>

<span data-ttu-id="f0947-110">В следующем примере выполняется сток и принудительное удаление работающего устройства облачного соединителя на сервере узла, даже если процесс стока завершился сбоем.</span><span class="sxs-lookup"><span data-stu-id="f0947-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="f0947-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="f0947-111">Example 3</span></span>

<span data-ttu-id="f0947-112">В следующем примере удаляется резервная версия облачного соединителя без подтверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="f0947-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="f0947-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="f0947-113">Detailed Description</span></span>
<span data-ttu-id="f0947-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f0947-114"></span></span>

<span data-ttu-id="f0947-115">Если вы удаляете текущую работающую версию облачного соединителя, сначала выполняются службы стока на сервере и на пограничном сервере, чтобы начать одновременные звонки перед удалением виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="f0947-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="f0947-116">Если вы удаляете резервную версию, сток не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f0947-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f0947-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0947-117">Parameters</span></span>
<span data-ttu-id="f0947-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f0947-118"></span></span>

|<span data-ttu-id="f0947-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="f0947-119">**Parameter**</span></span>|<span data-ttu-id="f0947-120">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="f0947-120">**Required**</span></span>|<span data-ttu-id="f0947-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f0947-121">**Type**</span></span>|<span data-ttu-id="f0947-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f0947-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f0947-123">Версия</span><span class="sxs-lookup"><span data-stu-id="f0947-123">Version</span></span> <br/> | <span data-ttu-id="f0947-124">Необязательно </span><span class="sxs-lookup"><span data-stu-id="f0947-124">Optional</span></span> <br/> |<span data-ttu-id="f0947-125">System.String</span><span class="sxs-lookup"><span data-stu-id="f0947-125">System.String</span></span>  <br/> | <span data-ttu-id="f0947-126">Версия облачного соединителя, которая будет удалена с сервера узла.</span><span class="sxs-lookup"><span data-stu-id="f0947-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="f0947-127">Если этот параметр не задан, удаляется текущая версия.</span><span class="sxs-lookup"><span data-stu-id="f0947-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="f0947-128">Force</span><span class="sxs-lookup"><span data-stu-id="f0947-128">Force</span></span>  <br/> |<span data-ttu-id="f0947-129">Необязательный</span><span class="sxs-lookup"><span data-stu-id="f0947-129">Optional</span></span>  <br/> |<span data-ttu-id="f0947-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f0947-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="f0947-p103">При удалении текущей рабочей версии предпринимается попытка выполнить очистку на сервере-посреднике и пограничном сервере до удаления виртуальных машин. Если задан параметр "Force", виртуальные машины будут удалены даже в том случае, если работа служб очистки завершится сбоем. Этот параметр используется только для удаления текущей рабочей версии.</span><span class="sxs-lookup"><span data-stu-id="f0947-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="f0947-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="f0947-134">Confirm</span></span>  <br/> |<span data-ttu-id="f0947-135">Необязательно</span><span class="sxs-lookup"><span data-stu-id="f0947-135">Optional</span></span>  <br/> |<span data-ttu-id="f0947-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f0947-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="f0947-137">Запрашивать подтверждение пользователя, чтобы удалить виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="f0947-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="f0947-138">Значение по умолчанию: TRUE.</span><span class="sxs-lookup"><span data-stu-id="f0947-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f0947-139">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="f0947-139">Input Types</span></span>
<span data-ttu-id="f0947-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f0947-140"></span></span>

<span data-ttu-id="f0947-p105">Нет. Командлет Uninstall-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="f0947-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f0947-143">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="f0947-143">Return Types</span></span>
<span data-ttu-id="f0947-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f0947-144"></span></span>

<span data-ttu-id="f0947-145">Нет</span><span class="sxs-lookup"><span data-stu-id="f0947-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f0947-146">См. также</span><span class="sxs-lookup"><span data-stu-id="f0947-146">See also</span></span>
<span data-ttu-id="f0947-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f0947-147"></span></span>

[<span data-ttu-id="f0947-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f0947-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="f0947-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f0947-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="f0947-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f0947-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="f0947-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="f0947-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

