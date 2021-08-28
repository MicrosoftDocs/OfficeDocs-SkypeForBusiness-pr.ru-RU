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
ms.localizationpriority: medium
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: В Get-CcSiteDirectory показан текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит базовые файлы VHD и Skype для бизнеса Cloud Connector Edition установки. Эта папка должна быть совместной со всеми другими устройствами сайта Cloud Connector.
ms.openlocfilehash: 04b1460b9743c3d19ca4db77f67d057d400f400b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616375"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
В Get-CcSiteDirectory показан текущий каталог, в котором хранятся файлы конфигурации уровня сайта. Папка содержит базовые файлы VHD и Skype для бизнеса Cloud Connector Edition установки. Эта папка должна быть совместной со всеми другими устройствами сайта Cloud Connector.
  
Этот кодлет применяется к Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин компонентов cloud Connector:
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Чтобы обеспечить близость шлюза и высокую доступность, устройства Cloud Connector можно объединить на сайтах. Пользователям назначены сайты, а не устройства Cloud Connector. Каждый сайт имеет общую папку, в которой хранятся базовые файлы установки VHD и cloud Connector. Устройства используют эту папку во время развертывания. Папка по умолчанию — C:\Users \% userprofile%\CloudConnector\SiteRoot. Путь можно изменить с помощью Set-CcSiteDirectory.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Get-CcSiteDirectory не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь файла.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

