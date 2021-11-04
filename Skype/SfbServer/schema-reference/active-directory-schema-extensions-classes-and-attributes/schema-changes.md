---
title: Схема изменяется в Skype для бизнеса Server
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
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Прежде чем развернуть и Skype для бизнеса Server, необходимо подготовить службы домена Active Directory, расширив схему. Расширения схем добавляют классы и атрибуты, необходимые Skype для бизнеса Server.
ms.openlocfilehash: 000aad35a546556a2a6bceaedc0d0fdb9deb2420
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743285"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Схема изменяется в Skype для бизнеса Server
 
Прежде чем развернуть и Skype для бизнеса Server, необходимо подготовить службы домена Active Directory, расширив схему. Расширения схем добавляют классы и атрибуты, необходимые Skype для бизнеса Server.

> [!NOTE]
> При обновлении с Lync Server 2013 до Skype для бизнеса Server 2015 г. изменения схемы не внесены, поэтому эта статья не применяется.
  
Skype для бизнеса Server требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты. Кроме того, большая часть сведений о конфигурации Skype для бизнеса Server хранится в хранилище Central Management, а не в AD DS, как в предыдущих версиях. Следующие сведения по-прежнему хранятся в AD DS в Skype для бизнеса Server:
  
- **Расширения схемы**:
    
  - расширения объектов-пользователей;
    
  - Расширения для классов для поддержания обратной совместимости с поддерживаемыми предыдущими версиями Lync Server.
    
- **Данные** (хранимые Skype для бизнеса Server расширенной схеме и в существующих классах схемы):
    
  - универсальный код ресурса (URI) SIP и другие параметры пользователя;
    
  - контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;
    
  - Указатель на центральный магазин управления
    
  - Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)
    
В этом разделе описываются изменения схемы Active Directory, необходимые для Skype для бизнеса Server. Она не описывает изменения схемы, которые были представлены предыдущими версиями Office Communications Server. Список классов и их описаний см. в [Skype для бизнеса Server.](schema-classes-and-descriptions.md) Список атрибутов и их описаний см. в [Skype для бизнеса Server.](schema-attributes-and-descriptions.md) Список классов с атрибутами, которые они могут содержать, см. в [Skype для бизнеса Server.](schema-attributes-by-class.md)
  
Префикс msRTCSIP определяет классы и атрибуты, которые являются Skype для бизнеса Server.
  
## <a name="new-active-directory-attributes"></a>Новые атрибуты Active Directory

В следующей таблице описываются атрибуты Active Directory, добавленные Skype для бизнеса Server.
  
**Атрибуты, добавленные Skype для бизнеса Server**

|**Атрибут**|**Описание**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю. Политики хранения определяют срок хранения элементов почтового ящика для пользователя. Этот атрибут совместно с Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Этот атрибут используется для хранения зеркального SQL Server, используемого пулом переднего конца.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Измененные классы Active Directory

В следующей таблице описываются классы Active Directory, измененные Skype для бизнеса Server.
  
**Классы, измененные Skype для бизнеса Server**

|**Class**|**Изменение**|**Класс или атрибут**|
|:-----|:-----|:-----|
|User  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

