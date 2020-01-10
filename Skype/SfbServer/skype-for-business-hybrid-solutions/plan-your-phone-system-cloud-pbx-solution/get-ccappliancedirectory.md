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
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 'Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.  '
ms.openlocfilehash: 77064676062411c3417e554e422b0ffaae461191
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003409"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
Командлет Get-CcApplianceDirectory извлекает рабочий каталог на сервере узла Skype для бизнеса Cloud Connector Edition. В этом каталоге хранятся все файлы развертывания.   
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся файлы конфигурации и виртуальных машин в компонентах облачного соединителя.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Get-Ккапплианцедиректори показывает, какие файлы конфигурации и виртуальных машин, журналы и внешние сертификаты хранятся для устройства облачного соединителя.
  
У каждого устройства облачного соединителя есть четыре компонента: сервер-посредник, хранилище Центрального управления, пограничный сервер и контроллер домена. По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\апплианцерут. Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Get-CCApplianceDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

