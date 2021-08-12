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
description: Этот Get-CcCredential возвращает учетные данные текущего Skype для бизнеса Cloud Connector Edition развертывания.
ms.openlocfilehash: 277062068c6e5e630fd22cd1bd4c6dbfb873db1cb90b915424aa6e3a3eb6ce50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322892"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Этот Get-CcCredential возвращает учетные данные текущего Skype для бизнеса Cloud Connector Edition развертывания. 
  
С версией 2.0 и более поздней версией можно также использовать параметр -DisplayPassword для отображения паролей для TenantAdmin, DomainAdmin и VMAdmin.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере возвращаются учетные данные администратора домена виртуального домена Облачного соединитетеля:
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Get-CcCredential возвращает сведения о учетных данных указанного типа учетной записи. Эти учетные данные заданы администратором, который выполняет Register-CcAppliance и Install-CcAppliance при развертывании текущего устройства. 
  
В Get-CcCredential возвращается экземпляр объекта System.Management.Automation.PSCredential. Свойством пароля возвращаемого объекта является System.Security.SecureString.
  
Если вы хотите получить четкий текст пароля администратора домена, убедитесь, что пароль введет текущая учетная запись логотипа на сервере хост-сервера, а затем откройте консоль PowerShell в качестве администратора и запустите ниже скрипт:
  
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
| AccountType <br/> |Обязательный  <br/> | System.String <br/> | Значение AccountType может быть одним из следующих: <br/>  VmAdmin: локальный администратор виртуальных машин Cloud Connector. <br/>  DomainAdmin. Администратор домена домена виртуальной машины Cloud Connector. <br/>  SafeModeAdmin: SafeModeAdmin контроллера домена виртуальной машины Cloud Connector. <br/>  ExternalCert. Учетная запись внешнего сертификата, установленного на edge Server. <br/>  TenantAdmin. Администратор клиента O365. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Get-CcCredential не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

В Get-CcCredential возвращается экземпляр объекта System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

