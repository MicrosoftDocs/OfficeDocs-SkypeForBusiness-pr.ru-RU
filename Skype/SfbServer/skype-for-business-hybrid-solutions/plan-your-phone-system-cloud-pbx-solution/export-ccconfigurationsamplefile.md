---
title: Export-CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере файлы для загрузки пример файла конфигурации с сайта корпорации Майкрософт и записывает в каталоге appliance appliance облачных соединителя:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Текущая версия облачных соединителя необходимо указать несколько параметров в INI-файла; Например, для таких параметров IP-адреса виртуальных машин для облачных компоненты, имена компонентов, параметры шлюза и т. д.
  
Этот командлет, при запуске на главном компьютере соединителя облачных файлы для загрузки примера INI-файле с примерами настройки с сайта корпорации Майкрософт. Командлет записывает файл в каталоге appliance appliance облачных соединителя. С помощью командлета Set-CcApplianceDirectory указан каталог устройства.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Export-CcConfigurationSampleFile не принимает входные данные по конвейеру. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[SET-CcApplianceDirectory](set-ccappliancedirectory.md)
  

