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
ms.localizationpriority: medium
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Этот Remove-CcLegacyServerCertificate удаляет устаревшие сертификаты сервера в Центральном хранилище управления, сервере-посреднике и edge Server после выполнения Renew-CcCACertificate или обновления CcServerCertificate.
ms.openlocfilehash: 93df3e8658cecdb4a6cc8b14d59d61a716dab8fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589953"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Этот Remove-CcLegacyServerCertificate удаляет устаревшие сертификаты сервера в Центральном хранилище управления, сервере-посреднике и edge Server после выполнения Renew-CcCACertificate или обновления CcServerCertificate.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере удаляются устаревшие сертификаты, выданные для центра управления, сервера-посредника и edge Server после возобновления сертификатов:
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>Пример 2

В следующем примере удаляются сертификаты, выдав для сервера-посредника и edge Server после возобновления сертификатов: 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Роли <br/> |Необязательна  <br/> |System.Array  <br/> | Массив ролей сервера облачного соединителя. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Remove-CcLegacyServerCertificate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

