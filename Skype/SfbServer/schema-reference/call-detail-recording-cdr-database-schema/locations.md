---
title: Таблица расположения в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например на вызов E9-1-1.
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213003"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Таблица расположения в Скайп для Business Server 2015
 
Каждая запись представляет одну ссылку на расположение в экстренном звонке, например на вызов E9-1-1.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. Используется совместно с **SessionIdSeq** для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**SessionIdSeq** <br/> |целое  <br/> |Основной, внешний  <br/> |Номер идентификатора для идентификации сеанса. Используется в сочетании с **SessionIdTime** для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**Расположение** <br/> |nvarchar(max)  <br/> ||Расположение экстренного звонка.  <br/> |
   

