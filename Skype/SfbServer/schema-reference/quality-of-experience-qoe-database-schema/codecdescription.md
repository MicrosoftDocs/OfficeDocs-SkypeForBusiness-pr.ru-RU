---
title: Таблица CodecDescription
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
ms.openlocfilehash: 9facaa9ddf29024a731f9e199b5cf749d91bc6671c320ded510d693755640f38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309178"
---
# <a name="codecdescription-table"></a>Таблица CodecDescription
 
В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный кодеку.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Уникальное описание кодека, соответствующего CodecDescriptionKey.  <br/> |
   

