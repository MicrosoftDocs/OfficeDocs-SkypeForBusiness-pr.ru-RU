---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814627"
---
# <a name="tblconfig"></a>tblConfig
 
Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|конфиглабел  <br/> |nvarchar (255), NOT NULL  <br/> |Группа "пул".  <br/> |
|конфигконтент  <br/> |nvarchar (max)  <br/> |Содержимое конфигурации.  <br/> |
|конфигпулид  <br/> |GUID, а не NULL  <br/> |Уникальный идентификатор экземпляра базы данных.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|конфиглабел  <br/> |Первичный ключ.  <br/> |
   

