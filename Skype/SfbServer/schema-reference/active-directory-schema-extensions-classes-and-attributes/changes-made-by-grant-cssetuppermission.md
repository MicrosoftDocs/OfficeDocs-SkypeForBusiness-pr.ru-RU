---
title: Изменения, сделанные Grant-CsSetupPermission в Скайп для Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Делегирование установки, вы может предоставить разрешения универсальной группы RTCUniversalServerAdmins для конкретных Active Directory подразделения (OU), включив члены группы RTCUniversalServerAdmins, Подразделения для установки Скайп для Business Server в Указанный домен не члены группы "Администраторы домена".
ms.openlocfilehash: 3976cb22a947e9a9590989895cf688465c8f5ef0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213391"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Изменения, сделанные Grant-CsSetupPermission в Скайп для Business Server
 
Делегирование установки, вы может предоставить разрешения универсальной группы RTCUniversalServerAdmins для конкретных Active Directory подразделения (OU), включив члены группы RTCUniversalServerAdmins, Подразделения для установки Скайп для Business Server в Указанный домен не члены группы "Администраторы домена". 
  
Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на Подразделение, как указано в следующей таблице:
  
**Разрешения, предоставленные объектам в Подразделении**

|**Разрешения применяются к:**|**Предоставляемые разрешения**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Специальный доступ: <br/>  Чтение в servicePrincipalName <br/>  Запись в servicePrincipalName <br/>  Удаление дерева <br/>  Репликация изменений каталога <br/> |
|Объектам-потомкам serviceConnectionPoint  <br/> | Специальный доступ: <br/>  Разрешения на чтение <br/>  Разрешения на запись <br/>  Создание дочернего объекта <br/>  Удаление дочернего объекта <br/>  Список содержимого <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объекты потомкам msRTCSIP сервера  <br/> | Специальный доступ: <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объекты потомкам msRTCSIP-WebComponents  <br/> | Специальный доступ: <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объекты потомкам msRTCSIP-MCU  <br/> | Специальный доступ: <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объекты потомкам msRTCSIP-MediationServer  <br/> | Специальный доступ: <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объекты потомкам msRTCSIP-ApplicationServer  <br/> | Специальный доступ: <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объекты потомкам msRTCSIP-ConnectionPoint  <br/> | Специальный доступ: <br/>  Запись свойства <br/>  Чтение свойства <br/>  Удаление дерева <br/> |
|Объектам-потомкам Computer  <br/> | Специальный доступ для serviceConnectionPoint на: <br/>  Создание дочерних объектов <br/>  Удаление дочерних объектов <br/>  Удаление дерева <br/>  Специальный доступ для общедоступных сведений: <br/>  Чтение свойства <br/>  Специальный доступ для имени узла DNS: <br/>  Чтение свойства <br/> |
   

