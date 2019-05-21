---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition. Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.
ms.openlocfilehash: e0b8a793f0210535a726b0bed19f240bf8b30dd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287302"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition. Эта папка должна быть предоставлена всем другим устройствам на сайте облачного соединителя.
  
Этот командлет применяется к версии Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин в компонентах облачного соединителя.
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Для обеспечения соответствия шлюза и высокой доступности устройства облачного соединителя можно объединять на сайтах. Пользователи назначаются на сайты, а не в облачных устройствах-соединителях. На каждом сайте есть общая папка, в которой хранятся базовые установочные файлы VHD и Cloud Connector. Устройства используют эту папку во время развертывания. По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут. Путь можно изменить с помощью командлета Set-CcSiteDirectory.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Отсутствуют. Командлет Get-CcSiteDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

