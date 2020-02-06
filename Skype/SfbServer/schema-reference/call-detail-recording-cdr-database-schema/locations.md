---
title: Таблица "расположения" в Skype для бизнеса Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815117"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Таблица "расположения" в Skype для бизнеса Server 2015
 
Каждая запись представляет одну ссылку на расположение в экстренном звонке, например, в вызове E9-1-1.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**сессионидтиме** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. Используется в сочетании с **сессионидсек** для уникальной идентификации сеанса. Дополнительные сведения приведены [в таблице диалоговые окна в Skype для бизнеса Server 2015](dialogs.md) . <br/> |
|**сессионидсек** <br/> |целое  <br/> |Основной, внешний  <br/> |ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с **сессионидтиме** для уникальной идентификации сеанса. Дополнительные сведения приведены [в таблице диалоговые окна в Skype для бизнеса Server 2015](dialogs.md) . <br/> |
|**Расположение** <br/> |nvarchar (max)  <br/> ||Место вызова экстренной помощи.  <br/> |
   

