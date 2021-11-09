---
title: Список таблиц сохраняемого соответствия требованиям chat Server в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных данных сохраняемого чата состоит из следующих таблиц.
ms.openlocfilehash: cc4a40d5c2fa80559ddb2ba2cb713c078b4af357
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833253"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Список таблиц сохраняемого соответствия требованиям chat Server в Skype для бизнеса Server
 
Схема базы данных данных сохраняемого чата состоит из следующих таблиц.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соблюдения требований для сервера сохраняемого чата

|**Table**|**Описание**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Содержит события соответствия, которые еще не были обработаны настроенным адаптером.  <br/> В эту таблицу включены события, связанные с постоянным чатом, такие как сообщения чата и скачивание файлов. (События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)  <br/> (Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Содержит серверы, обработавшие события соответствия. Эта таблица тесно связана с таблицей tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Содержит сведения о текущих участниках по службам чата и серверам. Он поддерживается на основе событий соответствия требованиям, полученным от службы "Стойкий чат".  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Содержит сведения о состоянии соответствия во всем пуле.  <br/> |
   

