---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData содержит события соответствия, которые не были обработаны адаптером соответствия еще.
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212616"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData содержит события соответствия, которые не были обработаны адаптером соответствия еще.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, не может быть null  <br/> |Идентификатор события.  <br/> |
|entryDate  <br/> |smalldatetime, не null  <br/> |Время вставки (может относиться к далекому будущему для cmplType = 9, так как запись в этом случае является всего лишь заполнителем).  <br/> |
|cmplType  <br/> |int, не null  <br/> | Тип события соответствия нормативным требованиям: <br/>  1: чата <br/>  2: ответ на чат <br/>  3: Загрузка файла <br/>  4: Отправка файла <br/>  9: промежуточная передача файла <br/>  10: удаление чата (с заменой) <br/>  11: очистка чата <br/> |
|cmplTime  <br/> |bigint, не может быть null  <br/> |Метка времени для события.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), отлично от null  <br/> |Канал универсальный код ресурса (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Идентификатор (в соответствии с таблицей tblChat.chatId) чата.  <br/> |
|cmplUserID  <br/> |int, не null  <br/> |Идентификатор субъекта плакат (в соответствии с таблицей tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), отлично от null  <br/> |URI пользователя.  <br/> |
|cmplMessage  <br/> |nvarchar (максимум)  <br/> |Сообщение (кодировка зависит от cmplType).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|cmplEventID  <br/> |Первичный ключ.  <br/> |
   

