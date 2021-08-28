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
ms.localizationpriority: medium
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: В Set-CcExternalCertificateFilePath указывается путь, по котором хранится сертификат для сервера-посредника или edge Server.
ms.openlocfilehash: b8555d3a3c6770481e1a66f79fd4a1060d3d9936
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615525"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
В Set-CcExternalCertificateFilePath указывается путь, по котором хранится сертификат для сервера-посредника или edge Server.
  
Этот сертификат необходим во время развертывания или при добавлении новых Skype для бизнеса Cloud Connector Edition. Команда также позволяет импортировать новый сертификат для сервера-посредника после развертывания.
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задан путь сертификата для edge Server:
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>Пример 2

Следующий пример задает путь сертификата для сервера-посредника:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>Пример 3

В следующем примере обновляется сертификат для сервера-посредника:
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Во время развертывания или при изменении топологии необходимо указать путь для сертификата Edge Server и необязательно для сертификата Mediation Server. 
  
Сертификат для сервера-посредника необходим, если TLS будет использоваться между шлюзом (s) и сервером-посредником. При развертывании устройства cloud Connector и развертывании TLS можно указать путь только к сертификату, который будет развернут на сервере-посреднике. Однако для обновления сертификата-посредника на уже развернутом устройстве необходимо указать путь и параметр -Import. Чтобы увидеть путь, используйте Get-CCExternalCertificateFilePath.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Область применения <br/> | Обязательный <br/> |System.String  <br/> |Тип запрашиваемого пути файла. Типы включают в себя:  <br/> EdgeServer (по умолчанию)  <br/> MediationServer  <br/> |
|Импорт  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Указывает, что сертификат должен быть импортироваться на сервер-посредник. Этот параметр не требуется при первом развертывании устройства. Этот параметр необходим для изменения существующего сертификата в уже развернутой версии.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

В Set-CcExternalCertificateFilePath не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

