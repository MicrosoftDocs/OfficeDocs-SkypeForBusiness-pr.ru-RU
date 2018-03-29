---
title: Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Схема базы данных соответствия Persistent Chat состоит из следующих таблиц.
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server
 
Схема базы данных соответствия Persistent Chat состоит из следующих таблиц.
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Список таблиц соответствия сервера сохраняемого чата

|**В таблице**|**Описание**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |Содержит события соответствия требованиям, которые еще не были обработаны настроенным адаптером.  <br/> В этой таблице содержит события, связанные с сохраняемого чата, такие как мгновенных сообщений и файлов для загрузки. (Участника события отслеживаются в таблице tblComplianceParticipant).  <br/> (Серверы, которые обработали события в следующей таблице перечислены в таблице tblComplianceFanout.)  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |Содержит серверы, обработавшие событие соответствия. В этой таблице тесно связаны с таблицей tblComplianceData.  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |Содержит текущих участников в службы чата и на сервере. Поддерживается на основании присоединения и часть события соответствия, полученные от службы сохраняемого чата.  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |Содержит сведения о состоянии соответствия во всем пуле.  <br/> |
   

