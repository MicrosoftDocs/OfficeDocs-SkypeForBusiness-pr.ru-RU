---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: В Install-CcAppliance устанавливается Skype для бизнеса Cloud Connector Edition устройства, включая виртуальные машины AD, Central Management Store, Mediation Server и Edge Server.
ms.openlocfilehash: b88b869e3c30783a69bc16ab690a258506ebcc90e849eb474a17859140485e8d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343183"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
В Install-CcAppliance устанавливается Skype для бизнеса Cloud Connector Edition устройства, включая виртуальные машины AD, Central Management Store, Mediation Server и Edge Server. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере устанавливается новый прибор облачного соединителя на сервере хост-сервера:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере обновление облачного соединитетеля до последней версии:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Пример 3

В следующем примере удаляются все учетные данные облачного соединителя, кэшные на сервере хост-сервера, пользователь снова указывает все сведения о учетных данных, а затем устанавливает облачный соединитатель:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Пример 4

В следующем примере отображаются все этапы развертывания в консоли PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Параметр -ShowStepsOnly только для устранения неполадок.
  
### <a name="example-5"></a>Пример 5

В следующем примере создаются файлы конфигурации для каждого шага развертывания на хост-сервере. Файлы конфигурации сохраняются в \<ApplianceRoot\> папке \Instances \\<Version \> -default\ExportedConfig на хост-сервере:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Чтобы определить корень устройства, запустите Get-CcApplianceDirectory. 
  
### <a name="example-6"></a>Пример 6

В следующем примере cloud Connector выполняет этапы развертывания 1, 2 и 3 для создания виртуальных коммутаторов, создания виртуальной машины AD и установки службы домена на сервере AD. Он пропускает шаг, если шаг уже выполнен:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Параметр SkipExistingObjects должен использоваться в сочетании с параметром Steps.
  
> [!NOTE]
> Параметр Steps предназначен только для устранения неполадок. Не используйте этот параметр для развертывания устройства или обновления устройства, которое находится в службе. 
  
Чтобы определить этапы развертывания, запустите следующую команду:
  
Install-CcAppliance-ShowStepsOnly
  
## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Install-CcAppliance используется для развертывания облачного соединителя на новом устройстве или обновления существующего устройства до последней версии.
  
Если у вас новый прибор, сначала ознакомьтесь с подготовкой среды для облачного соединителя, запустите Register-CcAppliance для регистрации устройства, а затем запустите Install-CcAppliance. Дополнительные сведения см. в [веб-сайте Развертывание](deploy-a-single-site-in-cloud-connector.md) одного сайта в облачном соединители и развертывание нескольких сайтов [в облачном соединители.](deploy-multiple-sites-in-cloud-connector.md) 
  
Если у вас есть существующее развертывание облачного соединиттеля и вы хотите обновить, выполните инструкции в Обновлении до новой версии [облачного соединитетеля.](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> | Создание файлов конфигурации для каждого шага развертывания. Этот параметр только для устранения неполадок. <br/> |
|ShowStepsOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Отображаем только имена этапов развертывания. Этот параметр только для устранения неполадок.  <br/> |
|SkipExistingObjects  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Этот параметр должен использоваться в сочетании с параметром Steps. Этот параметр только для устранения неполадок.  <br/> |
|Действия  <br/> |Необязательный  <br/> |System.Array  <br/> |Запустите этапы развертывания. Этот параметр только для устранения неполадок.  <br/> |
|Обновление  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Обновление существующего облачного соединитетеля до последней версии.  <br/> |
|UpdateAllCredentials  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Удалите все учетные данные облачного соединитетеля в кэше. Покажите пользователю указать новые сведения об учетных данных для установки.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Install-CcAppliance не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

