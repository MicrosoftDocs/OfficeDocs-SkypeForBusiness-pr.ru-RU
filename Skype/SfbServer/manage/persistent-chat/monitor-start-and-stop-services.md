---
title: Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Сводка: сведения о запуске, остановке и мониторинге служб сохраняемого чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418693"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015
 
**Сводка:** Инструкции по запуску, остановке и мониторингу служб сохраняемого чата в Skype для бизнеса Server 2015.
  
Службы постоянной видеосвязи и проверки соответствия требованиям в чате входят в топологию сервера Skype для бизнеса и поэтому могут быть отслеживаемы, остановлены и запущены с помощью следующих командлетов:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Возвращает подробные сведения о компонентах Skype для бизнеса Server 2015, которые выполняются в качестве служб Windows.  <br/> |
|start-CsWindowsService  <br/> |Запуск службы.  <br/> |
|stop-CsWindowsService  <br/> |Остановка службы.  <br/> |
   
> [!NOTE]
> Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Эта функция доступна в Teams. Дополнительные сведения можно найти в разделе [Начало работы с обновлением Microsoft Teams](/microsoftteams/upgrade-start-here). Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить работу с Skype для бизнеса Server 2015. 

Подробные сведения об использовании командлетов см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

