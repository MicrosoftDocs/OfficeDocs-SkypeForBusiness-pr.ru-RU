---
title: Управление сервером сохраняемой беседы в Skype для бизнеса Server 2015
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
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: Сводка. Сведения об управлении сервером сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832889"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Управление сервером сохраняемой беседы в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как управлять сервером сохраняемой беседы в Skype для бизнеса Server 2015.
  
При настройке сервера сохраняемой беседы для организации указывается начальная конфигурация во время развертывания. Однако иногда может потребоваться изменить реализации поддержки сервера сохраняемой беседы. Например, может потребоваться настроить поддержку сервера сохраняемого чата и другие элементы управления для определенной команды или группы в организации. В этом разделе приводится информация и процедуры, которые помогут настроить развертывание сервера сохраняемой беседы. Дополнительные сведения о функциях и функциях, которые можно настроить для сервера сохраняемого чата, см. в подстроке "Планирование сервера сохраняемого чата" в [Skype для бизнеса Server 2015.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) Дополнительные сведения о развертывании сервера сохраняемой беседы см. в сведениях о развертывании сервера сохраняемой беседы [в Skype для бизнеса Server 2015.](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md) 

> [!NOTE]
> Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams. Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015. 
  
Управлять сервером сохраняемой беседы можно с помощью панели управления или с помощью Windows PowerShell других. 
  
Чтобы использовать панель управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.
    
2. В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.
    
3. В левой панели навигации щелкните **сохраняемого чата**.
    
В следующей таблице приводится Windows PowerShell, которые помогут вам управлять сервером сохраняемой беседы. Подробные сведения о синтаксисе, включая все доступные параметры, см. в руководстве [по skype для бизнеса Server 2015 Management Shell.](../management-shell.md)
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Создает новую категорию  <br/> |
|Set-CsPersistentChatCategory  <br/> |Настройка параметров для существующей категории  <br/> |
|Get-CsPersistentChatCategory  <br/> |Извлекает сведения о категориях  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Удаляет категорию  <br/> |
|New-CsPersistentChatRoom  <br/> |Создает новую комнату чата  <br/> |
|Set-CsPersistentChatRoom  <br/> |Настраивает параметры для существующей комнаты; назначение пользователей и групп пользователей комнате  <br/> |
|Get-CsPersistentChatRoom  <br/> |Извлекает сведения о комнатах  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Очищает комнату или сообщения из комнаты  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Удаляет комнату  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Удаляет сообщения из комнаты  <br/> |
|New-CsPersistentChatAddin  <br/> |Создание новой надстройки  <br/> |
|Set-CsPersistentChatAddin  <br/> |Настройка параметров для существующей надстройки  <br/> |
|Get-CsPersistentChatAddin  <br/> |Извлекает сведения о надстройки  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Удаление надстройки  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Изменяет существующую коллекцию параметров конфигурации соответствия требованиям  <br/> |
|Export-CsPersistentChatData  <br/> |Экспорт данных из базы данных сохраняемой беседы  <br/> |
|Import-CsPersistentChatData  <br/> |Импортирует данные, экспортируемые из предыдущей версии Lync Server  <br/> |
   

