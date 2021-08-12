---
title: Таблица пула
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Во вспомогательной таблице Pool хранятся сведения о различных интерфейсных пулах. Каждая запись в таблице представляет один пул.
ms.openlocfilehash: e9ad0f0661bbd38a2d1175ab38113585c306baf234bc97e98bf40fca949d0cd9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312977"
---
# <a name="pool-table"></a>Таблица пула
 
Во вспомогательной таблице Pool хранятся сведения о различных интерфейсных пулах. Каждая запись в таблице представляет один пул.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий пул.  <br/> |
|**PoolName** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Полное доменное имя пула.  <br/> |
   

