---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814607"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|валуеид  <br/> |smallint, NOT NULL  <br/> |Идентификатор значения.  <br/> |
|attributeID  <br/> |smallint, NOT NULL  <br/> |Идентификатор атрибута.  <br/> |
|attributeValue  <br/> |nvarchar (256), NOT NULL  <br/> |Имя значения.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|валуеид  <br/> |Первичный ключ.  <br/> |
|attributeID  <br/> |Внешний ключ с подстановкой в таблице Тбленуматтрибуте. attributeID.  <br/> |
   
**Значения таблицы**

|**валуеид**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |закрытые  <br/> |
|3  <br/> |1  <br/> |област  <br/> |
|4  <br/> |2  <br/> |нормальный  <br/> |
|5  <br/> |2  <br/> |аудиториум  <br/> |
|6  <br/> |1  <br/> |запуска  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
