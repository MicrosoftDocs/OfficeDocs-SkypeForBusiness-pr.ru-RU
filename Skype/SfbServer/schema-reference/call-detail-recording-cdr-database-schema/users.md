---
title: Таблица User
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Таблица Users является вспомогательной таблицей. В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814807"
---
# <a name="users-table"></a>Таблица User
 
Таблица Users является вспомогательной таблицей. В каждой записи в таблице хранятся сведения о пользователях, участвующих в звонках или сеансах с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**некступдатетс** <br/> |datetime  <br/> ||Метка времени для внутреннего использования.  <br/> |
|**Идентификатора пользователя** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|**усерури** <br/> |nvarchar (450)  <br/> | <br/> |URI пользователя.  <br/> |
|**TenantId** <br/> |целое  <br/> |Другом  <br/> |Идентификатор клиента этого пользователя. Дополнительные сведения см. в [таблице "клиенты](tenants.md) ". <br/> |
|**уритипеид** <br/> |целое  <br/> |Другом  <br/> |Тип универсального кода ресурса (URI) этого пользователя. Для получения дополнительных сведений ознакомьтесь с [таблицей уритипес](uritypes.md) . <br/> |
   

