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
ms.openlocfilehash: d5c710e1301344c853ef39aeff3b57f62c630c95
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505127"
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

|**ID**|**Роль**|**Описание**|**Пользователь**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Любой  <br/> |Универсальный участника без известных типа. Не используется в таблице tblPrincipal.  <br/> ||
|2  <br/> |AnyUser  <br/> |Универсальный участника пользовательского типа. Не используется в таблице tblPrincipal.  <br/> |Да  <br/> |
|3  <br/> |AnyGroup  <br/> |Универсальный участника с группой семантических. Не используется в таблице tblPrincipal.  <br/> ||
|4  <br/> |Системного пользователя  <br/> |Используемое во внутренней сети с сервера сохраняемого чата.  <br/> ||
|5  <br/> |Пользователь  <br/> |Обычный пользователь.  <br/> |Да  <br/> |
|8  <br/> |КОНТРОЛЛЕР ДОМЕНА  <br/> |Контроллер домена Active Directory доменных служб.  <br/> ||
|9  <br/> |Группа  <br/> |Группа безопасности Active Directory.  <br/> ||
| 10  <br/> |Папка  <br/> |Active Directory контейнер или подразделение.  <br/> ||
   
## <a name="see-also"></a>См. также

[tblPrincipal](tblprincipal.md)