---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809859"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData содержит события соответствия нормативным требованиям, которые еще не были обработаны адаптером соответствия.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, не NULL  <br/> |Идентификатор события.  <br/> |
|entryDate  <br/> |smalldatetime, не NULL  <br/> |Время вставки (может относиться к далекому будущему для  cmplType=9, так как в этом случае запись является всего лишь заполнителем).  <br/> |
|cmplType  <br/> |int, не NULL  <br/> | Типа события соответствия нормативным требованиям: <br/>  1: Чат <br/>  2: Ответ на чат <br/>  3: Загрузка файла <br/>  4: Отправка файла <br/>  9: Промежуточная передача файла <br/>  10: Удаление чата (с заменой) <br/>  11: Очистка чата <br/> |
|cmplTime  <br/> |bigint, не NULL  <br/> |Метка времени для события.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), не NULL  <br/> |Универсальный код ресурса (URI) для канала.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Идентификатор чата (в соответствии с таблицей tblChat.chatId).  <br/> |
|cmplUserID  <br/> |int, не NULL  <br/> |Идентификатор субъекта для отправителя (в соответствии с таблицей tblPrincipal.prinID).  <br/> |
|cmplUserUri  <br/> |nvarchar (255), не NULL  <br/> |Универсальный код ресурса (URI) для пользователя.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Сообщение (кодировка зависит от cmplType).  <br/> |
   
**Раздел**

|**Столбец**|**Описание**|
|:-----|:-----|
|cmplEventID  <br/> |Первичный ключ.  <br/> |
   

