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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Этот Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации на уровне сайта. Папка содержит базовые файлы установки VHD и Skype для бизнеса Cloud Connector Edition. Эта папка должна совместно работать со всеми другими устройствами сайта Cloud Connector.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799869"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Этот Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации на уровне сайта. Папка содержит базовые файлы установки VHD и Skype для бизнеса Cloud Connector Edition. Эта папка должна совместно работать со всеми другими устройствами сайта Cloud Connector.
  
Этот cmdlet применяется к Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин компонентов Cloud Connector:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Чтобы обеспечить сходство шлюзов и высокую доступность, устройства Cloud Connector можно объединить на сайтах. Пользователи назначены сайтам, а не устройствам Cloud Connector. Каждый сайт имеет общую папку, в которой хранятся файлы установки базового VHD и Cloud Connector. Устройства используют эту папку во время развертывания. Папка по умолчанию C:\Users \% userprofile%\CloudConnector\SiteRoot. Путь можно изменить с помощью Set-CcSiteDirectory управления.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Get-CcSiteDirectory не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

