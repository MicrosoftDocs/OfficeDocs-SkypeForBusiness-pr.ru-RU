---
title: Таблица DeRegisterType в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных пользователя отмены регистрации типов, например «инициируется клиентом», «срок действия регистрации истек» или «клиент перестал отвечать».
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213195"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Таблица DeRegisterType в Скайп для Business Server 2015
 
Таблица DeRegisterType — это статическая таблица, в которой хранится список возможных пользователя отмены регистрации типов, например «инициируется клиентом», «срок действия регистрации истек» или «клиент перестал отвечать».
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Допускаются следующие значения: <br/>  0 — Неизвестный <br/>  1 — Клиент инициировал отмену регистрации <br/>  2 — срок действия регистрации истек <br/>  3 — аварийное завершение клиента <br/>  4 — атрибуты пользователя изменены <br/>  5 — предпочтительный регистратор изменен <br/>  6 — Устаревший клиент в режиме сохранения <br/> |
   

