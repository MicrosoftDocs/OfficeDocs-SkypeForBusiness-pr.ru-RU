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
ms.localizationpriority: medium
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue — это встроенная таблица, которая содержит значения отображения и поведения атрибутов, используемых в таблице Node.
ms.openlocfilehash: 0854b20316f0200e2521109880cad32862524c22
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619705"
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
|2   <br/> |1   <br/> |частный  <br/> |
|3   <br/> |1   <br/> |область  <br/> |
|4   <br/> |2   <br/> |нормальный  <br/> |
|5   <br/> |2   <br/> |аудитория  <br/> |
|6   <br/> |1   <br/> |open  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
