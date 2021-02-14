---
title: Set-CcExternalCertificateFilePath
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
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Этот Set-CcExternalCertificateFilePath указывает путь, в котором хранится сертификат для сервера-посредника или сервера-посредника.
ms.openlocfilehash: 9216b82626da7160d6e1bfa8d611757321a2683a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824203"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
Этот Set-CcExternalCertificateFilePath указывает путь, в котором хранится сертификат для сервера-посредника или сервера-посредника.
  
Этот сертификат требуется во время развертывания или при добавлении новых устройств Skype для бизнеса Cloud Connector Edition. Команда также позволяет импортировать новый сертификат для сервера-посредника после развертывания.
  
Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задан путь к сертификату для edge Server:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Пример 2

В следующем примере задан путь к сертификату для сервера-посредника:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Пример 3

В следующем примере обновляется сертификат для сервера-посредника:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Во время развертывания или при изменении топологии необходимо указать путь к сертификату сервера-посредника и, при необходимости, сертификату сервера-посредника. 
  
Сертификат для сервера-посредника необходим, если между шлюзом и сервером-посредником будет использоваться TLS. При развертывании устройства Cloud Connector и развертывании TLS можно указать только путь к сертификату, который будет развернут на сервере-посреднике. Однако если вы хотите обновить сертификат-посредник на уже развернутом устройстве, необходимо указать путь и параметр -Import. Чтобы увидеть путь, используйте Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Target <br/> | Обязательный <br/> |System.String  <br/> |Тип запрашиваемого пути к файлу. К типам относятся:  <br/> EdgeServer (по умолчанию)  <br/> MediationServer  <br/> |
|Импорт  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Указывает, что сертификат необходимо импортировать на сервер-посредник. Этот параметр не требуется при первом развертывании устройства. Этот параметр необходим, если требуется изменить существующий сертификат в уже развернутой версии.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Этот Set-CcExternalCertificateFilePath не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

