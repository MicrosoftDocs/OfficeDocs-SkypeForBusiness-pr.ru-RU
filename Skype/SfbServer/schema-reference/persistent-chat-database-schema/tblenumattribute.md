---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809719"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, не может быть null  <br/> |Идентификатор атрибута.  <br/> |
|attributeName  <br/> |nvarchar (256), не может быть null  <br/> |Имя атрибута.  <br/> |
   
**Раздел**

|**Столбец**|**Описание**|
|:-----|:-----|
|attributeID  <br/> |Первичный ключ.  <br/> |
   
**Значения таблицы**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1   <br/> |Видимость.  <br/> |
|2   <br/> |Поведение.  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
