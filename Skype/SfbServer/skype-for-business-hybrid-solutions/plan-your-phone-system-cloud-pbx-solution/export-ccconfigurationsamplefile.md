---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Этот Export-CcConfigurationSampleFile экспортирует файл Skype для бизнеса Cloud Connector Edition примера конфигурации (.ini) в каталог приборов устройства облачного соединителя. Вы можете изменить и переименовать файл для развертывания.
ms.openlocfilehash: f59e93cf241ca762dcb41cf23d617017a62581b453cb84cebc915b1703f5a019
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326265"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Этот Export-CcConfigurationSampleFile экспортирует файл Skype для бизнеса Cloud Connector Edition примера конфигурации (.ini) в каталог приборов устройства облачного соединителя. Вы можете изменить и переименовать файл для развертывания.
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере загружается пример файла конфигурации с сайта Майкрософт и записывает его в каталог устройства Cloud Connector:
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

В текущей версии облачного соединитетеля требуется предоставить несколько параметров в .ini файле; например, такие параметры, как IP-адреса виртуальных машин для компонентов cloud Connector, имена компонентов, параметры шлюза и так далее.
  
Этот комлет при запуске на хост-машине облачного соединителя загружает пример .ini с примерами конфигурации с сайта Майкрософт. The cmdlet writes the file to the appliance directory of the Cloud Connector appliance. Каталог приборов определяется с помощью Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Export-CcConfigurationSampleFile не принимается конвейерный ввод. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

