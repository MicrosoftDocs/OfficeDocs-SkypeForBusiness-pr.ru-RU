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
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных соответствия требованиям к сохраненным Чатам состоит из следующих таблиц.
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295659"
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
   

