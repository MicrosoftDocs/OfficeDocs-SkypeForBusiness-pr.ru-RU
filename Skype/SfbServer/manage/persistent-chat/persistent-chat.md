---
title: Управление постоянным сервером чата в Skype для бизнеса Server 2015 г.
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
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Сводка. Сведения о том, как управлять стойким сервером чата в Skype для бизнеса Server 2015 г.'
---

# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Управление постоянным сервером чата в Skype для бизнеса Server 2015 г.
 
**Сводка:** Узнайте, как управлять стойким сервером чата в Skype для бизнеса Server 2015 г.
  
При настройке стойких серверов чата для организации указывается начальная конфигурация во время развертывания. Однако могут возникнуть моменты, когда необходимо изменить реализации поддержки сохраняемой службы чат-сервера. Например, для определенной группы или группы в организации может потребоваться настроить службу поддержки и управления сервером сохраняемого чата по-разному. В этом разделе содержится информация и процедуры, которые помогут настроить развертывание сервера сохраняемой системы чата. Дополнительные сведения о функциях и функциях, которые можно настроить для сервера сохраняемого чата, см. в материале [Plan for Persistent Chat Server в Skype для бизнеса Server 2015 г](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Дополнительные сведения о развертывании сервера постоянных чатов см. в материале [Deploy Persistent Chat Server в Skype для бизнеса Server 2015 г](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Постоянный чат доступен в Skype для бизнеса Server 2015 г., но больше не поддерживается Skype для бизнеса Server 2019 г. Такая же функциональность доступна в Teams. Дополнительные сведения см. в [ссылке Начало работы с Microsoft Teams обновления](/microsoftteams/upgrade-start-here). Если вам нужно использовать постоянный чат, вы можете либо перенести пользователей, требующих Teams, либо продолжить использование Skype для бизнеса Server 2015 г. 
  
Вы можете управлять стойким сервером чата с помощью панели управления или с помощью Windows PowerShell- 
  
Чтобы использовать панель управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.
    
2. В меню **Пуск** выберите панель управления Skype для бизнеса Server или откройте окно браузера, а затем введите URL-адрес администратора.
    
3. В левой панели навигации нажмите кнопку **Persistent Chat**.
    
В следующей таблице обобщены Windows PowerShell, доступные для управления стойким сервером чата. Подробные сведения о синтаксисе, включая все доступные параметры, см. в Skype для бизнеса Server [2015 года](../management-shell.md).
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Создает новую категорию  <br/> |
|Set-CsPersistentChatCategory  <br/> |Настройка параметров для существующей категории  <br/> |
|Get-CsPersistentChatCategory  <br/> |Извлечение сведений о категориях  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Удаляет категорию  <br/> |
|New-CsPersistentChatRoom  <br/> |Создание новой комнаты чата  <br/> |
|Set-CsPersistentChatRoom  <br/> |Настройка параметров для существующего помещения; назначение пользователей и групп пользователей в комнату  <br/> |
|Get-CsPersistentChatRoom  <br/> |Извлечение сведений о комнатах  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Очищает комнату или сообщения из комнаты  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Удаление комнаты  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Удаление сообщений из комнаты  <br/> |
|New-CsPersistentChatAddin  <br/> |Создание новой надстройки  <br/> |
|Set-CsPersistentChatAddin  <br/> |Настройка параметров существующей надстройки  <br/> |
|Get-CsPersistentChatAddin  <br/> |Извлекает сведения о надстройки  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Удаление надстройки  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Изменяет существующую коллекцию параметров конфигурации соответствия требованиям  <br/> |
|Export-CsPersistentChatData  <br/> |Экспорт данных из базы данных сохраняемой системы чата  <br/> |
|Import-CsPersistentChatData  <br/> |Импорт данных, экспортируемых из предыдущей версии Lync Server  <br/> |
   

