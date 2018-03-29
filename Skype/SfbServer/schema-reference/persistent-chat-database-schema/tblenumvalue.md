---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint, не может быть null  <br/> |ИД значения.  <br/> |
|attributeID  <br/> |smallint, не может быть null  <br/> |Идентификатор атрибута.  <br/> |
|attributeValue  <br/> |nvarchar (256), отлично от null  <br/> |Имя значения.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|valueID  <br/> |Первичный ключ.  <br/> |
|attributeID  <br/> |Внешний ключ с поиском в таблице tblEnumAttribute.attributeID.  <br/> |
   
**Значения таблицы**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |закрытые  <br/> |
|3  <br/> |1  <br/> |область  <br/> |
|4  <br/> |2  <br/> |Обычный  <br/> |
|5  <br/> |2  <br/> |аудитория  <br/> |
|6  <br/> |1  <br/> |Откройте  <br/> |
   
## <a name="see-also"></a>См. также

#### 

[tblNode](tblnode.md)

