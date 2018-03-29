---
title: Удаление CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла. '
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="17676-103">Удаление CcAppliance</span><span class="sxs-lookup"><span data-stu-id="17676-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="17676-104">Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла. </span><span class="sxs-lookup"><span data-stu-id="17676-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="17676-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="17676-105">Examples</span></span>
<span data-ttu-id="17676-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="17676-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="17676-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="17676-107">Example 1</span></span>

<span data-ttu-id="17676-108">В следующем примере извлекаются и удаляет appliance облачных соединителя с хост-сервера:</span><span class="sxs-lookup"><span data-stu-id="17676-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="17676-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="17676-109">Example 2</span></span>

<span data-ttu-id="17676-110">Далее примере извлекаются и принудительно удаляет выполняемого appliance облачных соединителя на хост-сервера, даже в том случае, если не удалось выполнить процесс обозначает:</span><span class="sxs-lookup"><span data-stu-id="17676-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="17676-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="17676-111">Example 3</span></span>

<span data-ttu-id="17676-112">Следующий пример удаляет в облаке соединителя резервной версии без запроса подтверждения пользователя:</span><span class="sxs-lookup"><span data-stu-id="17676-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="17676-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="17676-113">Detailed Description</span></span>
<span data-ttu-id="17676-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="17676-114"></span></span>

<span data-ttu-id="17676-115">При удалении текущей версии выполняемого соединителя облачных обозначает службы сначала выполняются на сервер-посредник и пограничного сервера, чтобы позволить одновременных звонков завершить перед удалением виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="17676-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="17676-116">При удалении резервной версии опустошения не выполняется.</span><span class="sxs-lookup"><span data-stu-id="17676-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="17676-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="17676-117">Parameters</span></span>
<span data-ttu-id="17676-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="17676-118"></span></span>

|<span data-ttu-id="17676-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="17676-119">**Parameter**</span></span>|<span data-ttu-id="17676-120">**Обязательно**</span><span class="sxs-lookup"><span data-stu-id="17676-120">**Required**</span></span>|<span data-ttu-id="17676-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="17676-121">**Type**</span></span>|<span data-ttu-id="17676-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="17676-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="17676-123">Версия</span><span class="sxs-lookup"><span data-stu-id="17676-123">Version</span></span> <br/> | <span data-ttu-id="17676-124">Необязательно</span><span class="sxs-lookup"><span data-stu-id="17676-124">Optional</span></span> <br/> |<span data-ttu-id="17676-125">System.String</span><span class="sxs-lookup"><span data-stu-id="17676-125">System.String</span></span>  <br/> | <span data-ttu-id="17676-126">Версия облачных соединитель, который будет удален из хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="17676-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="17676-127">Если этот параметр не задан, удаляется текущая версия.</span><span class="sxs-lookup"><span data-stu-id="17676-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="17676-128">Force</span><span class="sxs-lookup"><span data-stu-id="17676-128">Force</span></span>  <br/> |<span data-ttu-id="17676-129"> Необязательно</span><span class="sxs-lookup"><span data-stu-id="17676-129">Optional</span></span>  <br/> |<span data-ttu-id="17676-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="17676-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="17676-p103">При удалении текущей рабочей версии предпринимается попытка выполнить очистку на сервере-посреднике и пограничном сервере до удаления виртуальных машин. Если задан параметр "Force", виртуальные машины будут удалены даже в том случае, если работа служб очистки завершится сбоем. Этот параметр используется только для удаления текущей рабочей версии.</span><span class="sxs-lookup"><span data-stu-id="17676-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="17676-134">Confirm</span><span class="sxs-lookup"><span data-stu-id="17676-134">Confirm</span></span>  <br/> |<span data-ttu-id="17676-135">Необязательно</span><span class="sxs-lookup"><span data-stu-id="17676-135">Optional</span></span>  <br/> |<span data-ttu-id="17676-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="17676-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="17676-137">Запрос подтверждения пользователя для удаления виртуальных машин.</span><span class="sxs-lookup"><span data-stu-id="17676-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="17676-138">Значение по умолчанию: TRUE.</span><span class="sxs-lookup"><span data-stu-id="17676-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="17676-139">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="17676-139">Input Types</span></span>
<span data-ttu-id="17676-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17676-140"></span></span>

<span data-ttu-id="17676-p105">Нет. Командлет Uninstall-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="17676-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="17676-143">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="17676-143">Return Types</span></span>
<span data-ttu-id="17676-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17676-144"></span></span>

<span data-ttu-id="17676-145">Нет</span><span class="sxs-lookup"><span data-stu-id="17676-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17676-146">См. также</span><span class="sxs-lookup"><span data-stu-id="17676-146">See also</span></span>
<span data-ttu-id="17676-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="17676-147"></span></span>

[<span data-ttu-id="17676-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="17676-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="17676-149">Публикация CcAppliance</span><span class="sxs-lookup"><span data-stu-id="17676-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="17676-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="17676-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="17676-151">Отмена регистрации CcAppliance</span><span class="sxs-lookup"><span data-stu-id="17676-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

