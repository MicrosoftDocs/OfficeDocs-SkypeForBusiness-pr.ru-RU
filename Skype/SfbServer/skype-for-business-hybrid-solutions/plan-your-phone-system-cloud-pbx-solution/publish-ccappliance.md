---
title: Publish-CcAppliance
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
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824315"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="3d9dd-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3d9dd-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="3d9dd-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span><span class="sxs-lookup"><span data-stu-id="3d9dd-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="3d9dd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d9dd-105">Parameters</span></span>

<span data-ttu-id="3d9dd-106">Нет</span><span class="sxs-lookup"><span data-stu-id="3d9dd-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3d9dd-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="3d9dd-107">Examples</span></span>
<span data-ttu-id="3d9dd-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d9dd-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3d9dd-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="3d9dd-109">Example 1</span></span>

<span data-ttu-id="3d9dd-110">Следующий пример получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Cloud Connector на сервере хост-сервера:</span><span class="sxs-lookup"><span data-stu-id="3d9dd-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="3d9dd-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="3d9dd-111">Detailed Description</span></span>
<span data-ttu-id="3d9dd-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3d9dd-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3d9dd-113">Сведения о высокой доступности содержат FQDN сервера-посредника и IP-адреса сайта STN.</span><span class="sxs-lookup"><span data-stu-id="3d9dd-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="3d9dd-114">Новые записи A DNS добавляются на сервер AD для IP-адресов сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="3d9dd-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="3d9dd-115">Новые элементы топологии обновляются в центральном хранилище управления для FQDNs и IP-адресов сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="3d9dd-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="3d9dd-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="3d9dd-116">Input Types</span></span>
<span data-ttu-id="3d9dd-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d9dd-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3d9dd-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="3d9dd-118">None.</span></span> <span data-ttu-id="3d9dd-119">Этот Publish-CcAppliance не принимает конвейерные входные данные.</span><span class="sxs-lookup"><span data-stu-id="3d9dd-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3d9dd-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="3d9dd-120">Return Types</span></span>
<span data-ttu-id="3d9dd-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d9dd-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3d9dd-122">Нет</span><span class="sxs-lookup"><span data-stu-id="3d9dd-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d9dd-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3d9dd-123">See also</span></span>
<span data-ttu-id="3d9dd-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d9dd-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3d9dd-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3d9dd-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="3d9dd-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3d9dd-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="3d9dd-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3d9dd-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="3d9dd-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="3d9dd-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

