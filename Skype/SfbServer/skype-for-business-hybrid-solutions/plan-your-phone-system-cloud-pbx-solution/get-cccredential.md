---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Этот Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: c4e2d47ffc31eb7afef76c710fc93024ce2c593e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800399"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Этот Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. 
  
В версиях 2.0 и более поздних версий можно также использовать параметр -DisplayPassword для отображения паролей для TenantAdmin, DomainAdmin и VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере возвращаются учетные данные администратора домена виртуальной машины Cloud Connector:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Get-CcCredential возвращает учетные данные об указанном типе учетной записи. Эти учетные данные заданы администратором, который запускает Register-CcAppliance и Install-CcAppliance при развертывании текущего устройства. 
  
Этот Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential. Свойство password возвращаемого объекта — System.Security.SecureString.
  
Если вы хотите получить понятный текст пароля администратора домена, убедитесь, что пароль введен текущей учетной записью входа на сервере хост-сервера, а затем откройте консоль PowerShell от имени администратора и запустите сценарий ниже:
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Обязательный  <br/> | System.String <br/> | Значение AccountType может быть одним из следующих значений: <br/>  VmAdmin: локальный администратор виртуальных машин Cloud Connector. <br/>  DomainAdmin: администратор домена виртуальной машины Cloud Connector. <br/>  SafeModeAdmin: SafeModeAdmin контроллера домена виртуальной машины Cloud Connector. <br/>  ExternalCert: учетная запись внешнего сертификата, установленного на edge Server. <br/>  TenantAdmin: администратор клиента O365. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Get-CcCredential не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Этот Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

