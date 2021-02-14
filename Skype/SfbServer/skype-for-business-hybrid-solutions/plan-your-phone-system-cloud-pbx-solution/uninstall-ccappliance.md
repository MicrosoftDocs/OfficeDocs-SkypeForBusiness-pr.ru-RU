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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: С помощью Uninstall-CcAppliance-сервера с хост-сервера будет выгрузка запущенного устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824143"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="3ac86-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3ac86-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="3ac86-104">С помощью Uninstall-CcAppliance-сервера с хост-сервера будет выгрузка запущенного устройства Skype для бизнеса Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="3ac86-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3ac86-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="3ac86-105">Examples</span></span>
<span data-ttu-id="3ac86-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3ac86-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3ac86-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="3ac86-107">Example 1</span></span>

<span data-ttu-id="3ac86-108">В следующем примере устройство Cloud Connector с сервера хост-сервера будет разрядлено и выгрузлено:</span><span class="sxs-lookup"><span data-stu-id="3ac86-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="3ac86-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="3ac86-109">Example 2</span></span>

<span data-ttu-id="3ac86-110">В следующем примере на хост-сервере происходит принудительное истощается запущенное устройство Cloud Connector, даже если процесс утечки не удался:</span><span class="sxs-lookup"><span data-stu-id="3ac86-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="3ac86-111">Пример 3</span><span class="sxs-lookup"><span data-stu-id="3ac86-111">Example 3</span></span>

<span data-ttu-id="3ac86-112">В следующем примере пошаговая версия резервной копии Cloud Connector будет без подтверждения пользователя:</span><span class="sxs-lookup"><span data-stu-id="3ac86-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="3ac86-113">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3ac86-113">Detailed Description</span></span>
<span data-ttu-id="3ac86-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3ac86-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3ac86-115">Если вы укажете текущую запущенную версию Cloud Connector, на сервере-посреднике и на сервере-посреднике сначала будут запущены службы опустынения, чтобы завершиться выполнение одновременно работающих вызовов перед тем, как они будут выгружены виртуальными машинами.</span><span class="sxs-lookup"><span data-stu-id="3ac86-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="3ac86-116">При выполнении стирания резервной версии не выполняется сток.</span><span class="sxs-lookup"><span data-stu-id="3ac86-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3ac86-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ac86-117">Parameters</span></span>
<span data-ttu-id="3ac86-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3ac86-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="3ac86-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="3ac86-119">**Parameter**</span></span>|<span data-ttu-id="3ac86-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="3ac86-120">**Required**</span></span>|<span data-ttu-id="3ac86-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3ac86-121">**Type**</span></span>|<span data-ttu-id="3ac86-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="3ac86-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3ac86-123">Версия</span><span class="sxs-lookup"><span data-stu-id="3ac86-123">Version</span></span> <br/> | <span data-ttu-id="3ac86-124">Необязательный</span><span class="sxs-lookup"><span data-stu-id="3ac86-124">Optional</span></span> <br/> |<span data-ttu-id="3ac86-125">System.String</span><span class="sxs-lookup"><span data-stu-id="3ac86-125">System.String</span></span>  <br/> | <span data-ttu-id="3ac86-126">Версия Cloud Connector, которая будет выгрузлена с хост-сервера.</span><span class="sxs-lookup"><span data-stu-id="3ac86-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="3ac86-127">Если он не указан, удалить текущую запущенную версию.</span><span class="sxs-lookup"><span data-stu-id="3ac86-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="3ac86-128">Force</span><span class="sxs-lookup"><span data-stu-id="3ac86-128">Force</span></span>  <br/> |<span data-ttu-id="3ac86-129">Необязательный</span><span class="sxs-lookup"><span data-stu-id="3ac86-129">Optional</span></span>  <br/> |<span data-ttu-id="3ac86-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3ac86-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3ac86-131">При этом необходимо попытаться оцедить серверы на сервере-посреднике и на сервере-посреднике, прежде чем выгрузить виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="3ac86-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="3ac86-132">Если указать переключатель Force, даже если службы разгрузки не будут работать, виртуальные машины будут выгрузки.</span><span class="sxs-lookup"><span data-stu-id="3ac86-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="3ac86-133">Этот параметр используется только для того, чтобы удалить текущую запущенную версию.</span><span class="sxs-lookup"><span data-stu-id="3ac86-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="3ac86-134">Подтверждение</span><span class="sxs-lookup"><span data-stu-id="3ac86-134">Confirm</span></span>  <br/> |<span data-ttu-id="3ac86-135">Необязательный</span><span class="sxs-lookup"><span data-stu-id="3ac86-135">Optional</span></span>  <br/> |<span data-ttu-id="3ac86-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3ac86-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3ac86-137">Попросите пользователя подтвердить удалить виртуальные машины.</span><span class="sxs-lookup"><span data-stu-id="3ac86-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="3ac86-138">Значение по умолчанию — TRUE.</span><span class="sxs-lookup"><span data-stu-id="3ac86-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3ac86-139">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="3ac86-139">Input Types</span></span>
<span data-ttu-id="3ac86-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3ac86-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3ac86-141">Нет.</span><span class="sxs-lookup"><span data-stu-id="3ac86-141">None.</span></span> <span data-ttu-id="3ac86-142">Этот Uninstall-CcAppliance не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="3ac86-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3ac86-143">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="3ac86-143">Return Types</span></span>
<span data-ttu-id="3ac86-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3ac86-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3ac86-145">Нет</span><span class="sxs-lookup"><span data-stu-id="3ac86-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ac86-146">См. также</span><span class="sxs-lookup"><span data-stu-id="3ac86-146">See also</span></span>
<span data-ttu-id="3ac86-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3ac86-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3ac86-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3ac86-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="3ac86-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3ac86-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="3ac86-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3ac86-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="3ac86-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3ac86-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

