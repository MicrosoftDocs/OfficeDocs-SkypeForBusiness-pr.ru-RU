---
title: Публикация CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла.
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a><span data-ttu-id="d4a57-103">Публикация CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d4a57-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="d4a57-104">Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла.</span><span class="sxs-lookup"><span data-stu-id="d4a57-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="d4a57-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4a57-105">Parameters</span></span>

<span data-ttu-id="d4a57-106">Нет</span><span class="sxs-lookup"><span data-stu-id="d4a57-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d4a57-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="d4a57-107">Examples</span></span>
<span data-ttu-id="d4a57-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a57-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="d4a57-109">Пример 1</span><span class="sxs-lookup"><span data-stu-id="d4a57-109">Example 1</span></span>

<span data-ttu-id="d4a57-110">В следующем примере возвращает сведения о высокой доступности из конфигурации сети клиентов и публикуется в облаке соединителя устройство на хост-сервера:</span><span class="sxs-lookup"><span data-stu-id="d4a57-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="d4a57-111">Подробное описание</span><span class="sxs-lookup"><span data-stu-id="d4a57-111">Detailed Description</span></span>
<span data-ttu-id="d4a57-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a57-112"></span></span>

<span data-ttu-id="d4a57-p101">В сведениях о высокой доступности содержатся полные доменные имена и IP-адреса серверов-посредников для сайта ТСОП. На сервер Active Directory добавляется новая запись DNS A для IP-адресов сервера-посредника. Полные доменные имена сервера центрального хранилища управления и сервера-посредника обновляются в соответствии с новыми элементами топологии. </span><span class="sxs-lookup"><span data-stu-id="d4a57-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="d4a57-116">Типы входных данных</span><span class="sxs-lookup"><span data-stu-id="d4a57-116">Input Types</span></span>
<span data-ttu-id="d4a57-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a57-117"></span></span>

<span data-ttu-id="d4a57-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="d4a57-118">None.</span></span> <span data-ttu-id="d4a57-119">Командлет Publish-CcAppliance не принимает входные данные по конвейеру.</span><span class="sxs-lookup"><span data-stu-id="d4a57-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d4a57-120">Типы возвращаемых данных</span><span class="sxs-lookup"><span data-stu-id="d4a57-120">Return Types</span></span>
<span data-ttu-id="d4a57-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a57-121"></span></span>

<span data-ttu-id="d4a57-122">Нет</span><span class="sxs-lookup"><span data-stu-id="d4a57-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4a57-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d4a57-123">See also</span></span>
<span data-ttu-id="d4a57-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d4a57-124"></span></span>

[<span data-ttu-id="d4a57-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d4a57-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d4a57-126">Удаление CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d4a57-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="d4a57-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d4a57-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d4a57-128">Отмена регистрации CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d4a57-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

