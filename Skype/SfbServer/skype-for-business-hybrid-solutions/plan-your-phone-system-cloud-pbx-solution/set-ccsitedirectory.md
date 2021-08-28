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
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Этот Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации Skype для бизнеса Cloud Connector Edition уровней сайта. Папка будет содержать базовые файлы конфигурации VHD и облачного соединитела.
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610536"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Этот Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации Skype для бизнеса Cloud Connector Edition уровней сайта. Папка будет содержать базовые файлы конфигурации VHD и облачного соединитела.
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере корневой каталог сайта устанавливается \\ в SiteShare\CloudConnector:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Чтобы обеспечить близость шлюза и высокую доступность, устройства Cloud Connector можно объединить на сайтах. Пользователям назначены сайты, а не устройства Cloud Connector. Каждый сайт имеет общую папку, в которой хранятся базовые файлы установки VHD и cloud Connector. Устройства используют эту папку во время развертывания. Эта папка должна быть совместной со всеми другими устройствами на сайте Cloud Connector.
  
Папка по умолчанию — C:\Users \% userprofile%\CloudConnector\SiteRoot. Путь можно просмотреть с помощью Get-CcSiteDirectory.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Путь <br/> | Обязательный <br/> | System.String <br/> |Предоставляет путь к папке, в которой будут храниться файлы сайтов Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Set-CcSiteDirectory не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

