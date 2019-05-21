---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295561"
---
# <a name="tbladupdates"></a>tblADUpdates
 
Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Прингуид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID участника измененного объекта.  <br/> |
|Принадпас  <br/> |nvarchar (384), NOT NULL  <br/> |Отличительное имя объекта.  <br/> |
|Принаттрибутесчанжед  <br/> |bit, NOT NULL  <br/> |Значение true, если по крайней мере один из атрибутов объекта изменился.  <br/> |
|Принмемберсчанжед  <br/> |bit, NOT NULL  <br/> |Значение true, если изменилось членство.  <br/> |
|Принаффилиатионсчанжед  <br/> |bit, NOT NULL  <br/> |Не используется.  <br/> |
|Принделетед  <br/> |bit, NOT NULL  <br/> |Значение true, если объект был удален.  <br/> |
|Ластупдатед  <br/> |DateTime, NOT NULL  <br/> |Метка времени вставки строки.  <br/> |
   

