---
title: Настройка надстройок для постоянных чатов в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: Сводка. Сведения о настройке надстройок для комнат чатов сохраняемого чата chat Server в Skype для бизнеса Server 2015 г.
ms.openlocfilehash: 183ac4cbbdcdddfea65b3a6acab44ef4c81fe662
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745955"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Настройка надстройок для постоянных чатов в Skype для бизнеса Server 2015 г.
 
**Сводка:** Узнайте, как настроить надстройки для постоянных чатов chat Server в Skype для бизнеса Server 2015 г.
  
Надстройки используются для расширения работы в комнате, связывая URL-адреса с комнатами чатов. Эти URL-адреса отображаются в области разностойности клиентской беседы. Типичная надстройка может включать URL-адрес приложения Silverlight, который перехватывает при размещении тикера акций в комнате чата и отображает историю запасов в области простота. К другим примерам относится внедрение URL-адреса OneNote 2013 в комнату чата в виде надстройки для предоставления общего контекста, например темы дня.
  
 Прежде чем пользователи смогут увидеть надстройку в клиенте, необходимо добавить надстройку в список зарегистрированных надстройок, а администраторам или создателям чата необходимо связать комнаты с надстройкой.
  
> [!NOTE]
> Постоянный чат доступен в Skype для бизнеса Server 2015 г., но больше не поддерживается Skype для бизнеса Server 2019 г. Такая же функциональность доступна в Teams. Дополнительные сведения см. в ссылке Начало работы [с обновлением Microsoft Teams обновления.](/microsoftteams/upgrade-start-here) Если вам нужно использовать постоянный чат, вы можете либо перенести пользователей, требующих Teams, либо продолжить использование Skype для бизнеса Server 2015 г. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Настройка надстройок для чатов с помощью панели управления

Настройка надстройок для чатов с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.
    
2. В меню **Пуск** выберите панель управления Skype для бизнеса Server или откройте окно браузера, а затем введите URL-адрес администратора.
    
3. В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Надстройка**.
    
    Для нескольких развертываний пула сохраняемого сервера чата выберите соответствующий пул из выпадаемого списка.
    
4. На странице **Надстройка** нажмите кнопку **Создать**.
    
5. В **Выберите службу** выберите службу, соответствующую пулу серверов сохраняемого чата, где необходимо создать надстройки. Надстройки нельзя переместить из одного пула в другой и нельзя сделать их общими для разных пулов.
    
6. В окне **Создание надстройки** выполните следующие действия.
    
   - В поле **Имя** введите имя новой надстройки.
    
   - В поле **URL-адрес** укажите URL-адрес, который необходимо связать с надстройкой. URL-адреса ограничены протоколами http и https.
    
7. Щелкните **Исполнить**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Настройка надстройок с помощью Windows PowerShell

Надстройки для чатов можно настроить с помощью следующих Windows PowerShell. Подробные сведения о синтаксис, включая все доступные параметры, см. в Skype для бизнеса Server [2015 года.](../management-shell.md)
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Создание новой надстройки  <br/> |
|Set-CsPersistentChatAddin  <br/> |Настройка параметров существующей надстройки  <br/> |
|Get-CsPersistentChatAddin  <br/> |Извлечение сведений о надстройки  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Удаление надстройки  <br/> |
   
### <a name="create-a-new-add-in"></a>Создание новой надстройки

Новую надстройку можно создать с помощью **комлета New-CsPersistentChatAddin.**
  
Например, следующая команда создает новую надстройку (с именем ITPersistentChatAddin) для `atl-cs-001.contoso.com` пула. Параметр URL-адреса и значение параметра указывают расположение `http://atl-cs-001.contoso.com/itchat` веб-страницы надстройки:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Настройка параметров существующей надстройки

Параметры существующей надстройки можно настроить с помощью cmdlet **Set-CsPersistentChatAddIn.** Например, следующая команда изменяет URL-адрес, присвоенный надстройке Persistent Chat в ITPersistentChatAddin. В этом случае URL-адрес изменен на `http://atl-cs-001.contoso.com/itchat2` :
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Извлечение сведений о надстройки

Сведения о надстройке можно получить с помощью **cmdlet Get-CsPersistentChatAddin.** Например, следующая команда возвращает сведения обо всех надстройках Persistent Chat, настроенных для использования в организации:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Удаление надстройки

Надстройку можно удалить с помощью **cmdlet Remove-CsPersistentChatAddIn.** Например, следующая команда удаляет надстройку Persistent Chat в ITChatAddin, найденную в `atl-cs-001.contoso.com` пуле:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


