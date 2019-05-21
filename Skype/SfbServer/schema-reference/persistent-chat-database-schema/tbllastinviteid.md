---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: Тблластинвитеид — это последний идентификатор приглашения, созданный (и использованный в таблице ТблпринЦипалинвитес) для каждого пользователя.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295358"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
Тблластинвитеид — это последний идентификатор приглашения, созданный (и использованный в таблице ТблпринЦипалинвитес) для каждого пользователя.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|Ластинвитеид  <br/> |int, NOT NULL  <br/> |Идентификатор приглашения последнего использован.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|Принид  <br/> |Первичный ключ.  <br/> |
|Принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   
## <a name="see-also"></a>См. также

[tblPrincipalInvites](tblprincipalinvites.md)
