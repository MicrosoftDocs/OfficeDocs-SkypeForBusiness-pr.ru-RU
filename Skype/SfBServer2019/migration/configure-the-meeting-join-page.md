---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Когда пользователь щелкает ссылку на собрание в запросе собрания, страница соединения собрания обнаруживает, какой клиент уже установлен на компьютере пользователя. Если клиент уже установлен, он открывается и выполняет присоединение к собранию. Если клиент не установлен, по умолчанию откроется веб-приложение.
ms.openlocfilehash: c90e8afa95a73618eb1aa95b3d8d174e950e7e92a49988cb6146209f49cc0e58
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295126"
---
# <a name="configure-the-meeting-join-page"></a>Конфигурация страницы присоединения к собранию

Когда пользователь щелкает ссылку на собрание в запросе собрания, страница соединения собрания обнаруживает, какой клиент уже установлен на компьютере пользователя. Если клиент уже установлен, он открывается и выполняет присоединение к собранию. Если клиент не установлен, по умолчанию откроется веб-приложение.
  
Вы можете изменить поведение страницы присоединиться к собранию, если вы хотите разрешить пользователям присоединяться к собраниям. Эти параметры конфигурации были удалены из панели управления, но их можно настроить с помощью cmdlet CsWebServiceConfiguration.
  
**Параметры командлета CsWebServiceConfiguration для настройки страницы присоединения к собранию**

|**Параметр командлета CsWebServiceConfiguration**|**Description**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Если установлено true, пользователи, присоединяясь к собранию с помощью клиентского приложения, кроме Lync, будут иметь возможность присоединиться к собранию. Значение по умолчанию — False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |При наборе True альтернативные варианты присоединения к онлайн-конференции будут автоматически расширяться и показываться пользователям. При наборе false (значение по умолчанию) эти параметры будут доступны, но пользователю придется отобразить список параметров для себя.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Настройка страницы присоединиться к собранию с помощью Skype для бизнеса Server 2019 г.

1. Запустите Skype для бизнеса Server 2019: нажмите кнопку Начните, нажмите кнопку Все **программы,** щелкните Microsoft **Skype для бизнеса Server 2019,** а затем **нажмите кнопку Skype для бизнеса Server Shell** управления .
    
2. Выполните следующий командлет: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Этот командлет возвращает параметры конфигурации веб-службы.
    
3. Запустите следующую команду с параметрами True или False в зависимости от ваших предпочтений (сведения о параметрах этого командлета см. в документации [Skype для бизнеса Server Management Shell):](../../SfbServer/manage/management-shell.md)
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


