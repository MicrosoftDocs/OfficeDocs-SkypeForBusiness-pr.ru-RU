---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Этот Set-CcCredential задает учетные данные текущего Skype для бизнеса Cloud Connector Edition развертывания.
ms.openlocfilehash: 330326790f20add51dcaeb4468b17438c302c353c08076402e15f4d32985c117
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324139"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Этот Set-CcCredential задает учетные данные текущего Skype для бизнеса Cloud Connector Edition развертывания. 
  
С помощью облачного соединителя версии 2.0 и более поздней версии этот комлет также может задать сведения об учетной записи для администратора виртуальных машин и администратора домена.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере указывается имя и пароль учетной записи для администратора клиента:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Set-CcCredential задает имя и пароль учетной записи для администратора клиента. Для выпусков до 2.0 этот администратор должен быть глобальным администратором. Cloud Connector использует эту учетную запись для получения сведений о конфигурации, набора параметров конфигурации и обновления состояния устройства Microsoft 365 или Office 365 организации. С выпуском 2.0 и более поздней версией можно также использовать этот кодлет для обновления паролей для учетных записей VmAdmin и DomainAdmin.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Обязательный <br/> |System.String  <br/> | Значение параметра должно быть "TenantAdmin", "VmAdmin" или "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Set-CcCredential не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

