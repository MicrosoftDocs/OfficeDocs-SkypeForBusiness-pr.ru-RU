---
title: Изменения, внесенные Grant-CsSetupPermission в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного организационного подразделения Active Directory, что позволяет членам группы RTCUniversalServerAdmins устанавливать Skype для бизнеса Server в указанном домене без участия в группе администраторов домена.
ms.openlocfilehash: 06632a741fd8f06f3f6b0a5c48f568d7e6d16832
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745815"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Изменения, внесенные Grant-CsSetupPermission в Skype для бизнеса Server
 
Чтобы делегировать установку, можно предоставить разрешения универсальной группе RTCUniversalServerAdmins для определенного организационного подразделения Active Directory, что позволяет членам группы RTCUniversalServerAdmins устанавливать Skype для бизнеса Server в указанном домене без участия в группе администраторов домена. 
  
Командлет **Grant-CsSetupPermission** предоставляет группе RTCUniversalServerAdmins разрешения на подразделение, как показано в следующей таблице.
  
**Разрешения. предоставляемые на объекты в подразделении**

|**Разрешения применяются к**|**Предоставляемые разрешения**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Особый доступ на: <br/>  чтение в servicePrincipalName; <br/>  запись в servicePrincipalName; <br/>  удаление дерева; <br/>  репликацию изменений каталога. <br/> |
|Объектам-потомкам serviceConnectionPoint  <br/> | Особый доступ на: <br/>  чтение; <br/>  запись; <br/>  создание дочерних объектов; <br/>  удаление дочерних объектов; <br/>  перечень содержимого; <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам msRTCSIP-Server  <br/> | Особый доступ на: <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам msRTCSIP-WebComponents  <br/> | Особый доступ на: <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам msRTCSIP-MCU  <br/> | Особый доступ на: <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам msRTCSIP-MediationServer  <br/> | Особый доступ на: <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам msRTCSIP-ApplicationServer  <br/> | Особый доступ на: <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам msRTCSIP-ConnectionPoint  <br/> | Особый доступ на: <br/>  запись свойства; <br/>  чтение свойства; <br/>  удаление дерева. <br/> |
|Объектам-потомкам Computer  <br/> | Особый доступ для serviceConnectionPoint на: <br/>  создание дочерних объектов; <br/>  удаление дочерних объектов; <br/>  удаление дерева. <br/>  Специальный доступ для общедоступных сведений на: <br/>  чтение свойства. <br/>  Специальный доступ для имени узла DNS на: <br/>  чтение свойства. <br/> |
   

