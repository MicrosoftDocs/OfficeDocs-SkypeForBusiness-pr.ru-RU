---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Этот Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут содержаться файлы конфигурации базового VHD и Cloud Connector.
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824193"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Этот Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут содержаться файлы конфигурации базового VHD и Cloud Connector.
  
Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере для корневого каталога сайта устанавливается \\ siteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Чтобы обеспечить сходство шлюзов и высокую доступность, устройства Cloud Connector можно объединить на сайтах. Пользователи назначены сайтам, а не устройствам Cloud Connector. Каждый сайт имеет общую папку, в которой хранятся файлы установки базового VHD и Cloud Connector. Устройства используют эту папку во время развертывания. Эта папка должна совместно работать со всеми другими устройствами на сайте Cloud Connector.
  
Папка по умолчанию C:\Users \% userprofile%\CloudConnector\SiteRoot. Путь можно просмотреть с помощью Get-CcSiteDirectory.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Path <br/> | Обязательный <br/> | System.String <br/> |Предоставляет путь к папке, в которой будут храниться файлы сайта Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Set-CcSiteDirectory не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

