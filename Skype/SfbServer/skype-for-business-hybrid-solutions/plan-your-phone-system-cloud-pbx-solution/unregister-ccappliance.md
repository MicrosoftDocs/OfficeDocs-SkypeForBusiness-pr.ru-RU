---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Этот Unregister-CcAppliance регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition с сайта STN в конфигурации интерактивного клиента.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824133"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Этот Unregister-CcAppliance регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition с сайта STN в конфигурации интерактивного клиента.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере из конфигурации интерактивного клиента отрегистрировано текущее устройство:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере конфигурация проверяется на наличие локальной регистрации без подключения к конфигурации интерактивного клиента:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Пример 3

В следующем примере текущее устройство с именем Appliance1 будет отрегистрировано на сайте STN "Site1":
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Аналогично Register-CcAppliance, siteName в сочетании с внешним FQDN edge Server в CloudConnector.ini файле считается удостоверением сайта STN. Аналогичным образом, applianceName в сочетании с FQDN сервера-CloudConnector.ini в файле CloudConnector.ini считается удостоверением устройства.
  
После регистрации устройства перезапустите службу управления Cloud Connector и войдите в систему под учетной записью NetworkService.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Необязательный  <br/> |System.String  <br/> |Имя сайта STN, на котором зарегистрировано устройство. Значение по умолчанию — SiteName в CloudConnector.ini файле.  <br/> |
|ApplianceName  <br/> |Необязательный  <br/> |System.String  <br/> |Имя текущего устройства. Значение по умолчанию — имя компьютера хост-сервера.  <br/> |
|Локальный  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Проверьте конфигурацию регистрации локально, не подключаясь к конфигурации интерактивного клиента.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Unregister-CcAppliance не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

