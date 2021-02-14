---
title: Изменения схемы в Skype для бизнеса Server
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
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Перед развертыванием и эксплуатацией Skype для бизнеса Server необходимо подготовить доменные службы Active Directory путем расширения схемы. Расширения схемы добавляют классы и атрибуты, необходимые Skype для бизнеса Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813579"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Изменения схемы в Skype для бизнеса Server
 
Перед развертыванием и эксплуатацией Skype для бизнеса Server необходимо подготовить доменные службы Active Directory путем расширения схемы. Расширения схемы добавляют классы и атрибуты, необходимые Skype для бизнеса Server.

> [!NOTE]
> При обновлении Lync Server 2013 до Skype для бизнеса Server 2015 изменения схемы не вносяся, поэтому эта статья не применяется.
  
Skype для бизнеса Server требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты. Кроме того, большая часть сведений о конфигурации Skype для бизнеса Server хранится в центральном хранилище управления, а не в AD DS, как в предыдущих версиях. Следующие сведения по-прежнему хранятся в AD DS в Skype для бизнеса Server:
  
- **Расширения схемы**:
    
  - расширения объектов-пользователей;
    
  - Расширения для классов для обеспечения обратной совместимости с поддерживаемыми предыдущими версиями Lync Server.
    
- **Данные** (хранимые в расширенной схеме Skype для бизнеса Server и в существующих классах схемы):
    
  - универсальный код ресурса (URI) SIP и другие параметры пользователя;
    
  - контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;
    
  - Указатель на центральное хранилище управления
    
  - Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)
    
В этом разделе описываются изменения схемы Active Directory, необходимые для Skype для бизнеса Server. В нем не описываются изменения схемы, которые были представлены в предыдущих версиях Office Communications Server. Список классов и их описания см. в описании и классах схемы [в Skype для бизнеса Server.](schema-classes-and-descriptions.md) Список атрибутов и их описания см. в описании и атрибутах схемы [в Skype для бизнеса Server.](schema-attributes-and-descriptions.md) Список классов с атрибутами, которые они могут содержать, см. в атрибутах [схемы по классам в Skype для бизнеса Server.](schema-attributes-by-class.md)
  
Префикс msRTCSIP определяет классы и атрибуты, специфические для Skype для бизнеса Server.
  
## <a name="new-active-directory-attributes"></a>Новые атрибуты Active Directory

В следующей таблице описываются атрибуты Active Directory, добавленные Skype для бизнеса Server.
  
**Атрибуты, добавленные в Skype для бизнеса Server**

|**Атрибут**|**Описание**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю. Политики хранения определяют срок хранения элементов почтового ящика для пользователя. Этот атрибут является общим для Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Этот атрибут используется для хранения зеркального SQL Server, используемого пулом переднего входа.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Измененные классы Active Directory

В следующей таблице описаны классы Active Directory, измененные в Skype для бизнеса Server.
  
**Классы, измененные в Skype для бизнеса Server**

|**Class**|**Изменение**|**Класс или атрибут**|
|:-----|:-----|:-----|
|Пользователь  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Контакт  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

