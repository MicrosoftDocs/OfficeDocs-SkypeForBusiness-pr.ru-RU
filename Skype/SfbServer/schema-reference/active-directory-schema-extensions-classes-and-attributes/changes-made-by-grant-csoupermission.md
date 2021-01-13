---
title: Изменения, внесенные Grant-CsOUPermission в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Чтобы делегировать администрирование Skype для бизнеса Server, можно добавить разрешения для указанных подразделений, чтобы члены универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не являясь членами группы администраторов домена.
ms.openlocfilehash: 09a6d6baf554b18db0a388619ffb74c85c6963fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831849"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Изменения, внесенные Grant-CsOUPermission в Skype для бизнеса Server
 
Чтобы делегировать администрирование Skype для бизнеса Server, можно добавить разрешения для указанных подразделений, чтобы члены универсальных групп RTC, созданные при подготовке леса, могли получать доступ к подразделениям, не являясь членами группы администраторов домена. 
  
Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном подразделении, как указано в следующих таблицах.
  
## <a name="granting-permission-for-user-objects"></a>Предоставление разрешений для объектов-пользователей

При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам-пользователям**

|**Группа**|**Разрешение**|**Относится к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Public-Information  <br/> Чтение General-Information  <br/> Чтение User-Account-Restrictions  <br/> |К дочерним объектам-пользователям  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись msExchUCVoiceMailSettings  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним объектам-пользователям  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Предоставление разрешений для объектов-компьютеров

При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам-компьютерам**

|**Группа**|**Разрешение**|**Относится к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение Public-Information  <br/> Чтение Validated-DNS-Host-Name  <br/> |К дочерним объектам-компьютерам  <br/> |
|RTCUniversalUserAdmins  <br/> |Чтение Public-Information  <br/> Чтение Validated-DNS-Host-Name  <br/> |К дочерним объектам-компьютерам  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Предоставление разрешений для контактных объектов  или объектов AppContact

При запуске командлета **Grant-CsOuPermission** для контактных объектов и объектов AppContact в подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные контактным объектам и объектам AppContact**

|**Группа**|**Разрешение**|**Относится к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Public-Information  <br/> Чтение General-Information  <br/> Чтение Personal-Information  <br/> Чтение User-Account-Restrictions  <br/> |К дочерним контактным объектам  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись otherIpPhone  <br/> Запись displayName  <br/> Запись description  <br/> Запись telephoneNumber  <br/> Запись msExchUCVoiceMailSettings  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним контактным объектам  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Предоставление разрешений для объектов-устройств

При запуске командлета **Grant-CsOuPermission** для объектов-устройств в подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам-устройствам**

|**Группа**|**Разрешение**|**Относится к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Public-Information  <br/> Чтение Personal-Information  <br/> Чтение General-Information  <br/> Чтение User-Account-Restrictions  <br/> |К дочерним контактным объектам  <br/> |
|RTCUniversalUserAdmins  <br/> |Создание дочернего объекта  <br/> Удаление дочернего объекта  <br/> Удаление дерева  <br/> |Контакт  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись displayName  <br/> Запись description  <br/> Запись telephoneNumber  <br/> |К дочерним объектам-пользователям  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись otherIpPhone  <br/> Запись displayName  <br/> Запись description  <br/> Запись telephoneNumber  <br/> Запись msExchUCVoiceMailSettings  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним контактным объектам  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Предоставление разрешений для объектов inetOrgPerson

При запуске командлета **Grant-CsOuPermission** для объектов inetOrgPerson в подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам inetOrgPerson**

|**Группа**|**Разрешение**|**Относится к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Содержимое списка  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Personal-Information  <br/> Чтение Public-Information  <br/> Чтение General-Information  <br/> Чтение User-Account-Restrictions  <br/> |К дочерним объектам inetOrgPerson  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним объектам inetOrgPerson  <br/> |
   

