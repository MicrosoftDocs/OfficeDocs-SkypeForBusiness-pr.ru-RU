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
description: Этот Renew-CcServerCertificate возобновляет сертификаты для Skype для бизнеса Cloud Connector Edition, когда они истекли или уже истекли. Эта команда была изменена на Update-CcServerCertificate в cloud Connector 2.0 и более поздних выпусках.
ms.openlocfilehash: 632807f8d6b8dda7b3df6639e8f6166e8ac5e6a22381646616a0637779a9159a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340735"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
Этот Renew-CcServerCertificate возобновляет сертификаты для Skype для бизнеса Cloud Connector Edition, когда они истекли или уже истекли. Эта команда была изменена на Update-CcServerCertificate в cloud Connector 2.0 и более поздних выпусках. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере возобновляются сертификаты для центра управления, сервера-посредника и edge Server, когда срок действия сертификатов истек или уже истек:
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>Пример 2

В следующем примере возобновляются сертификаты для сервера-посредника и edge Server, когда они истекли или уже истекли:
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Внутренние сертификаты Cloud Connector, выдаваемые в Центральный магазин управления, сервер-посредник и edge Server, действительны в течение двух лет после их выдачи из службы authority certificate. Если срок действия сертификатов истек или истек, запустите Renew-CcServerCertificate для возобновления сертификатов. 
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Роли  <br/> |Необязательный  <br/> |System.Array  <br/> | Массив ролей сервера облачного соединителя. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Renew-CcServerCertificate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

