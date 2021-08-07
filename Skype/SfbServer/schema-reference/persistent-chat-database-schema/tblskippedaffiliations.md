---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (как правило, из-за ошибок доступа к службам доступа к доменам Active Directory).
ms.openlocfilehash: ddc8ef78f083235ccde122a3f26fd7f37e34b71d9643b1c729f802e3e080c413
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305371"
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

|**Column(s)**|**Description**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   

