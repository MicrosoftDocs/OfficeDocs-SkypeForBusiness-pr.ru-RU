---
title: Тестирование телефонных разговоров в Skype для бизнеса Server
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
description: Сводка. Сведения о проверке телефонных разговоров в Skype для бизнеса Server.
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096735"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Тестирование телефонных разговоров в Skype для бизнеса Server
 
**Сводка:** Узнайте, как протестировать диалоговое общение в Skype для бизнеса Server.
  
Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением. Кроме того, необходимо убедиться, что веб-сайт "Параметры параметров dial-in" и номера доступа к телефонным номерам работают правильно.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Поиск телефонных планов с регионом телефонных телефонных телефонов, который не используется номером доступа

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
3. Выполните следующий командлет:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.
    
Дополнительные сведения см. [в рублях Get-CsDialInConferencingAccessNumber.](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="find-access-numbers-without-assigned-regions"></a>Поиск номеров доступа без присвоенных регионов

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
3. Выполните следующий командлет:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.
    
Дополнительные сведения см. [в рублях Get-CsDialInConferencingAccessNumber.](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="test-webpage-and-access-numbers"></a>Тестовые номера веб-страницы и доступа

Чтобы убедиться, что веб-страница «Параметры конференц-связи с телефонным подключением» и номера доступа к телефонному подключению работают правильно, выполните следующее:
  
- Протестируйте веб-страницу «Параметры конференц-связи с телефонным подключением», выполнив вход с использованием простого URL-адреса.
    
- Протестируйте правильность работы номеров доступа для определенного пула, запустив описанный ниже сценарий. Этот сценарий имитирует звонки на номера доступа. Для его использования вам требуется SIP-адрес и учетные данные одного клиента объединенных коммуникаций, размещенного в этом заданном пуле.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Тестирование номеров доступа для определенного пула

1. Войдите на компьютер как член группы RTCUniversalServerAdmins или роли Cs-ServerAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**
    
3. Выполните следующую команду в командной строке:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Полученный отчет показывает успешность или сбой операции, а также содержит диагностические сведения. Флаг -Verbose предоставляет более подробные сведения о количестве найденных номеров доступа и сведениях о них.
    
Дополнительные сведения см. [в рублях Test-CsDialInConferencing.](/powershell/module/skype/test-csdialinconferencing?view=skype-ps)
