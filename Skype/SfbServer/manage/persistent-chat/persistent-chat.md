---
title: Управление сервером сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Сводка: Узнайте, как управлять сервера сохраняемого чата в Скайп для Business Server 2015.'
ms.openlocfilehash: f6bd3f9e1364f4dd5b347e65a0a5799e66a97b33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899111"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Управление сервером сохраняемого чата в Skype для бизнеса Server 2015
 
**Сводка:** Сведения об управлении сервера сохраняемого чата в Скайп для Business Server 2015.
  
При настройке серверов сохраняемого чата для вашей организации, укажите начальной настройки во время развертывания. Тем не менее возможны ситуации, когда нужно изменить, как реализовать поддержку сервера сохраняемого чата. Для примера необходимо настроить поддержку сервера сохраняемого чата и элементов управления для определенных групп или группе в организации. В этом разделе представлены сведения и процедуры, которые помогут вам настроить развертывание сервера сохраняемого чата. Для получения дополнительных сведений о возможностях и функциях, которые можно настроить для сервера сохраняемого чата видеть [Планирование сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Для получения дополнительных сведений о развертывании сервера сохраняемого чата видеть [Развертывание сервера сохраняемого чата в Скайп для Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019. Те же функциональные возможности доступны в группах. Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams). Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015. 
  
Серверов сохраняемого чата можно управлять с помощью панели управления или с помощью командлетов Windows PowerShell. 
  
Использование панели управления:
  
1. Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.
    
2. Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.
    
3. В левой панели навигации щелкните **Сохраняемый чат**.
    
В следующей таблице представлены командлеты Windows PowerShell, помогающих управлять сервера сохраняемого чата. Дополнительные сведения о синтаксисе, включая все доступные параметры, см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Создание новой категории  <br/> |
|Set-CsPersistentChatCategory  <br/> |Настройка параметров для существующей категории  <br/> |
|Get-CsPersistentChatCategory  <br/> |Извлечение информации о категориях  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Удаление категории  <br/> |
|New-CsPersistentChatRoom  <br/> |Создание новой комнаты чата  <br/> |
|Set-CsPersistentChatRoom  <br/> |Настройка параметров для существующей комнаты; назначение пользователей и групп пользователей для комнаты  <br/> |
|Get-CsPersistentChatRoom  <br/> |Извлекает сведения о комнат  <br/> |
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
   

