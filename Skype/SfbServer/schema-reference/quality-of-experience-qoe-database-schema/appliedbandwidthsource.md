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
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
ms.openlocfilehash: 2daa4d35d11c000503fa83c79963df14886f50cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633473"
---
# <a name="appliedbandwidthsource-table"></a>Таблица AppliedBandwidthSource
 
Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий источник.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Источник применяемого ограничения пропускной способности. В нем описывается, откуда приходит ограничение пропускной способности (например, "Сервер политики", "TURN Server" или "Modality").  <br/> |
   

