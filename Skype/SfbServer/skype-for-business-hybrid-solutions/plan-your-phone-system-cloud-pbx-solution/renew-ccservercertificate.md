---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. Эта команда была изменена Update-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусках.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824265"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. Эта команда была изменена Update-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусках. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере обновляются сертификаты центрального банка управления, сервера-посредника и сервера-посредника, когда срок действия сертификатов истекает или уже истек:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Пример 2

В следующем примере обновляются сертификаты для сервера-посредника и сервера-посредника, когда срок их действия истекает или уже истек:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Внутренние сертификаты Cloud Connector, выдавамые центральному окне управления, серверу-посреднику и серверу-посреднику, действуют в течение двух лет после их выдачи службой центра сертификации. Если срок действия сертификатов истекает или уже истек, запустите Renew-CcServerCertificate для их продления. 
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Roles  <br/> |Необязательна  <br/> |System.Array  <br/> | Массив ролей сервера Cloud Connector. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Renew-CcServerCertificate не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

