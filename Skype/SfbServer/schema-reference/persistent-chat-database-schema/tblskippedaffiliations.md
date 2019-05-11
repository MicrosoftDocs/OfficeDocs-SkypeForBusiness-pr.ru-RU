---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит принадлежности, которые не удалось прочитать (обычно вследствие ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924943"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations содержит принадлежности, которые не удалось прочитать (обычно вследствие ошибок доступа к доменным службам Active Directory).
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|affDescription  <br/> |nvarchar (256), отлично от null  <br/> |Строка, идентифицирующая принадлежность.  <br/> Имеет формат: guid: _{0}_ uri: _{1}_> id:_{2}_ <br/> |
|updatedBy  <br/> |int, не null  <br/> |Идентификатор субъекта, который обновления этой строки. Это всегда 1 (система пользователя), так как синхронизации Active Directory является единственным источником для этих операций.  <br/> |
   
**Ключи**

|**Столбцы**|**Описание**|
|:-----|:-----|
|\<prinID affDescription\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

