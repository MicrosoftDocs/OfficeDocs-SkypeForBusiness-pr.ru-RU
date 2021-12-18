---
title: Назначение политики маршрутизация голосовой связи
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как назначить голосовую политику для пользователей, использующих телефонная система с локальной связью PSTN.
ms.openlocfilehash: 158cd8e7bcd996297077adfb2c812febf4dc491b
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563360"
---
# <a name="assign-a-voice-routing-policy"></a>Назначение политики маршрутизация голосовой связи
 
> [!Important]
> Skype для бизнеса Online была отменена 31 июля 2021 г. И подключение КПС между локальной средой, будь то Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online, больше не поддерживается.  Узнайте, как подключить сеть локальной телефонии к Teams с помощью [прямого маршрутного маршрутинга.](/MicrosoftTeams/direct-routing-landing-page)

**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как назначить голосовую политику пользователям, использующим телефонная система с локальной связью PSTN. 
  
После того, как пользователь Skype для бизнеса в Интернете и телефонная система с локальной подключением PSTN, к ним будут применяться две политики голосовой связи. Одна из них — это локальное политика маршрутинга голосовой маршрутики, которую вы назначите в помещении. Эта политика может быть глобальной или пользовательской и определяет, какие записи использования PSTN связаны с пользователем. В этом разделе объясняется назначение этой политики.
  
Другая политика голосовой политики определяет, какие функции вызова доступны пользователю; эта политика голосовой связи определяется Корпорацией Майкрософт и идентична для всех пользователей телефонная система для локального подключения к PSTN. Оно автоматически назначено телефонная система пользователям.
  
|&nbsp;|Пользователь локальной сети|телефонная система с локальной пользователем подключения PSTN|
|:-----|:-----|:-----|
|Функции вызова, определенные в   |Политика голосовой связи   |Заранее определенные политики голосовой политики, назначенной автоматически, когда пользователь имеет лицензию на телефонная система.   |
|Записи использования PSTN, связанные с   |Политика голосовой связи   |Политика маршрутивки голосовых данных, назначенная в то время как пользователь по-прежнему находится в локальном помещении.   |
   
Выполните следующие действия, используя локальное развертывание, в то время как пользователь по-прежнему находится в локальном развертывании.
  
## <a name="using-a-global-voice-routing-policy"></a>Использование глобальной политики маршрутинга голосовой почты

Перед использованием глобальной политики маршрутичности голосовой связи телефонная система с пользователями подключения к сети PSTN на локальной основе, необходимо добавить записи об использовании PSTN в политику.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Назначение записей использования PSTN глобальной политике маршрутинга голосовых данных

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
3. Добавьте записи использования PSTN в политику:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Пример:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Создание новой политики маршрутивки голосовой почты

### <a name="to-create-a-new-voice-routing-policy"></a>Создание новой политики маршрутивки голосовой почты

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
3. Создайте новую политику маршрутинга голосовой почты:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Например:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

В этом примере создается новая политика маршрутизов голосовой маршрутики под названием HybridVoice, которая имеет два использования PSTN, связанных с ней.
  
## <a name="assigning-a-voice-routing-policy"></a>Назначение политики маршрутивки голосовой почты

Независимо от того, используете ли вы глобальную политику маршрутивки голосовой маршрутики или только для пользователей, используйте следующие действия для назначения политики пользователю.
  
### <a name="to-assign-the-voice-routing-policy"></a>Назначение политики маршрутики голосовой почты

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Запустите Skype для бизнеса Server: нажмите кнопку Начните, щелкните Все **программы,** нажмите кнопку Skype для бизнеса **2015,** а затем нажмите кнопку **Skype для бизнеса Server.**
    
3. Назначьте существующую политику голосовой связи пользователю:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Пример:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

В этом примере пользователю с именем Bob Kelly назначена ранее созданная голосовая политика с именем HybridVoice.
  
Дополнительные сведения о политиках маршрутизации голосовых данных см. в материале Create or modify a voice [policy and configure PSTN use records in Skype для бизнеса 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy)и [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy).
