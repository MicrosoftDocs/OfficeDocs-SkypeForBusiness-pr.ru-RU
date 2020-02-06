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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814687"
---
# <a name="tbladupdates"></a>tblADUpdates
 
Тбладупдатес содержит изменения доменных служб Active Directory, которые еще не были обработаны с помощью последующих шагов синхронизации Active Directory.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|прингуид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID участника измененного объекта.  <br/> |
|принадпас  <br/> |nvarchar (384), NOT NULL  <br/> |Отличительное имя объекта.  <br/> |
|принаттрибутесчанжед  <br/> |bit, NOT NULL  <br/> |Значение true, если по крайней мере один из атрибутов объекта изменился.  <br/> |
|принмемберсчанжед  <br/> |bit, NOT NULL  <br/> |Значение true, если изменилось членство.  <br/> |
|принаффилиатионсчанжед  <br/> |bit, NOT NULL  <br/> |Не используется.  <br/> |
|принделетед  <br/> |bit, NOT NULL  <br/> |Значение true, если объект был удален.  <br/> |
|ластупдатед  <br/> |DateTime, NOT NULL  <br/> |Метка времени вставки строки.  <br/> |
   

