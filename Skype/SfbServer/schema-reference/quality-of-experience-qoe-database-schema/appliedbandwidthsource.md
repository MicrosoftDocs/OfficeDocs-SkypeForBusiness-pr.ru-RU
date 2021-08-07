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
ms.openlocfilehash: fcb0323b1e6775b20a8ca4d269bcc8eecdc055b73d5a93a490e97f8a1af44b11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305351"
---
# <a name="appliedbandwidthsource-table"></a>Таблица AppliedBandwidthSource
 
Таблица AppliedBandwidthSource является вспомогательной. Каждая запись представляет один источник.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий источник.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Источник применяемого ограничения пропускной способности. В нем описывается, откуда приходит ограничение пропускной способности (например, "Сервер политики", "TURN Server" или "Modality").  <br/> |
   

