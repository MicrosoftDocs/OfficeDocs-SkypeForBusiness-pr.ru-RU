---
title: Тестирование телефонной сети в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: Сводка. Сведения о проверке телефонной сети в Skype для бизнеса Server.
ms.openlocfilehash: 214ec05c49072825e6a8744cb92db66d864e3d34
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827939"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Тестирование телефонной сети в Skype для бизнеса Server
 
**Сводка:** Learn how to test dial-in conferencing in Skype for Business Server.
  
Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением. Кроме того, следует убедиться, что веб-страницы параметров и номеров доступа для телефонного номера работают правильно.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Поиск dial plans with a dial-in conferencing region that is not used by an access number

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Выполните следующий командлет:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.
    
Дополнительные сведения см. в сведениях [о get-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="find-access-numbers-without-assigned-regions"></a>Поиск номеров доступа без присвоенных областей

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Выполните следующий командлет:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.
    
Дополнительные сведения см. в сведениях [о get-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="test-webpage-and-access-numbers"></a>Тестовые веб-страницы и номера доступа

Чтобы убедиться, что веб-страница «Параметры конференц-связи с телефонным подключением» и номера доступа к телефонному подключению работают правильно, выполните следующее:
  
- Протестируйте веб-страницу «Параметры конференц-связи с телефонным подключением», выполнив вход с использованием простого URL-адреса.
    
- Протестируйте правильность работы номеров доступа для определенного пула, запустив описанный ниже сценарий. Этот сценарий имитирует звонки на номера доступа. Для его использования вам требуется SIP-адрес и учетные данные одного клиента объединенных коммуникаций, размещенного в этом заданном пуле.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Тестирование номеров доступа для определенного пула

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Выполните следующую команду в командной строке:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Полученный отчет показывает успешность или сбой операции, а также содержит диагностические сведения. Флаг -Verbose предоставляет более подробные сведения о количестве найденных номеров доступа и сведения о них.
    
Дополнительные сведения [см. в test-CsDialInConferencing.](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)
  

