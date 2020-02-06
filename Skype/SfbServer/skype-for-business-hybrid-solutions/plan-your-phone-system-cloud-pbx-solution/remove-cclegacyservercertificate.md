---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824285"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере удаляются прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после продления сертификатов.
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Пример 2

В следующем примере удаляются прежние версии сертификатов сервера-посредника и пограничного сервера после продления сертификатов.  
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Роли <br/> |Необязательно   <br/> |System.Array  <br/> |  Массив ролей сервера Cloud Connector. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Remove-CcLegacyServerCertificate не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

