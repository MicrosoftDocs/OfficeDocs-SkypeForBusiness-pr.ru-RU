---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Этот Get-CcApplianceDirectory извлекает рабочий каталог на сервере Skype для бизнеса Cloud Connector Edition сервере. Все файлы развертывания хранятся в этом каталоге.
ms.openlocfilehash: 9b049b0227f923518ae682415df48afeb044c3c3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599864"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Этот Get-CcApplianceDirectory извлекает рабочий каталог на сервере Skype для бизнеса Cloud Connector Edition сервере. Все файлы развертывания хранятся в этом каталоге. 
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся конфигурации и файлы виртуальных машин компонентов Облачного соединитетеля:
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

В Get-CcApplianceDirectory показано, где хранятся все файлы конфигурации и виртуальные компьютеры, журналы и внешние сертификаты для устройства Cloud Connector.
  
Каждое устройство облачного соединитела имеет четыре компонента: сервер-посредник, центральный магазин управления, edge Server и контроллер домена. Папка по умолчанию — C:\Users \% userprofile%\CloudConnector\ApplianceRoot. Эту папку можно изменить с помощью Set-CCApplianceDirectory.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Get-CCApplianceDirectory не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь файла.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

