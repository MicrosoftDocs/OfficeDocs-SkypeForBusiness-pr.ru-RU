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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295456"
---
# <a name="tblconfig"></a>tblConfig
 
Тблконфиг включает в себя неподдерживаемую конфигурацию сервера чатов в одной строке.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Конфиглабел  <br/> |nvarchar (255), NOT NULL  <br/> |Группа "пул".  <br/> |
|Конфигконтент  <br/> |nvarchar (max)  <br/> |Содержимое конфигурации.  <br/> |
|Конфигпулид  <br/> |GUID, а не NULL  <br/> |Уникальный идентификатор экземпляра базы данных.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|Конфиглабел  <br/> |Первичный ключ.  <br/> |
   

