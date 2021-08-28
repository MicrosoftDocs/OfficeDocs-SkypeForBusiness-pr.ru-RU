---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Этот Get-CcExternalCertificateFilePath возвращает путь внешнего файла сертификата для Skype для бизнеса Cloud Connector Edition развертывания. Пользователь готовит этот сертификат.
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622041"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Этот Get-CcExternalCertificateFilePath возвращает путь внешнего файла сертификата для Skype для бизнеса Cloud Connector Edition развертывания. Пользователь готовит этот сертификат.
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показан путь сертификата для edge Server:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Пример 2

В следующем примере показан набор сертификатов для сервера-посредника:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Во время развертывания или при изменении топологии необходимо указать путь для сертификата Edge Server и, необязательно, для сервера-посредника. Сертификат для сервера-посредника необходим, если TLS будет использоваться между шлюзом (s) и сервером-посредником. Чтобы изменить путь, используйте Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Область применения  <br/> |Необязательный  <br/> | System.Management.Automation.SwitchParameter <br/> |Тип запрашиваемого пути файла. Типы включают в себя:  <br/> EdgeServer (по умолчанию)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

В Get-CcExternalCertificateFilePath не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь файла.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

