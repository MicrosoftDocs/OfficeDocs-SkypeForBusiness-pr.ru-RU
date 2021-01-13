---
title: Windows PowerShell и средства управления Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 'В Skype для бизнеса Server средства управления реализуются с помощью Windows PowerShell. Windows PowerShell включает среду командной строки, команды для определенных продуктов и полный язык сценариев. Средства Skype для бизнеса Server, реализованные с помощью Windows PowerShell включают следующие:'
ms.openlocfilehash: 740a5e3d7998523970e1b0adc1e72aa85d0b09c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832159"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell и средства управления Skype для бизнеса Server
 
В Skype для бизнеса Server средства управления реализуются с помощью Windows PowerShell. Windows PowerShell включает среду командной строки, команды для определенных продуктов и полный язык сценариев. Средства Skype для бизнеса Server, реализованные с помощью Windows PowerShell включают следующие: 
  
- **Построитель топологий.** Построитель топологий используется для создания, настройки и публикации запланированной топологии, а также проверяет топологию перед началом установки сервера. При установке Skype для бизнеса Server на отдельных серверах серверы считыют опубликованную топологию в рамках процесса установки, а программа установки развертывает сервер, как указано в топологии. После установки сведения о конфигурации автоматически реплицируются на все серверы. Компоненты можно добавлять в развертывание только с помощью построитель топологий.
    
- **Skype для бизнеса Server Management Shell.** Для полного управления развертыванием с помощью командной строки Skype для бизнеса Server.
    
- **Панель управления Skype для бизнеса Server.** Для управления наиболее распространенными задачами в развертывании можно использовать пользовательский интерфейс панели управления Skype для бизнеса Server.
    
Эти средства используют Windows PowerShell для управления развертыванием, включая почти 550 специальных продуктов. The security cmdlets included in Skype for Business Server are primarily used to manage authentication, and user rights and permissions. Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов). Кроме того, ряд cmdlets позволяют использовать новый Role-Based управления доступом (RBAC) для делегирования административного управления Skype для бизнеса Server. For details about the Skype for Business Server cmdlets, see [Skype for Business Server Management Shell.](../../manage/management-shell.md)
  
Функции безопасности скриптов для Windows PowerShell специально разработаны для предотвращения некоторых проблем безопасности, связанных с скриптами, в старых технологиях, включая Microsoft Visual Basic Scripting Edition (VBScript). Функции Windows PowerShell безопасности предназначены для создания среды, в которой пользователи не могут легко или непреднастраиво запускать сценарии. По умолчанию Windows PowerShell безопасности включены. Вы можете изменить состояние этих функций в зависимости от потребностей сценариев и различных целей безопасности. Это не говорит о том, что оболочка не позволяет пользователям запускать сценарии. Вместо этого оболочка по умолчанию затрудняет для пользователей запуск сценариев, не понимая, что они делают это. Подробные сведения [см. в Windows PowerShell Script Security.](https://go.microsoft.com/fwlink/p/?LinkId=213145)
  

