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
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла.
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287162"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="fe5a3-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe5a3-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="fe5a3-104">Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="fe5a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe5a3-105">Parameters</span></span>

<span data-ttu-id="fe5a3-106">Нет</span><span class="sxs-lookup"><span data-stu-id="fe5a3-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="fe5a3-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="fe5a3-107">Examples</span></span>
<span data-ttu-id="fe5a3-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fe5a3-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="fe5a3-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="fe5a3-109">Example 1</span></span>

<span data-ttu-id="fe5a3-110">В следующем примере показано получение сведений о высокой доступности из конфигурации Интернет-клиента и его публикация на устройстве облачного соединителя на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="fe5a3-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="fe5a3-111">Detailed Description</span></span>
<span data-ttu-id="fe5a3-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fe5a3-112"></span></span>

<span data-ttu-id="fe5a3-p101">В сведениях о высокой доступности содержатся полные доменные имена и IP-адреса серверов-посредников для сайта ТСОП. На сервер Active Directory добавляется новая запись DNS A для IP-адресов сервера-посредника. Полные доменные имена сервера центрального хранилища управления и сервера-посредника обновляются в соответствии с новыми элементами топологии. </span><span class="sxs-lookup"><span data-stu-id="fe5a3-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="fe5a3-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="fe5a3-116">Input Types</span></span>
<span data-ttu-id="fe5a3-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe5a3-117"></span></span>

<span data-ttu-id="fe5a3-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-118">None.</span></span> <span data-ttu-id="fe5a3-119">Командлет Publish-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fe5a3-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="fe5a3-120">Return Types</span></span>
<span data-ttu-id="fe5a3-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe5a3-121"></span></span>

<span data-ttu-id="fe5a3-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="fe5a3-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe5a3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="fe5a3-123">See also</span></span>
<span data-ttu-id="fe5a3-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe5a3-124"></span></span>

[<span data-ttu-id="fe5a3-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe5a3-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="fe5a3-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe5a3-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="fe5a3-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe5a3-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="fe5a3-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="fe5a3-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

