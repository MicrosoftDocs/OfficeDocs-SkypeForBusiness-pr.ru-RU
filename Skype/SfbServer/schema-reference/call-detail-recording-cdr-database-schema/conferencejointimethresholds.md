---
title: Таблица ConferenceJoinTimeThresholds в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:'
ms.openlocfilehash: 0ecdb432c5e386944e762016236e4c42fe6d9dae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386317"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Таблица ConferenceJoinTimeThresholds в Skype для бизнеса Server 2015 г.
 
Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:
  
- менее 2 секунд;
    
- от 2 до 5 секунд;
    
- от 5 до 10 секунд;
    
- более 10 секунд.
    
Таблица ConferenceJoinTimeThresholds содержит значения классификации для 2 секунд, 5 секунд и 10 секунд.
  
Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Верхняя граница для классификации. Допустимые значения: <br/>  2 <br/>  5 <br/>  10  <br/> |
   

