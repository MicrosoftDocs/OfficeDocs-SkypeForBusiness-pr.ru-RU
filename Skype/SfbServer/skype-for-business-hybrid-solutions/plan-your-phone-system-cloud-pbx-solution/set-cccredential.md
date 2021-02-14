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
description: Этот Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221573"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Этот Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. 
  
С помощью Cloud Connector версии 2.0 и более поздних версий этот cmdlet также может устанавливать сведения об учетной записи для администратора виртуальной машины и администратора домена.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере указывается имя и пароль учетной записи для администратора клиента:
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Set-CcCredential задает имя и пароль учетной записи для администратора клиента. Для выпусков до версии 2.0 этот администратор должен быть глобальным администратором. Cloud Connector использует эту учетную запись для получения сведений о конфигурации, настройки параметров конфигурации и обновления состояния устройства в конфигурации организации Microsoft 365 или Office 365. В выпуске 2.0 и более поздних версиях этот cmdlet также можно использовать для обновления паролей учетных записей VmAdmin и DomainAdmin.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Обязательный <br/> |System.String  <br/> | Значение параметра должно быть "TenantAdmin", "VmAdmin" или "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Set-CcCredential не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

