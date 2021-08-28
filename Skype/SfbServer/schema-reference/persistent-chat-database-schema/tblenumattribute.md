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
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.
ms.openlocfilehash: 7f55d99a028a7af7979394321bb543db11bb1933
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628551"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
Жестко запрограммированная таблица tblEnumAttribute содержит атрибуты Visibility и Behavior, которые используются в таблице Node.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, не может быть null  <br/> |Идентификатор атрибута.  <br/> |
|attributeName  <br/> |nvarchar (256), не может быть null  <br/> |Имя атрибута.  <br/> |
   
**Ключ**

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
