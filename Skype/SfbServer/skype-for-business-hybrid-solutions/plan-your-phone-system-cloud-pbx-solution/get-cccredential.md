---
title: Get-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Командлет Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: cff2ba89f7ebf3151a92a753e4dc6adc490dde05
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569996"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Командлет Get-CcCredential возвращает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. 
  
С версии 2.0 и более поздних версий можно также использовать параметр - DisplayPassword для отображения пароли для TenantAdmin, страница и VMAdmin.
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере возвращаются учетные данные администратора домена виртуальной машины Cloud Connector:
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Get-CcCredential возвращает сведения об учетных данных для указанного типа учетной записи. Эти учетные данные задаются администратором, который выполняет командлеты Register-CcAppliance и Install-CcAppliance при развертывании текущего устройства.  
  
Командлет Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential. Свойство password возвращаемого объекта имеет тип System.Security.SecureString.
  
Если вы хотите получить пароль администратора домена в открытом виде, введите пароль текущей учетной записи для входа на сервере узла, после чего откройте консоль PowerShell от имени администратора и выполните следующий скрипт:
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |Обязательно  <br/> | System.String <br/> | AccountType значение может быть одним из следующих: <br/>  VmAdmin: локальный администратор соединителя облачных виртуальных машин. <br/>  Страница: Администратора соединителя облачных виртуальной машины домена. <br/>  SafeModeAdmin. Администратор безопасного режима для контроллера домена виртуальных машин Cloud Connector. <br/>  ExternalCert. Учетная запись для внешнего сертификата, установленного на пограничном сервере. <br/>  TenantAdmin. Администратор клиента O365. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Get-CcCredential не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Командлет Get-CcCredential возвращает экземпляр объекта System.Management.Automation.PSCredential.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[SET-CcCredential](set-cccredential.md)
  

