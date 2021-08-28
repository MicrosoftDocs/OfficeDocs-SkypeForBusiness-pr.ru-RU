---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Этот Register-CcAppliance регистрирует сведения о устройстве на сайтЕ PSTN в конфигурации клиента в Интернете. Перед развертыванием и управлением устройством должна быть зарегистрирована служба Skype для бизнеса Cloud Connector Edition управления.
ms.openlocfilehash: 159e74f91ca26cd0f8bdd214c9cd6ac45b5c1196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589963"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Этот Register-CcAppliance регистрирует сведения о устройстве на сайтЕ PSTN в конфигурации клиента в Интернете. Перед развертыванием и управлением устройством должна быть зарегистрирована служба Skype для бизнеса Cloud Connector Edition управления.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере регистрируются текущие сведения о устройстве в конфигурации клиента в Интернете:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере проверяется конфигурация регистрации локально без подключения к конфигурации клиента в Интернете:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Пример 3

В следующем примере регистрируется текущий прибор с именем "Appliance1" на сайте PSTN "Site1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Необходимо предоставить имя и пароль учетной записи администратора клиента. Используйте учетную запись, созданную для управления облачным подключением. 
  
В выпуске 1.4.2 и ранее следуйте инструкциям по предоставлению внешнего пароля сертификата, пароля администратора безопасного режима, пароля администратора домена и пароля администратора VM. 
  
В выпуске 2.0 и более поздней версии следуйте инструкциям по предоставлению внешнего пароля сертификата, пароля CceService и пароля CABackupFile.
  
По завершении регистрации перезапустите службу управления облачным соединитетелем и войдите в службы в качестве учетной записи CceService.
  
Имя сайта в сочетании с внешним FQDN Edge Server в CloudConnector.ini файл считается идентификатором сайта PSTN. Если для регистрации сайта не использовались ни имя сайта, ни внешний FQDN Edge Server, для этого устройства в конфигурации клиента в Интернете будет создан новый сайт. При обнаружении удостоверения сайта PSTN этот идентификатор будет применяться на сайте PSTN, и устройство будет зарегистрировано на этом сайте PSTN. 
  
В следующей ситуации, cmdlet не удастся и указать, что Site1 уже зарегистрирован: 
  
- SiteName — это Site1, а внешний FQDN edge Server — edgserver1.contoso.com. 
    
- A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.
    
- Сайт PSTN, имя сайта которого — внешний FQDN NewSite и Edge Server, edgserver1.contoso.com зарегистрирован. 
    
Имя applianceName в сочетании с FQDN-сервером-посредником в CloudConnector.ini файл считается идентификатором устройства. Если для регистрации устройства не было использовано имя applianceName или FQDN-сервера-посредника, в конфигурации клиента в Интернете будет создан новый прибор. Если устройство уже зарегистрировано, этот кодлет не будет работать.
  
В следующей ситуации, cmdlet не удастся и указать, что устройство уже зарегистрировано: 
  
- ApplianceName — это appliance1, а сервер-посредник FQDN ms1.vdomain.com.
    
- На текущем сайте PSTN, если устройство с именем Appliance1 и Mediation Server FQDN ms.vdomain.com или устройство, имя которого NewAppliance и mediation server FQDN ms1.vdomain.com было зарегистрировано.
    
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Имя сайта  <br/> |Необязательный  <br/> |System.String  <br/> |Имя сайта PSTN, на которое зарегистрирован прибор. Значение по умолчанию — это значение SiteName в CloudConnector.ini файле.  <br/> |
|ApplianceName  <br/> |Необязательный  <br/> |System.String  <br/> |Имя текущего устройства. Значение по умолчанию — это имя компьютера хост-сервера.  <br/> |
|Локальный  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Проверьте конфигурации для регистрации локально без подключения к конфигурации клиента в Интернете.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Register-CcAppliance не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

