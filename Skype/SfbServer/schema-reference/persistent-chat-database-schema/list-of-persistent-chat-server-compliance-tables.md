---
title: Список таблиц соответствия для сервера сохраняемого чата в Skype для бизнеса Server
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
description: Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813059"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Список таблиц соответствия для сервера сохраняемого чата в Skype для бизнеса Server
 
Схема базы данных соответствия сохраняемого чата состоит из следующих таблиц.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соблюдения требований для сервера сохраняемого чата

|**Table**|**Описание**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Содержит события соответствия, которые еще не были обработаны настроенным адаптером.  <br/> Эта таблица содержит события, связанные с сохраняемого чата, такие как сообщения чата и загрузка файлов. (События, связанные с участниками, отслеживаются в таблице tblComplianceParticipant.)  <br/> (Серверы, которые обработали события, содержащиеся в этой таблице, приводятся в таблице tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Содержит серверы, обработавшие события соответствия. Эта таблица тесно связана с таблицей tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Содержит сведения о текущих участниках по службам чата и серверам. Она поддерживается на основе событий join и part compliance, полученных от службы сохраняемой беседы.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Содержит сведения о состоянии соответствия во всем пуле.  <br/> |
   

