---
title: Get-CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Командлет Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Этот сертификат подготавливается пользователем.
ms.openlocfilehash: 9ceba99310ab25676a7cd3938ed386c4752f453e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Командлет Get-CcExternalCertificateFilePath возвращает путь к файлу внешнего сертификата для развертывания Skype для бизнеса Cloud Connector Edition. Этот сертификат подготавливается пользователем.
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показан путь к сертификату пограничного сервера.
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>Пример 2

В следующем примере показан путь к сертификату сервера-посредника.
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

При развертывании или изменении топологии необходимо указать путь к сертификату пограничного сервера и при необходимости к сертификату сервера-посредника. Сертификат сервера-посредника требуется в том случае, если между шлюзами и сервером-посредником используется протокол TLS.Чтобы изменить путь, используйте командлет Set-CcExternalCertificateFilePath.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Целевой объект  <br/> |Необязательно   <br/> | System.Management.Automation.SwitchParameter <br/> |Тип запрашиваемого пути к файлу. Возможные типы:  <br/> EdgeServer (по умолчанию)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Командлет Get-CcExternalCertificateFilePath не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[SET-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

