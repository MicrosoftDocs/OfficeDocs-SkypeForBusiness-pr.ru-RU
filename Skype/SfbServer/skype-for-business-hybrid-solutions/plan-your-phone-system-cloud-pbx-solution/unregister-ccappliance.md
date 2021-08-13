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
description: Этот Unregister-CcAppliance не зарегистририт текущий Skype для бизнеса Cloud Connector Edition с сайта PSTN в конфигурации онлайн-клиента.
ms.openlocfilehash: de872082f6a025a736b871a76d41061c888acb1f401739229ba7ad670a0c19ce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344548"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Этот Unregister-CcAppliance не зарегистририт текущий Skype для бизнеса Cloud Connector Edition с сайта PSTN в конфигурации онлайн-клиента.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере отрегистрация текущего устройства из конфигурации клиента в Интернете:
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере проверяется конфигурация для локальной регистрации без подключения к конфигурации клиента в Интернете:
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Пример 3

В следующем примере unregisters текущего устройства с именем "Appliance1" на сайте PSTN "Site1":
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Как и Register-CcAppliance, имя сайта в сочетании с внешним FQDN Edge Server в файле CloudConnector.ini считается идентификатором сайта PSTN. Кроме того, имя applianceName в сочетании с идентификатором сервера-посредника в файле CloudConnector.ini считается идентификатором устройства.
  
После незарегистрации устройства перезапустите службу управления облачным соединитетелем и войдите в качестве учетной записи NetworkService.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Имя сайта <br/> |Необязательный  <br/> |System.String  <br/> |Имя сайта PSTN, где зарегистрирован прибор. Значение по умолчанию — это значение SiteName в CloudConnector.ini файле.  <br/> |
|ApplianceName  <br/> |Необязательный  <br/> |System.String  <br/> |Имя текущего устройства. Значение по умолчанию — это имя компьютера хост-сервера.  <br/> |
|Локальный  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Проверьте конфигурацию для локальной регистрации без подключения к конфигурации клиента в Интернете.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Unregister-CcAppliance не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

