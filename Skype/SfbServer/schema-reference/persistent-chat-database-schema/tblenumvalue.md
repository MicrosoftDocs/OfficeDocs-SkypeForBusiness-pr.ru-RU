---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816029"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, not null  <br/> |ИД значения.  <br/> |
|attributeID  <br/> |smallint, не может быть null  <br/> |ИД атрибута.  <br/> |
|attributeValue  <br/> |nvarchar (256), not null  <br/> |Имя значения.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|valueID  <br/> |Первичный ключ.  <br/> |
|attributeID  <br/> |Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.  <br/> |
   
**Значения таблицы**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2   <br/> |1   <br/> |private  <br/> |
|3   <br/> |1   <br/> |scope  <br/> |
|4   <br/> |2   <br/> |normal  <br/> |
|5   <br/> |2   <br/> |аудитория  <br/> |
|6   <br/> |1   <br/> |open  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
