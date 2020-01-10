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
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Командлет Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 46c51783361ad6613d1e2971600969b324f0f350
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003389"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Командлет Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. 
  
В версии 2,0 и более поздних версиях можно также использовать параметр-Дисплайпассворд, чтобы показать пароли для администратора клиента, Домаинадмин и Вмадмин.
  
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

Командлет Get-CcCredential возвращает сведения об учетных данных для указанного типа учетной записи. Эти учетные данные задаются администратором, который выполняет командлеты Register-CcAppliance и Install-CcAppliance при развертывании текущего устройства.  
  
Командлет Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential. Свойство password возвращаемого объекта имеет тип System.Security.SecureString.
  
Если вы хотите получить пароль администратора домена в открытом виде, введите пароль текущей учетной записи для входа на сервере узла, после чего откройте консоль PowerShell от имени администратора и выполните следующий скрипт:
  
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

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Обязательный  <br/> | System.String <br/> | Параметр AccountType может иметь следующие значения. <br/>  Вмадмин: локальный администратор виртуальных машин облачного соединителя. <br/>  DomainAdmin. Администратор домена виртуальных машин Cloud Connector. <br/>  SafeModeAdmin. Администратор безопасного режима для контроллера домена виртуальных машин Cloud Connector. <br/>  ExternalCert. Учетная запись для внешнего сертификата, установленного на пограничном сервере. <br/>  TenantAdmin. Администратор клиента O365. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Get-CcCredential не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Командлет Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

