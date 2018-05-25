---
title: Добавление хранилища SQL Server для сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Настройка хранилища SQL Server, которые предоставят базы данных для сервера сохраняемого чата или пул серверов сохраняемого чата.
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-sql-server-store"></a>Добавление хранилища SQL Server для сохраняемого чата
 
Настройка хранилища SQL Server, которые предоставят базы данных для сервера сохраняемого чата или пул серверов сохраняемого чата.
  
 **Хранилища SQL Server**: выберите существующий SQL Server и при необходимости экземпляр для сохраняемого чата.
  
Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости и новый экземпляр для данных Persistent Chat.
  
Установите флажок **зеркальное отображение хранилища SQL Server для включения** для настройки базы данных SQL Server и необязательный экземпляр, которые предоставят зеркальную базу данных для данных Persistent Chat.
  
Выберите в списке **зеркалирование хранилища SQL Server** SQL Server и необязательный экземпляр для использования в качестве зеркала SQL Server для сохраняемого сеанса беседы SQL Server.
  
Нажмите кнопку **Создать** , чтобы определить новый SQL Server и при необходимости и новый экземпляр для зеркального отображения сохраняемого сеанса беседы SQL Server.
  
В списке **Использовать свидетель зеркалирования SQL Server для автоматического перехода на другой ресурс** выберите сервер SQL Server, который будет служить следящим сервером в ситуациях отработки отказа. Следящий сервер не не зеркала или ведущего приложения данные для серверов сохраняемых сеансов беседы, но гарантирует, что только один сервер SQL в зеркальной конфигурации active SQL Server в любое время.
  
Нажмите кнопку **Создать** , чтобы определить новый свидетель SQL Server при необходимости и экземпляр для сохраняемого сеанса беседы SQL Server следящий сервер зеркального отображения.
  
Для возврата к предыдущему диалоговому окну определения пула нажмите кнопку **Назад**.
  
После завершения ввода значений для конфигурации хранилища SQL Server в этом пуле, чтобы продолжить определение пула серверов сохраняемого чата нажмите кнопку **Далее** .
  
Для отмены всех изменений нажмите кнопку **Отмена**; при этом работа с мастером **Определение нового пула сохраняемого чата** завершается.
  
Для доступа к контекстно-зависимой справке, аналогичной данной странице, нажмите кнопку **Справка**.
  
## <a name="see-also"></a>См. также

#### 

[Планирование для сервера сохраняемого чата в Скайп Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Аппаратные и программные требования для сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Требования к серверу для Скайп для Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основные сведения о топологии для Скайп для Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Настройка высокой доступности и аварийного восстановления для сервера сохраняемого чата в Скайп для Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

