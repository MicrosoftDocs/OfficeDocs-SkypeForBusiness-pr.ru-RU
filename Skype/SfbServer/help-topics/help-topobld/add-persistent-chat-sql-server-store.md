---
title: Добавление хранилища SQL Server для сохраняемого чата
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Вы настраиваете SQL Server, которые будут предоставлять базы данных для сохраняемой системы чат-сервера или пула стойких чат-серверов.
ms.openlocfilehash: 27063ed9a2858714e6fd26db9fad98db1c47f95e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763947"
---
# <a name="add-persistent-chat-sql-server-store"></a>Добавление хранилища SQL Server для сохраняемого чата
 
Вы настраиваете SQL Server, которые будут предоставлять базы данных для сохраняемой системы чат-сервера или пула стойких чат-серверов.
  
 **SQL Server:** Выберите существующий SQL Server и необязательно экземпляр для сохраняемой беседы.
  
Щелкните **Новое,** чтобы определить новый SQL Server и необязательный новый экземпляр для данных сохраняемой беседы.
  
Выберите **контрольный SQL Server** для настройки SQL Server базы данных и дополнительного экземпляра, который предоставит зеркальную базу данных для данных сохраняемой беседы.
  
Выберите из списка **зеркальное SQL Server** хранить экземпляр SQL Server и необязательный экземпляр для SQL Server зеркала для SQL Server.
  
Щелкните **Новое,** чтобы определить новый SQL Server и необязательный новый экземпляр для сохраняемой SQL Server зеркального.
  
Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа. Сервер свидетеля не зеркально или не передает данные для серверов сохраняемой беседы, но гарантирует, что только SQL Server в зеркальной конфигурации является активным SQL Server в любое время.
  
Щелкните **Кнопку** New, чтобы определить новый SQL Server дополнительный экземпляр для сохраняемой SQL Server зеркального свидетеля.
  
Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.
  
Нажмите **кнопку** Далее после завершения ввода параметров конфигурации SQL Server этого пула и приступить к определению пула сохраняемой системы чата.
  
Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.
  
Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.
  
## <a name="see-also"></a>См. также

[Планирование на стойкий сервер чата в Skype для бизнеса Server 2015 г.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление постоянного сервера чата в топологию Skype для бизнеса Server 2015 г.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Требования к оборудованию и программному обеспечению для постоянного сервера чата в Skype для бизнеса Server 2015 г.](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Требования к серверу для Skype для бизнеса Server 2015 г.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основы топологии для Skype для бизнеса Server 2015 г.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Настройка высокой доступности и аварийного восстановления для сохраняемой сервера чата в Skype для бизнеса Server 2015 г.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
