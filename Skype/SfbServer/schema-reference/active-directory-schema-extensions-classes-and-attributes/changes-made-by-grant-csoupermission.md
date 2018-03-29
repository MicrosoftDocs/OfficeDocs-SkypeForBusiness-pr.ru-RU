---
title: Изменения, сделанные Grant-CsOUPermission в Скайп для Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Делегирование Скайп для администрирования сервера, можно добавить разрешения для указанного подразделения (OU), чтобы участниками универсальных групп RTC, созданные подготовки леса может обращаться к подразделения не являются членами группы "Администраторы домена".
ms.openlocfilehash: 1313394248da2dcaeb9843bd689b2e2da3c51f96
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Изменения, сделанные Grant-CsOUPermission в Скайп для Business Server
 
Делегирование Скайп для администрирования сервера, можно добавить разрешения для указанного подразделения (OU), чтобы участниками универсальных групп RTC, созданные подготовки леса может обращаться к подразделения не являются членами группы "Администраторы домена". 
  
Командлет **Grant-CsOuPermission** предоставляет разрешения объектам в указанном Подразделении, как указано в следующих таблицах.
  
## <a name="granting-permission-for-user-objects"></a>Предоставление разрешений для объектов-пользователей

При запуске командлета **Grant-CsOuPermission** для объектов-пользователей в Подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам-пользователям**

|**Группа**|**Разрешение**|**Применимо к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Public-Information  <br/> Чтение General-Information  <br/> Чтение ограничения учетной записи пользователя  <br/> |К дочерним объектам пользователей  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись msExchUCVoiceMailSettings  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним объектам пользователей  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Предоставление разрешений для объектов-компьютеров

При запуске командлета **Grant-CsOuPermission** для объектов-компьютеров в Подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам-компьютерам**

|**Группа**|**Разрешение**|**Применимо к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение Public-Information  <br/> Чтение проверенные DNS-имени узла  <br/> |Объектам-потомкам Computer  <br/> |
|RTCUniversalUserAdmins  <br/> |Чтение Public-Information  <br/> Чтение проверенные DNS-имени узла  <br/> |Объектам-потомкам Computer  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Предоставление разрешений для объектов AppContact или контактов

При запуске командлета **Grant-CsOuPermission** для контактных объектов или объектов AppContact в Подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные контактным объектам и объектам AppContact**

|**Группа**|**Разрешение**|**Применимо к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Public-Information  <br/> Чтение General-Information  <br/> Чтение Personal-Information  <br/> Чтение ограничения учетной записи пользователя  <br/> |К дочерним контактным объектам  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись otherIpPhone  <br/> Запись displayName  <br/> Запись description  <br/> Запись telephoneNumber  <br/> Запись msExchUCVoiceMailSettings  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним контактным объектам  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Предоставление разрешений для объектов-устройств

При запуске командлета **Grant-CsOuPermission** для объектов-устройств в Подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам-устройствам**

|**Группа**|**Разрешение**|**Применимо к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Public-Information  <br/> Чтение Personal-Information  <br/> Чтение General-Information  <br/> Чтение ограничения учетной записи пользователя  <br/> |К дочерним контактным объектам  <br/> |
|RTCUniversalUserAdmins  <br/> |Создание дочернего объекта  <br/> Удаление дочернего объекта  <br/> Удаление дерева  <br/> |Контакт  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись displayName  <br/> Запись description  <br/> Запись telephoneNumber  <br/> |К дочерним объектам пользователей  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись otherIpPhone  <br/> Запись displayName  <br/> Запись description  <br/> Запись telephoneNumber  <br/> Запись msExchUCVoiceMailSettings  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним контактным объектам  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Предоставление разрешений для объектов InetOrgPerson

При запуске командлета **Grant-CsOuPermission** для объектов InetOrgPerson в Подразделении группам предоставляются разрешения, как показано в следующей таблице.
  
**Разрешения, предоставленные объектам InetOrgPerson**

|**Группа**|**Разрешение**|**Применимо к**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Репликация изменений каталога  <br/> |Только к этому объекту  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Список содержимого  <br/> Чтение всех свойств  <br/> Разрешения на чтение  <br/> |Только к этому объекту  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Чтение RTCUserSearchPropertySet  <br/> Чтение RTCUserProvisioningPropertySet  <br/> Чтение RTCPropertySet  <br/> Чтение Personal-Information  <br/> Чтение Public-Information  <br/> Чтение General-Information  <br/> Чтение ограничения учетной записи пользователя  <br/> |К дочерним объектам InetOrgPerson  <br/> |
|RTCUniversalUserAdmins  <br/> |Запись RTCUserSearchPropertySet  <br/> Запись RTCUserProvisioningPropertySet  <br/> Запись RTCPropertySet  <br/> Запись proxyAddresses  <br/> |К дочерним объектам InetOrgPerson  <br/> |
   

