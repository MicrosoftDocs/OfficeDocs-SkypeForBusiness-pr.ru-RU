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
description: 'Командлет Renew-CcServerCertificate продлевает сертификаты Skype для бизнеса Cloud Connector Edition, срок действия которых истекает или уже истек. Эта команда была заменена на Update-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусков. '
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824265"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Командлет Renew-CcServerCertificate продлевает сертификаты Skype для бизнеса Cloud Connector Edition, срок действия которых истекает или уже истек. Эта команда была заменена на Update-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусков.  
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере продлеваются сертификаты сервера центрального хранилища управления (CMS), сервера-посредника или пограничного сервера, срок действия которых истекает или уже истек.
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Пример 2

В следующем примере продлеваются сертификаты сервера-посредника или пограничного сервера, срок действия которых истекает или уже истек.
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Внутренние сертификаты облачного соединителя, выданные для хранилища центрального управления, сервера-посредника и пограничного сервера, действительны в течение двух лет после того, как они были выпущены в службе сертификации. Если срок действия сертификатов истекает или уже истек, выполните командлет Renew-CcServerCertificate для их продления. 
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Роли  <br/> |Необязательно   <br/> |System.Array  <br/> |  Массив ролей сервера Cloud Connector. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Renew-CcServerCertificate не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

