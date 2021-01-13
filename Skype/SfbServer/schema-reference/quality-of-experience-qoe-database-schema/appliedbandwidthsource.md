---
title: Таблица AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831409"
---
# <a name="appliedbandwidthsource-table"></a>Таблица AppliedBandwidthSource
 
Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий источник.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Уникальные  <br/> |Источник применяемого ограничения пропускной способности. В нем описывается источник ограничения пропускной способности (например, "Сервер политики", "TURN Server" или "Модальность").  <br/> |
   

