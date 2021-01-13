---
title: Мониторинг, запуск и остановка служб сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: Сводка. Узнайте, как запускать, останавливать и отслеживать службы сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814139"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Мониторинг, запуск и остановка служб сохраняемой беседы в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как запускать, останавливать и отслеживать службы сохраняемой беседы в Skype для бизнеса Server 2015.
  
Службы сохраняемого чата и службы соответствия сохраняемого чата являются частью топологии Skype для бизнеса Server и поэтому могут отслеживаться, остановлены и запущены с помощью следующих cmdlets:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Возвращает подробные сведения о компонентах Skype для бизнеса Server 2015, которые работают как службы Windows.  <br/> |
|start-CsWindowsService  <br/> |Запускает службу.  <br/> |
|stop-CsWindowsService  <br/> |Останавливает службу.  <br/> |
   
> [!NOTE]
> Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams. Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015. 

Подробные сведения об использовании этих cmdlets см. в описании [skype для бизнеса Server 2015 Management Shell.](../management-shell.md)
  

