---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812017"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|аффдескриптион  <br/> |nvarchar (256), NOT NULL  <br/> |Строка, указывающая на принадлежность.  <br/> Формат: GUID: _{0}_ uri: _{1}_> ID:_{2}_ <br/> |
|упдатедби  <br/> |int, NOT NULL  <br/> |Идентификатор участника, который обновил эту строку. Это всегда 1 (Системный пользователь), так как служба каталогов Active Directory — это единственный источник этих записей.  <br/> |
   
**Параметры**

|**Столбцы (-ы)**|**Описание**|
|:-----|:-----|
|\<Принид, Аффдескриптион\>  <br/> |Первичный ключ.  <br/> |
|принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

