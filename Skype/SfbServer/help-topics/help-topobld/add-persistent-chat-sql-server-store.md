---
title: Добавление хранилища SQL Server для сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Настраиваются хранилища SQL Server, которые будут предоставлять базы данных для сервера сохраняемой беседы или пула серверов сохраняемой беседы.
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818659"
---
# <a name="add-persistent-chat-sql-server-store"></a>Добавление хранилища SQL Server для сохраняемого чата
 
Настраиваются хранилища SQL Server, которые будут предоставлять базы данных для сервера сохраняемой беседы или пула серверов сохраняемой беседы.
  
 **SQL Server хранения:** выберите существующий SQL Server и при желании экземпляр для сохраняемой беседы.
  
Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для данных сохраняемой беседы.
  
Чтобы настроить базу данных SQL Server и необязательный экземпляр, который будет предоставлять зеркальную базу данных для **данных** сохраняемой беседы, выберите SQL Server включить зеркальное зеркальное хранение данных.
  
Выберите в списке зеркальное **SQL Server** сохранить SQL Server и необязательный экземпляр для SQL Server зеркала для сохраняемой беседы SQL Server.
  
Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для зеркального SQL Server сохраняемой беседы.
  
Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа. Сервер-свидетель не зеркально и не служит для хранения данных для серверов сохраняемой беседы, но гарантирует, что только SQL Server в зеркальной конфигурации является активным SQL Server в любое время.
  
Нажмите **кнопку** "Новое", чтобы определить новый SQL Server,при желании экземпляр для свидетеля SQL Server сохраняемой беседы.
  
Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.
  
Нажмите **кнопку** "Далее", когда закончите ввод параметров конфигурации SQL Server этого пула, и перейдите к определению пула сервера сохраняемой беседы.
  
Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.
  
Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.
  
## <a name="see-also"></a>См. также

[Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление сервера сохраняемой беседы в топологию Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Требования к оборудованию и программному обеспечению для сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Требования к серверу для Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основы топологии для Skype для бизнеса Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
