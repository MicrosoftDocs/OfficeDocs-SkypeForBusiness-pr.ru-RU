---
title: 'Мониторинг, запуск и остановка службы сохраняемой беседы в Skype для бизнеса Server 2015 г.'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Сводка. Сведения о запуске, остановке и мониторинге службы сохраняемой беседы в Skype для бизнеса Server 2015 г.'
---

# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Мониторинг, запуск и остановка службы сохраняемой беседы в Skype для бизнеса Server 2015 г.
 
**Сводка:** Узнайте, как запустить, остановить и отслеживать службы сохраняемой беседы в Skype для бизнеса Server 2015 г.
  
Службы сохраняемого чата и службы сохраняемого соответствия требованиям к чату являются частью топологии Skype для бизнеса Server и поэтому могут отслеживаться, остановлены и запущены с помощью следующих cmdlets:
  
|Командлет|Функция|
|:-----|:-----|
|get-CsWindowsService  <br/> |Возвращает подробные сведения о Skype для бизнеса Server компоненты 2015 года, которые работают Windows службами.  <br/> |
|start-CsWindowsService  <br/> |Запускает службу.  <br/> |
|stop-CsWindowsService  <br/> |Останавливает службу.  <br/> |
   
> [!NOTE]
> Постоянный чат доступен в Skype для бизнеса Server 2015 г., но больше не поддерживается Skype для бизнеса Server 2019 г. Такая же функциональность доступна в Teams. Дополнительные сведения см. в [ссылке Начало работы с Microsoft Teams обновления](/microsoftteams/upgrade-start-here). Если вам нужно использовать постоянный чат, вы можете либо перенести пользователей, требующих Teams, либо продолжить использование Skype для бизнеса Server 2015 г. 

Подробные сведения об использовании команды см. в Skype для бизнеса Server [2015 года](../management-shell.md).
  

