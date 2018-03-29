---
title: SET-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a>SET-CcSiteDirectory
 
Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задается корневого каталога веб-сайтов \\SiteShare\CloudConnector:
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Чтобы обеспечить соответствие шлюза и высокой доступности, устройств для соединителя облаке могут быть объединены в сайты. Пользователи назначаются сайтов вместо устройств для соединителя облака. На каждом сайте есть общая папка, в которой хранятся файлы установки базового виртуального жесткого диска и Cloud Connector. Эта папка используется устройства во время развертывания. Эта папка должна быть общей с другими приложениями, в облаке соединителя сайта.
  
Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\SiteRoot. Путь можно просмотреть с помощью командлета Get-CcSiteDirectory.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Путь <br/> | Обязательно <br/> | System.String <br/> |Содержит путь к папке, где будут храниться файлы соединителя облака сайта.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Отсутствуют. Командлет Set-CcSiteDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

