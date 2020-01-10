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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 'Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: bcb88f11fb78d995e6d8271593c2e09bb0b11d22
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003219"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Командлет Set-CcCredential задает учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.  
  
С помощью облачного соединителя версии 2,0 и более поздних версий этот командлет также может задать сведения об учетной записи для администратора виртуальных машин и для администратора домена.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задаются имя и пароль учетной записи для администратора клиента.
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Set-CcCredential задает имя и пароль учетной записи для администратора клиента. В выпусках вплоть до версии 2.0 этот администратор должен быть глобальным администратором Office 365. Облачный соединитель использует эту учетную запись для получения сведений о конфигурации, настройки параметров конфигурации и обновления состояния устройства в конфигурации клиента Office 365. С выпуском 2,0 и более поздними версиями вы также можете использовать этот командлет, чтобы обновить пароли для учетных записей Вмадмин и Домаинадмин.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | Обязательный <br/> |System.String  <br/> |  Параметр должен иметь значение "TenantAdmin", "VmAdmin" или "DomainAdmin". <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Отсутствуют. Командлет Set-CcCredential не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

