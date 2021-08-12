---
title: Таблица ConferenceJoinTimeThresholds в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:'
ms.openlocfilehash: 9ce7e8e92921e0cccd8987d6f270a205c5c94de457571ebf959da703cc4bf2ca
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341754"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Таблица ConferenceJoinTimeThresholds в Skype для бизнеса Server 2015 г.
 
Таблица ConferenceJoinTimeThresholds содержит границы классификации, которые используются в сводном отчете о времени присоединения к к конференции. В данном отчете представлены сводные данные о времени, которое требуется для пользователей на успешное присоединение к конференции. Приводятся как средние значения, так и значения в одной из следующих категорий:
  
- менее 2 секунд;
    
- от 2 до 5 секунд;
    
- от 5 до 10 секунд;
    
- более 10 секунд.
    
Таблица ConferenceJoinTimeThresholds содержит значения классификации для 2 секунд, 5 секунд и 10 секунд.
  
Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Верхняя граница для классификации. Допустимые значения: <br/>  2 <br/>  5  <br/>  10  <br/> |
   

