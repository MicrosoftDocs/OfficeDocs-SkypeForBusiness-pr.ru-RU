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
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 'Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство. '
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003159"
---
# <a name="switch-ccversion"></a><span data-ttu-id="2dbf7-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="2dbf7-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="2dbf7-104">Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство. </span><span class="sxs-lookup"><span data-stu-id="2dbf7-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="2dbf7-105">Примеры</span><span class="sxs-lookup"><span data-stu-id="2dbf7-105">Examples</span></span>
<span data-ttu-id="2dbf7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2dbf7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="2dbf7-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="2dbf7-107">Example 1</span></span>

<span data-ttu-id="2dbf7-108">В следующем примере очищаются службы работающего устройства и выполняется переключение на только что развернутое или резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="2dbf7-109">Пример 2</span><span class="sxs-lookup"><span data-stu-id="2dbf7-109">Example 2</span></span>

<span data-ttu-id="2dbf7-110">В следующем примере очищаются службы работающего устройства, а в случае сбоя очистки службы принудительно останавливаются.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="2dbf7-111">Затем эта команда выполняет переключение на только что развернутое или резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="2dbf7-112">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="2dbf7-112">Detailed Description</span></span>
<span data-ttu-id="2dbf7-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2dbf7-113"></span></span>

<span data-ttu-id="2dbf7-114">Командлет Switch-Ккверсион перестокует службы облачного соединителя на сервере-посреднике и пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="2dbf7-115">Все выполняемые звонки завершаются, а устройство будет отклонять любые новые звонки.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="2dbf7-116">После очистки командлет отключает работающее устройство от корпоративной сети и Интернета, выключает все принадлежащие устройству виртуальные машины, после чего подключает к корпоративной сети и Интернету резервное устройство.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2dbf7-117">Параметры</span><span class="sxs-lookup"><span data-stu-id="2dbf7-117">Parameters</span></span>
<span data-ttu-id="2dbf7-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2dbf7-118"></span></span>

|<span data-ttu-id="2dbf7-119">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="2dbf7-119">**Parameter**</span></span>|<span data-ttu-id="2dbf7-120">**Обязательный**</span><span class="sxs-lookup"><span data-stu-id="2dbf7-120">**Required**</span></span>|<span data-ttu-id="2dbf7-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="2dbf7-121">**Type**</span></span>|<span data-ttu-id="2dbf7-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2dbf7-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2dbf7-123">Force</span><span class="sxs-lookup"><span data-stu-id="2dbf7-123">Force</span></span> <br/> | <span data-ttu-id="2dbf7-124">Необязательно</span><span class="sxs-lookup"><span data-stu-id="2dbf7-124">Optional</span></span> <br/> |<span data-ttu-id="2dbf7-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2dbf7-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="2dbf7-126"> Принудительно останавливает службы при сбое их очистки.</span><span class="sxs-lookup"><span data-stu-id="2dbf7-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2dbf7-127">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="2dbf7-127">Input Types</span></span>
<span data-ttu-id="2dbf7-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2dbf7-128"></span></span>

<span data-ttu-id="2dbf7-129">Нет</span><span class="sxs-lookup"><span data-stu-id="2dbf7-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2dbf7-130">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="2dbf7-130">Return Types</span></span>
<span data-ttu-id="2dbf7-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2dbf7-131"></span></span>

<span data-ttu-id="2dbf7-132">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="2dbf7-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dbf7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2dbf7-133">See also</span></span>
<span data-ttu-id="2dbf7-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2dbf7-134"></span></span>

<span data-ttu-id="2dbf7-135">Нет</span><span class="sxs-lookup"><span data-stu-id="2dbf7-135">None</span></span>
  

