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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.
ms.openlocfilehash: 5796a50a5e9ab121f8c84f81bd00f417843b2c86c5863dafb6d639b1fc0bab55
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305141"
---
# <a name="dialog-table"></a>Диалоговая таблица
 
Таблица Dialog является вспомогательной. Каждая запись представляет одно диалоговое окно SIP.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Время получения  агентом качества обслуживания первого отчета от звонящего или вызываемого абонента. Используется совместно с SessionSeq для уникальной идентификации сеанса.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Порядковый номер, позволяющий различать сеансы с одинаковым ConferenceDateTime.  <br/> |
|**Диалоговое окно** <br/> |varchar (256)  <br/> ||Глобальный уникальный идентификатор диалогового окна.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |Контрольная сумма идентификатора диалогового окна.  <br/> |
   

