---
title: Таблица PayloadDescription
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: Таблица PayloadDescription является вспомогательной. Каждая запись представляет один кодек, используемый в аудио- или видеосеансе.
ms.openlocfilehash: aada0dae9c371700756be16133ca9cccdcbf82ae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850622"
---
# <a name="payloaddescription-table"></a>Таблица PayloadDescription
 
Таблица PayloadDescription является вспомогательной. Каждая запись представляет один кодек, используемый в аудио- или видеосеансе.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, обозначающий кодек.  <br/> |
|**PayloadDescription** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Имя кодека.  <br/> |
   

