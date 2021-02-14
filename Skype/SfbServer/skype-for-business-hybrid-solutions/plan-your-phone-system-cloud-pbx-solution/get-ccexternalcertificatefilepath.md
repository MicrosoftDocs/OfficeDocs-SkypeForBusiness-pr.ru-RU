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
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Этот Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Пользователь подготавливает этот сертификат.
ms.openlocfilehash: 143595d30bb71756544a16ad464da05a229f476d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799909"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Этот Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Пользователь подготавливает этот сертификат.
  
Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показан путь к сертификату для edge Server:
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Пример 2

В следующем примере показан набор сертификатов для сервера-посредника:
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Во время развертывания или изменения топологии необходимо указать путь к сертификату сервера-посредника и,при необходимости, для сервера-посредника. Сертификат для сервера-посредника необходим, если между шлюзом и сервером-посредником будет использоваться TLS. Чтобы изменить путь, используйте Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Target  <br/> |Необязательный  <br/> | System.Management.Automation.SwitchParameter <br/> |Тип запрашиваемого пути к файлу. К типам относятся:  <br/> EdgeServer (по умолчанию)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Этот Get-CcExternalCertificateFilePath не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

