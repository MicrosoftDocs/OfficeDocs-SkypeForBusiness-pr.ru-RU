---
title: Изменения схемы в Скайп для Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Прежде чем развертывать и использование Скайп для Business Server, необходимо подготовить доменных служб Active Directory путем расширения схемы. Расширения схемы добавьте классы и атрибуты, которые необходимы Скайп для Business Server.
ms.openlocfilehash: 8594ff3a25c7af7ef8c57468a8900d3abbb7f790
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240919"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Изменения схемы в Скайп для Business Server
 
Прежде чем развертывать и использование Скайп для Business Server, необходимо подготовить доменных служб Active Directory путем расширения схемы. Расширения схемы добавьте классы и атрибуты, которые необходимы Скайп для Business Server.

> [!NOTE]
> При обновлении с Lync Server 2013 для Скайп для Business Server 2015, не изменяются схемы и поэтому эта статья не применяется.
  
Скайп для Business Server требуется несколько новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты. Кроме того объем сведений о конфигурации Скайп для Business Server хранится в центрального хранилища управления вместо в Доменные службы Active Directory как в предыдущих версиях. Следующие сведения по-прежнему хранятся в Доменных службах Active Directory в Скайп для Business Server:
  
- **Расширения схемы**:
    
  - Расширения объекта пользователя
    
  - Расширения для классов для обеспечения обратной совместимости с предыдущими версиями сервера Lync.
    
- **Данные** (хранятся в Скайп для расширенной схеме Business Server и существующей схеме классов):
    
  - Пользователь SIP универсальный код ресурса (URI) и другие параметры пользователей
    
  - Контактные объекты для приложений, таких как группа ответа и помощник по конференц-связи
    
  - Указатель на центральном хранилище управления
    
  - Учетная запись проверки подлинности Kerberos (дополнительный объект-компьютер)
    
В этом разделе описываются изменения схемы Active Directory, необходимые для Скайп для Business Server. Изменения схемы, которые были представлены в предыдущих версиях Office Communications Server не приведены. Список классов и их описания в разделе [классы схемы и описания в Скайп для Business Server](schema-classes-and-descriptions.md). Список атрибутов и их описания в разделе [атрибуты схемы и описания в Скайп для Business Server](schema-attributes-and-descriptions.md). Список классов с атрибутами они могут содержать см [атрибуты схемы по классам в Скайп для Business Server](schema-attributes-by-class.md).
  
Префикс msRTCSIP идентифицирует классы и атрибуты, относящиеся к Скайп для Business Server.
  
## <a name="new-active-directory-attributes"></a>Новые атрибуты Active Directory

В следующей таблице описываются атрибуты Active Directory, добавленные Скайп Business Server.
  
**Атрибуты, добавленные Скайп для Business Server**

|**Атрибут**|**Описание**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Этот атрибут со множеством значений содержит идентификаторы для хранения политик, которые применяются к пользователю. Удержаний политик сохраняются элементы почтовых ящиков для пользователя во время выполнения удержания. Этот атрибут используется совместно с Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Это SIP, маршрутизация идентификатор группы. Пользователи в той же группе будет регистрировать на тот же сервер переднего плана.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Этот атрибут используется для хранения зеркальных внутреннего сервера SQL Server, используемая пулом переднего плана.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Измененные классы Active Directory

В следующей таблице описываются классы Active Directory, изменяемые Скайп Business Server.
  
**Классы, изменяемые Скайп для Business Server**

|**Класс**|**ИЗМЕНИТЬ**|**Класс или атрибут**|
|:-----|:-----|:-----|
|Пользователь  <br/> |Добавление: mayContain  <br/> Добавление: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Контакт  <br/> |Добавление: mayContain  <br/> Добавление: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Получатель почты  <br/> |Добавление: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Добавление: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

