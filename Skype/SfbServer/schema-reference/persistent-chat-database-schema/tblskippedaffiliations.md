---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (как правило, из-за ошибок доступа к службам доступа к доменам Active Directory).
ms.openlocfilehash: 49272b03ae8ac4a3c53ea2cd99d2ed06a30c0682
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749748"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (как правило, из-за ошибок доступа к службам доступа к доменам Active Directory).
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Идентификатор субъекта.  <br/> |
|affDescription  <br/> |nvarchar (256), не NULL  <br/> |Строка, идентифицирующая принадлежность.  <br/> Формат: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, не NULL  <br/> |Идентификатор субъекта, обновившего эту строку. Он всегда равен 1 (системный пользователь) поскольку синхронизация Active Directory является единственным источником этих записей.  <br/> |
   
**Keys**

|**Column(s)**|**Описание**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   

