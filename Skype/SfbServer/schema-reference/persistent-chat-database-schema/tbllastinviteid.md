---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504854"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
Таблица tblLastInviteId содержит последний код приглашения, созданного (и используемый в таблице tblPrincipalInvites) для каждого пользователя.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|lastInviteID  <br/> |int, не null  <br/> |Последний использованный код приглашения.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   
## <a name="see-also"></a>См. также

[tblPrincipalInvites](tblprincipalinvites.md)