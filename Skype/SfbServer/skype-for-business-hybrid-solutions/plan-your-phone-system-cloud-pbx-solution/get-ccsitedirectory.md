---
title: Get-CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition. Эта папка должна быть общей с другими приложениями, соединитель облака сайта.
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Командлет Get-CcSiteDirectory показывает текущий каталог, в котором хранятся файлы конфигурации уровня сайта. В папке находятся файлы установки базового виртуального жесткого диска и Skype для бизнеса Cloud Connector Edition. Эта папка должна быть общей с другими приложениями, соединитель облака сайта.
  
Этот командлет применяется к версии Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показано текущую папку, где хранятся файлы конфигурации и виртуальных машин из облака соединитель компонентов:
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Чтобы обеспечить соответствие шлюза и высокой доступности, устройств для соединителя облаке могут быть объединены в сайты. Пользователи назначаются сайтов вместо устройств для соединителя облака. На каждом сайте есть общая папка, в которой хранятся файлы установки базового виртуального жесткого диска и Cloud Connector. Эта папка используется устройства во время развертывания. Папка по умолчанию является C:\Users\%userprofile%\CloudConnector\SiteRoot. Путь можно изменить с помощью командлета Set-CcSiteDirectory.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Отсутствуют. Командлет Get-CcSiteDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[SET-CcSiteDirectory](set-ccsitedirectory.md)
  

