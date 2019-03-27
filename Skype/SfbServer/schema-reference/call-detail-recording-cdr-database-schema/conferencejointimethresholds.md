---
title: Таблица conferencejointimethresholds в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Таблица conferencejointimethresholds содержит границ классификации, используемых отчету о Сводка времени присоединения к конференции. В сводном отчете время присоединения к конференции обобщаются количество времени, необходимое для пользователей, для успешного присоединения к конференции; Эти значения времени сообщает и как среднее значение, так и в одной из следующих категорий:'
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895819"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Таблица conferencejointimethresholds в Скайп для Business Server 2015
 
Таблица conferencejointimethresholds содержит границ классификации, используемых отчету о Сводка времени присоединения к конференции. В сводном отчете время присоединения к конференции обобщаются количество времени, необходимое для пользователей, для успешного присоединения к конференции; Эти значения времени сообщает и как среднее значение, так и в одной из следующих категорий:
  
- Менее 2 секунд.
    
- От 2 до 5 секунд.
    
- От 5 до 10 секунд.
    
- Более 10 секунд.
    
Таблица conferencejointimethresholds содержит значения классификации 2 секунд, 5 секунд и 10 секунд.
  
Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |целое  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**ThresholdValue** <br/> |целое  <br/> || Верхняя граница для классификации. Допустимые значения: <br/>  2 <br/>  5 <br/>  10 <br/> |
   

