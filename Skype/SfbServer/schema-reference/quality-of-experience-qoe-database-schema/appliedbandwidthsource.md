---
title: Таблица AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
ms.openlocfilehash: 772afa1ffe6ce34dc38676193825c0f2891d7bea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761837"
---
# <a name="appliedbandwidthsource-table"></a>Таблица AppliedBandwidthSource
 
Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий источник.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Источник применяемого ограничения пропускной способности. В нем описывается, откуда приходит ограничение пропускной способности (например, "Сервер политики", "TURN Server" или "Modality").  <br/> |
   

