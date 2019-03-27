---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Командлет Set-CcExternalCertificateFilePath задает путь к сертификату для сервера-посредника или пограничного сервера.
ms.openlocfilehash: 059d0f2fbf5fee708ceccd0d6e10ad4286fe4f85
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895351"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Командлет Set-CcExternalCertificateFilePath задает путь к сертификату для сервера-посредника или пограничного сервера.
  
Этот сертификат требуется для развертывания, а также при добавлении новых устройств Skype для бизнеса Cloud Connector Edition. Кроме того, эта команда позволяет импортировать новый сертификат для сервера-посредника после развертывания.
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задается путь к сертификату пограничного сервера:
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Пример 2

В следующем примере задается путь к сертификату сервера-посредника:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Пример 3

В следующем примере обновляется сертификат сервера-посредника:
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

При развертывании или изменении топологии необходимо указать путь к сертификату пограничного сервера и при необходимости к сертификату сервера-посредника. 
  
Сертификат сервера-посредника требуется в том случае, если между шлюзами и сервером-посредником используется протокол TLS. При развертывании appliance облачных соединителя и хотите развернуть TLS, можно указать только путь к сертификату, который будет развертываться на сервер-посредник. Тем не менее, если вы хотите обновить сертификат посредника на ранее развернутом устройстве, необходимо указать путь и параметр -Import. Чтобы просмотреть путь, используйте командлет Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**.|
|:-----|:-----|:-----|:-----|
| Целевой объект <br/> | Обязательно <br/> |System.String  <br/> |Тип запрашиваемого пути к файлу. Возможные типы:  <br/> EdgeServer (по умолчанию)  <br/> MediationServer  <br/> |
|Импорт  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Указывает, что сертификат необходимо импортировать на сервер-посредник. Этот параметр не требуется, если устройство развертывается впервые. Этот параметр обязателен, если требуется заменить существующий сертификат для ранее развернутой версии.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Командлет Set-CcExternalCertificateFilePath не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

