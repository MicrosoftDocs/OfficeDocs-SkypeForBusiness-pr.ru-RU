---
title: Проверка конференц-связи с телефонным подключением в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Общие сведения: Проверка конференций с телефонным подключением в Skype для бизнеса Server.'
ms.openlocfilehash: a19adba9d36fd7f862b9b40d3c7c239933fa7847
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992276"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Проверка конференц-связи с телефонным подключением в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как протестировать Конференц-связь с телефонным подключением в Skype для бизнеса Server.
  
Чтобы завершить проверку конфигурации конференц-связи с телефонным подключением, выполните поиск абонентских групп с регионом, для которого не задан ни один номер доступа, а также номеров доступа, для которых не задан ни один регион конференц-связи с телефонным подключением. Также следует проверить, что веб-страница "Параметры конференц-связи с телефонным подключением" и номера доступа к телефонному подключению работают правильно.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Поиск абонентских групп с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа

1. Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду в командной строке:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Этот командлет возвращает все абонентские группы с регионом конференц-связи с телефонным подключением, для которого не задан ни один номер доступа.
    
Дополнительные сведения можно найти в [статьях Get-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Поиск номеров доступа, которые не связаны ни с одним регионом

1. Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду в командной строке:
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Этот командлет возвращает все номера доступа к конференц-связи с телефонным подключением, которые не связаны ни с одним регионом.
    
Дополнительные сведения можно найти в [статьях Get-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Проверка веб-страницы и номеров доступа

Чтобы убедиться, что веб-страница «Параметры конференц-связи с телефонным подключением» и номера доступа к телефонному подключению работают правильно, выполните следующее:
  
- Протестируйте веб-страницу «Параметры конференц-связи с телефонным подключением», выполнив вход с использованием простого URL-адреса.
    
- Протестируйте правильность работы номеров доступа для определенного пула, запустив описанный ниже сценарий. Этот сценарий имитирует звонки на номера доступа. Для его использования вам требуется SIP-адрес и учетные данные одного клиента объединенных коммуникаций, размещенного в этом заданном пуле.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Тестирование номеров доступа для определенного пула

1. Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.
    
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Выполните следующую команду в командной строке:
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Полученный отчет показывает успешность или сбой операции, а также содержит диагностические сведения. Флаг-подробный содержит более подробные сведения о том, сколько номеров доступа было найдено, и о них.
    
Дополнительные сведения можно найти в разделе [Test-ксдиалинконференЦинг](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

