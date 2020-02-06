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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Сводка: сведения о запуске, остановке и мониторинге служб сохраняемого чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 846d7376e1a3e9bd06ae74c20ee0812c8c78bbeb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817478"
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
> Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here). Если вам нужно использовать сохраняемый чат, то вы можете либо перенести пользователей, которым нужна эта функция, в Teams, либо продолжать использовать Skype для бизнеса Server 2015. 

Подробные сведения об использовании командлетов см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

