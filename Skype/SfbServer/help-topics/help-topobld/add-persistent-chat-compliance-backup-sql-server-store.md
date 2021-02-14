---
title: Добавление резервного хранилища SQL Server соответствия сохраняемого чата
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Необходимо настроить резервные хранилища соответствия SQL Server, которые будут предоставлять резервные базы данных для серверов сохраняемой беседы или SQL Server сохраняемой беседы.
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818719"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Добавление резервного хранилища SQL Server соответствия сохраняемого чата
 
Необходимо настроить резервные хранилища соответствия SQL Server, которые будут предоставлять резервные базы данных для серверов сохраняемой беседы или SQL Server сохраняемой беседы.
  
 **SQL Server хранения:** выберите существующий SQL Server и при желании экземпляр для сохраняемой беседы.
  
Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для данных соответствия для резервного копирования сохраняемой беседы.
  
Select the **Enable SQL Server store mirroring** checkbox to configure a SQL Server database and optional instance that will provide a mirrored database for the Persistent Chat backup compliance data.
  
Выберите в списке зеркальное **SQL Server** сохранить SQL Server и необязательный экземпляр, чтобы выступать в качестве зеркала SQL Server для резервного копирования сохраняемой беседы SQL Server.
  
Щелкните **"Новое",** чтобы определить новый SQL Server и при желании новый экземпляр для зеркального SQL Server сохраняемой беседы.
  
Выберите в списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** сервер SQL Server, который будет выступать в качестве следящего сервера в сценариях отработки отказа. Сервер-свидетель не зеркально и не служит для хранения данных для серверов сохраняемой беседы, но гарантирует, что только SQL Server в зеркальной конфигурации является активным SQL Server в любое время.
  
Нажмите **кнопку** "Новое", чтобы определить новый SQL Server-свидетель, при желании экземпляр для резервного SQL Server сохраняемой беседы.
  
Нажмите кнопку **Назад**, чтобы вернуться в предыдущее диалоговое окно определения пула.
  
Нажмите **кнопку** "Далее", когда закончите вводить параметры для конфигурации резервного SQL Server пула пула и переходить к определению пула серверов сохраняемой беседы.
  
Нажмите кнопку **Отмена**, чтобы отменить все изменения и завершить работу с мастером **Определение нового пула сохраняемого чата**.
  
Нажмите кнопку **Справка**, чтобы открыть контекстно-зависимую справку, аналогичную данной странице.
  
## <a name="see-also"></a>См. также

[Планирование сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Требования к серверу для Skype для бизнеса Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Требования к оборудованию и программному обеспечению для сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Настройка службы соответствия для сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Настройка высокой доступности и аварийного восстановления для сервера сохраняемой беседы в Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
