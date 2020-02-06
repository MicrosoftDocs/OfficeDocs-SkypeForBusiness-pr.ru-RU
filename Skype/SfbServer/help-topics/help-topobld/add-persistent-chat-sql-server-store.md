---
title: Добавление хранилища SQL Server для сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Вы можете настроить хранилища SQL Server, в которых будут предоставляться базы данных для сервера сохраняемого чата или для пула серверов сохраняемого чата.
ms.openlocfilehash: 36939e6192b8d26e5fa84c3c2fe5ef4efe45b577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820661"
---
# <a name="add-persistent-chat-sql-server-store"></a>Добавление хранилища SQL Server для сохраняемого чата
 
Вы можете настроить хранилища SQL Server, в которых будут предоставляться базы данных для сервера сохраняемого чата или для пула серверов сохраняемого чата.
  
 **Хранилище SQL Server**: выберите существующий SQL Server и, при необходимости, экземпляр сохраняемого чата.
  
Нажмите кнопку **создать** , чтобы определить новый SQL Server и, при необходимости, новый экземпляр для сохраняемых данных чата.
  
Установите флажок **включить зеркальное отображение хранилища SQL Server** , чтобы настроить базу данных SQL Server и дополнительный экземпляр, который предоставит зеркальную базу данных для сохраняемых данных чата.
  
Выберите из списка **зеркальный набор в SQL Server сохраните** сервер SQL Server и дополнительный экземпляр, чтобы он действовал в качестве зеркального сервера SQL Server для СОХРАНЯЕМого SQL-сервера чата.
  
Нажмите кнопку **создать** , чтобы определить новый SQL Server и создать новый экземпляр для сохраняемого зеркального отображения SQL Server.
  
В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа. Сервер-свидетель не может зеркально отражать данные для серверов чатов, но гарантирует, что только один SQL Server в зеркальной конфигурации является активным сервером SQL Server в любой момент.
  
Нажмите кнопку " **создать** ", чтобы определить новый свидетель SQL Server, который является экземпляром для следящего сервера зеркального отображения SQL Server для сохраняемого чата.
  
Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.
  
После того как вы закончите ввод параметров для конфигурации хранилища SQL Server в этом пуле и продолжите работу с определением пула серверов для сохраняемого чата, нажмите кнопку **Далее** .
  
Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.
  
Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.
  
## <a name="see-also"></a>См. также

[Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основы топологии для Skype для бизнеса Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
