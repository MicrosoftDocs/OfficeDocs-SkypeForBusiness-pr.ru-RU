---
title: Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Сводка: Сведения о настройке надстроек для комнат чата Persistent Chat Server в Скайп для Business Server 2015.'
ms.openlocfilehash: b43340f44b7ce41a1d77768f10a96bff651afc3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885956"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Настройка надстроек для комнат сохраняемого чата в Skype для бизнеса Server 2015
 
**Сводка:** Сведения о настройке надстроек для комнат чата Persistent Chat Server в Скайп для Business Server 2015.
  
Надстройки используются для расширения доступных в комнате возможностей с помощью сопоставления URL-адресов с комнатами чата. Эти URL-адреса отображаются в области расширения беседы чата клиента. Типичная надстройки могут содержать URL-адрес приложение Silverlight, перехватывает при Финансовый символ представляется чата и отображает журнал запасов в области расширяемости. К другим примерам относится внедрение URL-адреса OneNote в комнату чата в качестве надстройки, чтобы включить некоторый общий контекст — "Важные размышления" или "Тема дня".
  
 Чтобы пользователи увидели надстройку в клиенте, необходимо добавить надстройку в список зарегистрированных надстроек, а руководители или создатели комнат чата должны сопоставить комнаты с надстройкой
  
> [!NOTE]
> Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019. Те же функциональные возможности доступны в группах. Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams). Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Конфигурация надстроек для комнат чата с помощью панели управления

Чтобы настроить надстройки для комнат чата с помощью панели управления, выполните следующие действия:
  
1. Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.
    
2. Из меню **Пуск** выберите Скайп для панели управления Business Server или откройте окно браузера и введите URL-адрес администрирования.
    
3. В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Надстройка**.
    
    Для нескольких развертываний пул серверов сохраняемого чата выберите соответствующий пул из раскрывающегося списка.
    
4. На странице **Надстройка** нажмите кнопку **Создать**.
    
5. В списке **поле выбора службы**выберите службы, соответствующий пул серверов сохраняемого чата, где необходимо создать надстройку. Надстройки нельзя перемещать из одного пула в другой или совместно использовать разными пулами.
    
6. В окне **Новая надстройка** выполните следующие действия:
    
   - В поле **Имя** укажите имя новой надстройки.
    
   - В поле **URL-адрес** укажите URL-адрес, который должен быть сопоставлен с данной надстройкой. Эти URL-адреса ограничены протоколами HTTP и HTTPS.
    
7. Нажмите **Исполнить**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Конфигурация надстроек с помощью Windows PowerShell

Надстройки для комнат чата можно настроить с помощью следующих командлетов Windows PowerShell. Дополнительные сведения о синтаксисе, включая все доступные параметры, см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Создание новой надстройки  <br/> |
|Set-CsPersistentChatAddin  <br/> |Настройка параметров для существующей надстройки  <br/> |
|Get-CsPersistentChatAddin  <br/> |Извлечение информации о надстройках  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Удаление надстройки  <br/> |
   
### <a name="create-a-new-add-in"></a>Создание новой надстройки

Создание надстройки можно создать с помощью командлета **New-CsPersistentChatAddin** .
  
Например следующая команда создает новый надстройки (с именем ITPersistentChatAddin) для пула atl-cs-001.contoso.com. Параметр URL-адреса и значение параметра http://atl-cs-001.contoso.com/itchat указать расположение добавить в веб-страницы:
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Настройка параметров для существующей надстройки

Параметры для существующей надстройки можно настроить с помощью командлета **Set-CsPersistentChatAddIn**. Например, следующая команда используется для изменения URL-адреса, назначенного надстройке сохраняемого чата ITPersistentChatAddin. В этом случае URL-адрес изменяется наhttp://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Извлечение информации о надстройках

Получить информацию о надстройках можно с помощью командлета **Get-CsPersistentChatAddin**. Например, следующая команда используется для получения информации обо всех настроенных в организации надстройках сохраняемого чата:
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Удаление надстройки

Add-in можно удалить с помощью командлета **Remove-CsPersistentChatAddIn** . Например, следующая команда удаляет Persistent Chat, надстройка ITChatAddin удастся найти на пул atl-cs-001.contoso.com:
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


