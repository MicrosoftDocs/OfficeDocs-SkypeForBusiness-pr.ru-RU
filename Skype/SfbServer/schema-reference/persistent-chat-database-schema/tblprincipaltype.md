---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.
ms.openlocfilehash: e058af1fa45c87f97b34ac9c5b931b7d7cb9114205c702c732984adafc04d3fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281652"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
Таблица tblPrincipalType содержит типы субъектов для разделения содержимого таблицы tblPrincipal по категориям.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, не может быть null  <br/> |Идентификатор типа субъекта.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), не может быть null  <br/> |Описание типа.  <br/> |
|ptypeIsSystemUser  <br/> |bit, не может быть null  <br/> |Имеет значение True, если тип соответствует субъектам, которые используются во внутренних целях.  <br/> |
|ptypeIsUser  <br/> |bit, не может быть null  <br/> |Имеет значение True, если тип соответствует пользователям.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|ptypeID  <br/> |Первичный ключ.  <br/> |
   
**Значения субъектов**

|**ID**|**Роль**|**Описание**|**Пользователь**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Любой  <br/> |Общий субъект неизвестного типа. Не используется в таблице tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Общий субъект типа "пользователь". Не используется в таблице tblPrincipal.  <br/> |Да  <br/> |
|3  <br/> |AnyGroup  <br/> |Общий субъект типа "группа". Не используется в таблице tblPrincipal.  <br/> ||
|4   <br/> |SystemUser  <br/> |Основной, используемый внутренним сервером сохраняемой чат-сервера.  <br/> ||
|5   <br/> |Пользователь  <br/> |Обычный пользователь.  <br/> |Да  <br/> |
|8   <br/> |DC  <br/> |Контроллер домена Active Directory Domain Services.  <br/> ||
|9   <br/> |Group  <br/> |Группа безопасности Active Directory.  <br/> ||
|10   <br/> |Folder  <br/> |Контейнер или подразделение Active Directory.  <br/> ||
   
## <a name="see-also"></a>См. также

[tblPrincipal](tblprincipal.md)
