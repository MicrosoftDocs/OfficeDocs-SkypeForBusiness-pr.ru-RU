---
title: Список таблиц соответствия требованиям сервера для работы с сохраняемым сервером чата в Skype для бизнеса Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814767"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Список таблиц соответствия требованиям сервера для работы с сохраняемым сервером чата в Skype для бизнеса Server
 
Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соответствия требованиям сервера для работы с постоянной версией чата

|**Таблица**|**Описание**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Содержит события соответствия требованиям, которые еще не были обработаны настроенным адаптером.  <br/> В этой таблице содержатся сохраняемые события, связанные с чат, такие как сообщения чата и загружаемые файлы. (События участников отслеживаются таблицей ТблкомплианцепартиЦипант.)  <br/> (Серверы, обработавшие события в этой таблице, перечислены в таблице Тблкомплианцефанаут).  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Содержат серверы, которые обрабатывали событие соответствия требованиям. Эта таблица тесно связана с таблицей Тблкомплианцедата.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Включает в себя текущих участников для каждой службы чата и для каждого сервера. Она поддерживается на основе событий присоединения и частей соответствия, полученных от службы сохраняемого чата.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Сведения о состоянии соответствия требованиям всего пула.  <br/> |
   

