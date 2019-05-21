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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Командлет Export-CcConfigurationSampleFile экспортирует образец файла конфигурации Skype для бизнеса Cloud Connector Edition (INI) в каталог устройства на устройстве Cloud Connector. Вы можете изменить и переименовать этот файл, чтобы использовать его в своем развертывании.
ms.openlocfilehash: 440253bc6b9c4e980a6f7ac4aae0c82ebad05660
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287384"
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

В следующем примере файл конфигурации примера загружается с сайта Майкрософт и записывается в каталог управляющего устройства облачного соединителя:
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Для текущей версии облачного соединителя требуется предоставить несколько параметров в ini-файле. Например, такие параметры, как IP-адреса виртуальных машин для компонентов облачного соединителя, имена компонентов, параметры шлюза и т. д.
  
Этот командлет при запуске на главном компьютере облачного соединителя, загружает образец ini-файла с примерами конфигурации на сайте Майкрософт. Командлет записывает файл в каталог управляющего устройства облачного соединителя. Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Export-CcConfigurationSampleFile не принимает входные данные по конвейеру. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

