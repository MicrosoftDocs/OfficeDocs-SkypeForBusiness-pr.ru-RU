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
description: Командлет Install-CcAppliance устанавливает на сервер узла устройство Skype для бизнеса Cloud Connector Edition, включая виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799879"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Командлет Install-CcAppliance устанавливает на сервер узла устройство Skype для бизнеса Cloud Connector Edition, включая виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показано, как установить новое управляющее устройство облачного соединителя на сервере узла:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Пример 2

Следующий пример обновляет облачный соединитель до последней версии:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Пример 3

Следующий пример удаляет все учетные данные облачного соединителя, кэшированные на сервере узла, предложит пользователю снова указать все учетные данные, а затем установит облачный соединитель:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Пример 4

В следующем примере в консоли PowerShell выводятся все шаги по развертыванию:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Параметр -ShowStepsOnly используется только для устранения неполадок.
  
### <a name="example-5"></a>Пример 5

В следующем примере создаются файлы конфигурации для каждого шага развертывания на сервере узла. Файлы конфигурации сохраняются в \<папке апплианцерут\>\Инстанцес\\<Version\>-дефаулт\експортедконфиг на сервере узла:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Чтобы определить корневой каталог устройства, выполните командлет Get-CcApplianceDirectory. 
  
### <a name="example-6"></a>Пример 6

В следующем примере Cloud Connector выполняет шаги развертывания 1, 2 и 3, создавая виртуальные коммутаторы и виртуальные машины Active Directory, после чего устанавливая службу домена на сервер Active Directory. Если шаг уже был выполнен ранее, он пропускается:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Вместе с параметром Steps необходимо использовать параметр SkipExistingObjects.
  
> [!NOTE]
> Параметр Steps используется только для устранения неполадок. Не используйте этот параметр для развертывания нового или обновления работающего устройства. 
  
Чтобы определить шаги развертывания, выполните следующий командлет:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Install-Ккапплианце используется для развертывания облачного соединителя на новом устройстве или для обновления существующего устройства до последней версии.
  
При наличии нового устройства убедитесь в том, что сначала нужно подготовить среду для работы с облаком, а затем выполните командлет Register-Ккапплианце для регистрации устройства, а затем запустите командлет Install-Ккапплианце. Дополнительные сведения можно найти [в разделе Развертывание одного сайта в облачном соединителе](deploy-a-single-site-in-cloud-connector.md) и [развертывание нескольких сайтов в облачном соединителе](deploy-multiple-sites-in-cloud-connector.md). 
  
Если у вас есть существующее развертывание облачного соединителя и вы хотите обновить его, выполните инструкции в разделе [обновление до новой версии облачного соединителя](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> | Создает файлы конфигурации для каждого шага развертывания. Этот параметр используется только для устранения неполадок.  <br/> |
|ShowStepsOnly  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Отображает только названия шагов развертывания. Этот параметр используется только для устранения неполадок.  <br/> |
|SkipExistingObjects  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Этот параметр используется вместе с параметром Steps. Этот параметр используется только для устранения неполадок.  <br/> |
|Steps  <br/> |Необязательно   <br/> |System.Array  <br/> |Выполняет шаги развертывания. Этот параметр используется только для устранения неполадок.  <br/> |
|Upgrade  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Обновляет существующее развертывание Cloud Connector до последней версии.  <br/> |
|UpdateAllCredentials  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Удалите все учетные данные облачного соединителя из кэша. Отображает запрос для ввода пользователем новых учетных данных для установки.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Install-CcAppliance не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

