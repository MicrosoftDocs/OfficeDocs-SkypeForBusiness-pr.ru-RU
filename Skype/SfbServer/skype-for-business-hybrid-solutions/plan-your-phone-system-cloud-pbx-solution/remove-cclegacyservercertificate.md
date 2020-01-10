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
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Командлет Remove-CcLegacyServerCertificate удаляет прежние версии сертификатов сервера центрального хранилища управления, сервера-посредника и пограничного сервера после выполнения командлетов Renew-CcCACertificate или Renew CcServerCertificate.
ms.openlocfilehash: f22a57a3a366c621a1c035881c886190055b15e6
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003289"
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
  

