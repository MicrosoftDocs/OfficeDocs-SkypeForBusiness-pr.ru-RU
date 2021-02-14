---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Этот Switch-CcVersion отключает запущенные устройства и переключается на новое развертывание или резервное устройство.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824153"
---
# <a name="switch-ccversion"></a><span data-ttu-id="de7c4-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="de7c4-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="de7c4-104">Этот Switch-CcVersion отключает запущенные устройства и переключается на новое развертывание или резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="de7c4-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="de7c4-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="de7c4-105">Examples</span></span>
<span data-ttu-id="de7c4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="de7c4-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="de7c4-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="de7c4-107">Example 1</span></span>

<span data-ttu-id="de7c4-108">В следующем примере службы текущего запущенного устройства разрядяются, а затем переключаются на только что развернутые или резервные устройства.</span><span class="sxs-lookup"><span data-stu-id="de7c4-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="de7c4-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="de7c4-109">Example 2</span></span>

<span data-ttu-id="de7c4-110">В следующем примере службы текущего запущенного устройства и принудительно останавливаются в случае сбойной работы служб.</span><span class="sxs-lookup"><span data-stu-id="de7c4-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="de7c4-111">Затем команда переключается на новое развертывание или резервное устройство:</span><span class="sxs-lookup"><span data-stu-id="de7c4-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="de7c4-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="de7c4-112">Detailed Description</span></span>
<span data-ttu-id="de7c4-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="de7c4-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="de7c4-114">Этот Switch-CcVersion истощает службы Cloud Connector на сервере-посреднике и на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="de7c4-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="de7c4-115">Все запущенные вызовы будут завершены, но устройство отклоняет все новые вызовы.</span><span class="sxs-lookup"><span data-stu-id="de7c4-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="de7c4-116">После этого он отключает запущенные устройства от корпоративной сети и интернет-сетей, отключает все виртуальные машины, принадлежащие устройству, а затем подключает устройство резервного копирования к корпоративным и интернет-сетям.</span><span class="sxs-lookup"><span data-stu-id="de7c4-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="de7c4-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="de7c4-117">Parameters</span></span>
<span data-ttu-id="de7c4-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="de7c4-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="de7c4-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="de7c4-119">**Parameter**</span></span>|<span data-ttu-id="de7c4-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="de7c4-120">**Required**</span></span>|<span data-ttu-id="de7c4-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="de7c4-121">**Type**</span></span>|<span data-ttu-id="de7c4-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="de7c4-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="de7c4-123">Force</span><span class="sxs-lookup"><span data-stu-id="de7c4-123">Force</span></span> <br/> | <span data-ttu-id="de7c4-124">Необязательный</span><span class="sxs-lookup"><span data-stu-id="de7c4-124">Optional</span></span> <br/> |<span data-ttu-id="de7c4-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="de7c4-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="de7c4-126">Принудительно останавливает службы в случае сбой их ливни.</span><span class="sxs-lookup"><span data-stu-id="de7c4-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="de7c4-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="de7c4-127">Input Types</span></span>
<span data-ttu-id="de7c4-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de7c4-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="de7c4-129">Нет</span><span class="sxs-lookup"><span data-stu-id="de7c4-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="de7c4-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="de7c4-130">Return Types</span></span>
<span data-ttu-id="de7c4-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de7c4-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="de7c4-132">Нет</span><span class="sxs-lookup"><span data-stu-id="de7c4-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de7c4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="de7c4-133">See also</span></span>
<span data-ttu-id="de7c4-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="de7c4-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="de7c4-135">Нет</span><span class="sxs-lookup"><span data-stu-id="de7c4-135">None</span></span>
  

