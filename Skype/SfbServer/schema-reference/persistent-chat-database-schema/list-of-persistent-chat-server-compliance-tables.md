---
title: Список таблиц сохраняемого соответствия требованиям chat Server в Skype для бизнеса Server
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
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных данных сохраняемого чата состоит из следующих таблиц.
ms.openlocfilehash: b41d8a3f3c5e42f9e4c29eeb6cb81774b5b177aee18c67dc52bc4c9009f67c8e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303672"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Список таблиц сохраняемого соответствия требованиям chat Server в Skype для бизнеса Server
 
Схема базы данных данных сохраняемого чата состоит из следующих таблиц.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соблюдения требований для сервера сохраняемого чата

|**Table**|**Description**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Содержит события соответствия, которые еще не были обработаны настроенным адаптером.  <br/> В эту таблицу включены события, связанные с постоянным чатом, такие как сообщения чата и скачивание файлов. (События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)  <br/> (Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Содержит серверы, обработавшие события соответствия. Эта таблица тесно связана с таблицей tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Содержит сведения о текущих участниках по службам чата и серверам. Он поддерживается на основе событий соответствия требованиям, полученным от службы "Стойкий чат".  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Содержит сведения о состоянии соответствия во всем пуле.  <br/> |
   

