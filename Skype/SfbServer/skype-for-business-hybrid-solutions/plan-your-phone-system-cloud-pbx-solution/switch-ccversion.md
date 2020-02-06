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
description: 'Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство. '
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824153"
---
# <a name="switch-ccversion"></a><span data-ttu-id="0b901-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="0b901-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="0b901-104">Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство. </span><span class="sxs-lookup"><span data-stu-id="0b901-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="0b901-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b901-105">Examples</span></span>
<span data-ttu-id="0b901-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0b901-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0b901-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="0b901-107">Example 1</span></span>

<span data-ttu-id="0b901-108">В следующем примере очищаются службы работающего устройства и выполняется переключение на только что развернутое или резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="0b901-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="0b901-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="0b901-109">Example 2</span></span>

<span data-ttu-id="0b901-110">В следующем примере очищаются службы работающего устройства, а в случае сбоя очистки службы принудительно останавливаются.</span><span class="sxs-lookup"><span data-stu-id="0b901-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="0b901-111">Затем эта команда выполняет переключение на только что развернутое или резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="0b901-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="0b901-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="0b901-112">Detailed Description</span></span>
<span data-ttu-id="0b901-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0b901-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="0b901-114">Командлет Switch-Ккверсион перестокует службы облачного соединителя на сервере-посреднике и пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="0b901-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="0b901-115">Все выполняемые звонки завершаются, а устройство будет отклонять любые новые звонки.</span><span class="sxs-lookup"><span data-stu-id="0b901-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="0b901-116">После очистки командлет отключает работающее устройство от корпоративной сети и Интернета, выключает все принадлежащие устройству виртуальные машины, после чего подключает к корпоративной сети и Интернету резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="0b901-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0b901-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b901-117">Parameters</span></span>
<span data-ttu-id="0b901-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0b901-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="0b901-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="0b901-119">**Parameter**</span></span>|<span data-ttu-id="0b901-120">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="0b901-120">**Required**</span></span>|<span data-ttu-id="0b901-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="0b901-121">**Type**</span></span>|<span data-ttu-id="0b901-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b901-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0b901-123">Force</span><span class="sxs-lookup"><span data-stu-id="0b901-123">Force</span></span> <br/> | <span data-ttu-id="0b901-124">Необязательно</span><span class="sxs-lookup"><span data-stu-id="0b901-124">Optional</span></span> <br/> |<span data-ttu-id="0b901-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0b901-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="0b901-126"> Принудительно останавливает службы при сбое их очистки.</span><span class="sxs-lookup"><span data-stu-id="0b901-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0b901-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="0b901-127">Input Types</span></span>
<span data-ttu-id="0b901-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b901-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="0b901-129">Нет</span><span class="sxs-lookup"><span data-stu-id="0b901-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0b901-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="0b901-130">Return Types</span></span>
<span data-ttu-id="0b901-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b901-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0b901-132">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0b901-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b901-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0b901-133">See also</span></span>
<span data-ttu-id="0b901-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0b901-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="0b901-135">Нет</span><span class="sxs-lookup"><span data-stu-id="0b901-135">None</span></span>
  

