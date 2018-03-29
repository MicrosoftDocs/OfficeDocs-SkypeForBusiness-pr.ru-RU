---
title: SET-CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a>SET-CcCredential
 
Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.  
  
С соединителем облачных версии 2.0 и более поздних версий этот командлет также можно настроить учетные данные администратора виртуальной машины, а также для администратора домена.
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задаются имя и пароль учетной записи для администратора клиента.
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Set-CcCredential задает имя и пароль учетной записи для администратора клиента. Для выпусков до 2.0 этот администратор должен быть глобального администратора Office 365. Облако соединитель использует эту учетную запись для получения сведений о конфигурации, задайте параметры конфигурации, а состояние обновления устройства для обеспечения связи в конфигурации клиента Office 365. В версии 2.0 и более поздних версий, можно также использовать этот командлет для обновления паролей для учетных записей VmAdmin и страница.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Обязательно <br/> |System.String  <br/> |  Параметр должен иметь значение "TenantAdmin", "VmAdmin" или "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Отсутствуют. Командлет Set-CcCredential не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

