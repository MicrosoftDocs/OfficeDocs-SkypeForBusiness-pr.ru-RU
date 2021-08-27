---
title: Диалоговая таблица
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.
ms.openlocfilehash: 0310845ada3b86346ccc6b410a5c7539b16689f3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603728"
---
# <a name="dialog-table"></a>Диалоговая таблица
 
Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Время получения  агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.  <br/> |
|**Диалоговое окно** <br/> |varchar (256)  <br/> ||Глобальный уникальный идентификатор диалогового окна.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Контрольная сумма идентификатора диалогового окна.  <br/> |
   

