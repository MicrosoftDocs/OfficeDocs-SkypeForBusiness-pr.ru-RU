---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Этот Update-CcServerCertificate возобновляет сертификаты для Skype для бизнеса Cloud Connector Edition, когда они истекли или уже истекли.
ms.openlocfilehash: 0545f4923a4f1abd654674024313c6f22665cb7123d87d9d21c3676452bd8fcf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344528"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Этот Update-CcServerCertificate возобновляет сертификаты для Skype для бизнеса Cloud Connector Edition, когда они истекли или уже истекли. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере возобновляются сертификаты для центра управления, сервера-посредника и edge Server, когда срок действия сертификатов истек или уже истек:
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>Пример 2

В следующем примере возобновляются сертификаты для сервера-посредника и edge Server, когда они истекли или уже истекли:
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Внутренние сертификаты Cloud Connector, выдаваемые в Центральный магазин управления, сервер-посредник и edge Server, действительны в течение двух лет после их выдачи из службы authority certificate. Если срок действия сертификатов истек или истек, запустите Update-CcServerCertificate для возобновления сертификатов. 
  
Эта команда заменяет командлет Renew-CcServerCertificate в Cloud Connector 2.0 и более поздних выпусках.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Роли  <br/> |Необязательный  <br/> |System.Array  <br/> | Массив ролей сервера облачного соединителя. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Update-CcServerCertificate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

