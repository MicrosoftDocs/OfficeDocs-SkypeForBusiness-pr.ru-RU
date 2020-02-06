---
title: Управление сервером сохраняемого чата в Skype для бизнеса Server 2015
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
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Сводка: сведения об управлении сохраняемым сервером чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817325"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Управление сервером сохраняемого чата в Skype для бизнеса Server 2015
 
**Сводка:** Сведения о том, как управлять сохраняемым сервером чата в Skype для бизнеса Server 2015.
  
При настройке постоянного сервера чата для организации вы указываете начальную конфигурацию во время развертывания. Тем не менее иногда требуется изменить способ реализации поддержки сервера сохраняемого чата. Например, может потребоваться настройка поддержки сервера сохраняемого чата и элементов управления для определенной группы или группы в Организации. В этом разделе приводятся сведения и процедуры, которые помогут вам настроить развертывание сервера сохраняемого чата. Подробные сведения о функциях и функциях, которые можно настроить для работы с сохраняемым сервером чата, приведены [в разделе Планирование сохраняемого сервера чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Подробнее о том, как развертывать сохраняемый сервер чата, можно найти [в разделе Развертывание постоянного сервера чата в Skype для бизнеса Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here). Если вам нужно использовать сохраняемый чат, то вы можете либо перенести пользователей, которым нужна эта функция, в Teams, либо продолжать использовать Skype для бизнеса Server 2015. 
  
Вы можете управлять сервером сохраняемого чата с помощью панели управления или командлетов Windows PowerShell. 
  
Использование панели управления:
  
1. Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.
    
2. В меню **Пуск** выберите Панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.
    
3. На панели навигации слева выберите пункт **сохраняемый чат**.
    
В приведенной ниже таблице перечислены командлеты Windows PowerShell, которые помогают управлять сервером сохраняемого чата. Дополнительные сведения о синтаксисе, включая все доступные параметры, см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Создание новой категории  <br/> |
|Set-CsPersistentChatCategory  <br/> |Настройка параметров для существующей категории  <br/> |
|Get-CsPersistentChatCategory  <br/> |Извлечение информации о категориях  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Удаление категории  <br/> |
|New-CsPersistentChatRoom  <br/> |Создание новой комнаты чата  <br/> |
|Set-CsPersistentChatRoom  <br/> |Настройка параметров для существующей комнаты; назначение пользователей и групп пользователей для комнаты  <br/> |
|Get-CsPersistentChatRoom  <br/> |Получение сведений о комнатах  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Очистка комнаты или сообщений комнаты  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Удаление комнаты  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Удаление сообщений из комнаты  <br/> |
|New-CsPersistentChatAddin  <br/> |Создание новой надстройки  <br/> |
|Set-CsPersistentChatAddin  <br/> |Настройка параметров для существующей надстройки  <br/> |
|Get-CsPersistentChatAddin  <br/> |Извлечение информации о надстройках  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Удаление надстройки  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Изменяет существующую коллекцию параметров конфигурации соответствия  <br/> |
|Export-CsPersistentChatData  <br/> |Экспорт данных из базы данных сохраняемых чатов  <br/> |
|Import-CsPersistentChatData  <br/> |Импорт данных, экспорт которых был выполнен в предыдущих версиях Skype для бизнеса Server  <br/> |
   

