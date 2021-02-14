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
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

Следующий пример получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Cloud Connector на сервере хост-сервера:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Сведения о высокой доступности содержат FQDN сервера-посредника и IP-адреса сайта STN. Новые записи A DNS добавляются на сервер AD для IP-адресов сервера-посредника. Новые элементы топологии обновляются в центральном хранилище управления для FQDNs и IP-адресов сервера-посредника. 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Publish-CcAppliance не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

