---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемого в таблице tblPrincipalInvites) для каждого пользователя.
ms.openlocfilehash: f7a7fdf9038de9a8bf4dcb22bce79f294ea231e5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768453"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемого в таблице tblPrincipalInvites) для каждого пользователя.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Код участника.  <br/> |
|lastInviteID  <br/> |int, не null  <br/> |Последний использованный код приглашения.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>См. также

[tblPrincipalInvites](tblprincipalinvites.md)
