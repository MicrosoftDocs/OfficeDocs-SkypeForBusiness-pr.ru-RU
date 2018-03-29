---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Таблица tblPrincipalType содержит типы субъектов для возможности в таблице tblPrincipal.
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
Таблица tblPrincipalType содержит типы субъектов для возможности в таблице tblPrincipal.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint, не может быть null  <br/> |Идентификатор типа субъекта.  <br/> |
|ptypeDesc  <br/> |nvarchar (256), отлично от null  <br/> |Описание типа.  <br/> |
|ptypeIsSystemUser  <br/> |bit, не может быть null  <br/> |Значение true, если тип соответствует субъектам, которые используются для внутренних целей.  <br/> |
|ptypeIsUser  <br/> |bit, не может быть null  <br/> |Значение true, если тип соответствует пользователям.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|ptypeID  <br/> |Первичный ключ.  <br/> |
   
**Значения субъектов**

|**ИДЕНТИФИКАТОР**|**Role (Роль)**|**Описание**|**Пользователь**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Любой  <br/> |Универсальный участника без известных типа. Не используется в таблице tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Универсальный участника пользовательского типа. Не используется в таблице tblPrincipal.  <br/> |Да  <br/> |
|3  <br/> |AnyGroup  <br/> |Универсальный участника с группой семантических. Не используется в таблице tblPrincipal.  <br/> ||
|4  <br/> |Системного пользователя  <br/> |Используемое во внутренней сети с сервера сохраняемого чата.  <br/> ||
|5  <br/> |Пользователь  <br/> |Обычный пользователь.  <br/> |Да  <br/> |
|8  <br/> |КОНТРОЛЛЕР ДОМЕНА  <br/> |Контроллер домена Active Directory доменных служб.  <br/> ||
|9  <br/> |Группа  <br/> |Группа безопасности Active Directory.  <br/> ||
|10  <br/> |Папка  <br/> |Active Directory контейнер или подразделение.  <br/> ||
   
## <a name="see-also"></a>См. также

#### 

[tblPrincipal](tblprincipal.md)

