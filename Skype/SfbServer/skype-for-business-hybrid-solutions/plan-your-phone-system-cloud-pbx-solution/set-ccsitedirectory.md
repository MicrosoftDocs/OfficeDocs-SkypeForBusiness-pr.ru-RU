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
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
ms.openlocfilehash: d0cc8d2a66adb831ea2d85381902eb9d3df7ba6a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003199"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Командлет Set-CcSiteDirectory задает каталог, в котором будут храниться файлы конфигурации уровня сайта для Skype для бизнеса Cloud Connector Edition. В папке будут находиться файлы конфигурации базового виртуального жесткого диска и Cloud Connector.
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере для корневого каталога сайта задается значение \\ситешаре\клаудконнектор:
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Для обеспечения соответствия шлюза и высокой доступности устройства облачного соединителя можно объединять на сайтах. Пользователи назначаются на сайты, а не в облачных устройствах-соединителях. На каждом сайте есть общая папка, в которой хранятся базовые установочные файлы VHD и Cloud Connector. Устройства используют эту папку во время развертывания. Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.
  
По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут. Путь можно просмотреть с помощью командлета Get-CcSiteDirectory.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Путь <br/> | Обязательно <br/> | System.String <br/> |Путь к папке, в которой будут храниться файлы сайта облачного соединителя.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Отсутствуют. Командлет Set-CcSiteDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

