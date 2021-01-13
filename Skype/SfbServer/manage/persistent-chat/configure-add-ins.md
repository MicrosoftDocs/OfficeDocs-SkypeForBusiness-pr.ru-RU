---
title: Настройка надстройки для комнат сохраняемого чата в Skype для бизнеса Server 2015
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
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: Сводка. Узнайте, как настроить надстройки для комнат чата сервера сохраняемого чата в Skype для бизнеса Server 2015.
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815085"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Настройка надстройки для комнат сохраняемого чата в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как настроить надстройки для комнат чата сервера сохраняемого чата в Skype для бизнеса Server 2015.
  
Надстройки используются для расширения работы в комнате, связывая URL-адреса с комнатами чата. Эти URL-адреса отображаются в области возможностей клиентской беседы. Типичная надстройка может включать URL-адрес, указывав на приложение Silverlight, которое перехватывает публикацию биржевого деления в комнате чата и отображает историю акций в области возможностей. К другим примерам относится внедрение URL-адреса OneNote 2013 в комнату чата в виде надстройки для предоставления общего контекста, например темы дня.
  
 Прежде чем пользователи смогут увидеть надстройку в клиенте, необходимо добавить ее в список зарегистрированных надстройок, а диспетчерам комнат чата или создателям необходимо связать комнаты с надстройкой.
  
> [!NOTE]
> Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019. Такие же функции доступны в Teams. Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams. Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Настройка надстройки для комнат чата с помощью панели управления

Чтобы настроить надстройки для комнат чата с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.
    
2. В меню **"Пуск"** выберите панель управления Skype для бизнеса Server или откройте окно браузера и введите URL-адрес администратора.
    
3. В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Надстройка**.
    
    Для нескольких развертываний пула серверов сохраняемого чата выберите соответствующий пул в выпадаемом списке.
    
4. На странице **Надстройка** нажмите кнопку **Создать**.
    
5. В **области "Выбор службы"** выберите службу, соответствующую пулу серверов сохраняемого чата, в котором необходимо создать надстройки. Надстройки нельзя переместить из одного пула в другой и нельзя сделать их общими для разных пулов.
    
6. В окне **Создание надстройки** выполните следующие действия.
    
   - В поле **Имя** введите имя новой надстройки.
    
   - В поле **URL-адрес** укажите URL-адрес, который необходимо связать с надстройкой. URL-адреса ограничены протоколами HTTP и HTTPS.
    
7. Щелкните **Исполнить**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Настройка надстройки с помощью Windows PowerShell

Вы можете настроить надстройки для комнат чата с помощью следующих Windows PowerShell. Подробные сведения о синтаксисе, включая все доступные параметры, см. в руководстве [по skype для бизнеса Server 2015 Management Shell.](../management-shell.md)
  

|**Командлет**|**Описание**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Создание новой надстройки  <br/> |
|Set-CsPersistentChatAddin  <br/> |Настройка параметров для существующей надстройки  <br/> |
|Get-CsPersistentChatAddin  <br/> |Извлечение сведений о надстройки  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Удаление надстройки  <br/> |
   
### <a name="create-a-new-add-in"></a>Создание новой надстройки

Вы можете создать новую надстройку с помощью **cmdlet New-CsPersistentChatAddin.**
  
Например, следующая команда создает новую надстройку (с именем ITPersistentChatAddin) для пула atl-cs-001.contoso.com. Параметр URL и его значение указывают расположение http://atl-cs-001.contoso.com/itchat веб-страницы надстройки:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Настройка параметров для существующей надстройки

Параметры существующей надстройки можно настроить с помощью **cmdlet Set-CsPersistentChatAddIn.** Например, следующая команда изменяет URL-адрес, присвоенный надстройке сохраняемого чата ITPersistentChatAddin. В этом случае URL-адрес меняется на http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Извлечение сведений о надстройки

Сведения о надстройке можно получить с помощью **cmdlet Get-CsPersistentChatAddin.** Например, следующая команда возвращает сведения обо всех надстройках сохраняемого чата, настроенных для использования в организации:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Удаление надстройки

Надстройку можно удалить с помощью **cmdlet Remove-CsPersistentChatAddIn.** Например, следующая команда удаляет надстройку сохраняемого чата ITChatAddin, найденную в пуле atl-cs-001.contoso.com:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


