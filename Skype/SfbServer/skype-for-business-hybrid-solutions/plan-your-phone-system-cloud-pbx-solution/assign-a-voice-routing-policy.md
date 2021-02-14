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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: Сводка. В этом разделе вы узнаете, как назначить политику голосовой связи пользователям, использующим телефонную систему с локальной связью через STN.
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359325"
---
# <a name="assign-a-voice-routing-policy"></a>Назначение политики маршрутизация голосовой связи
 
> [!Important]
> Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.  Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.  Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

**Сводка:** В этом разделе вы узнаете, как назначить политику голосовой связи пользователям, использующим телефонную систему с локальной связью через STN. 
  
После того как пользователь подключается к Skype для бизнеса Online и использует телефонную систему с локальной связью через STN, к ним будут применяться две политики голосовой связи. Один из них — это политика маршрутистики локальной голосовой почты, которую вы будете назначать локально. Эта политика может быть глобальной или пользовательской и определяет, какие записи использования STN связаны с пользователем. В этом разделе объясняется, как назначить эту политику.
  
Другая политика голосовой почты определяет, какие функции звонков доступны пользователю; Эта политика голосовой связи определяется корпорацией Майкрософт и идентична для всех пользователей телефонной системы с локальной связью по STN. Она автоматически назначена пользователям телефонной системы.
  
||**Пользователь локальной сети**|**Телефонная система с пользователем локального подключения к STN**|
|:-----|:-----|:-----|
|Функции звонков, определенные в  <br/> |Политика голосовой связи  <br/> |Предопределяемая политика голосовой связи, назначенная автоматически, когда у пользователя есть лицензия на телефонную систему.  <br/> |
|Записи использования PSTN, связанные с  <br/> |Политика голосовой связи  <br/> |Политика маршрутов голосовой почты, назначенная, когда пользователь по-прежнему находится в локальной сети.  <br/> |
   
Выполните следующие действия с использованием локального развертывания, пока пользователь по-прежнему находится в локальном развертывании.
  
## <a name="using-a-global-voice-routing-policy"></a>Использование глобальной политики маршрутов голосовой почты

Перед использованием глобальной политики маршрутки голосовой связи для телефонной системы с пользователями локальной сети ЗВОНКОВ необходимо добавить в политику записи об использовании ЗВОНКОВ.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>Назначение записей использования PSTN глобальной политике маршрутки голосовой почты

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Добавьте записи использования PSTN в политику:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Пример:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Создание новой политики маршрутки голосовой почты

### <a name="to-create-a-new-voice-routing-policy"></a>Создание новой политики маршрутки голосовой почты

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Создайте новую политику маршрутов голосовой почты:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Пример:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

В этом примере создается новая политика маршрутики голосовых данных HybridVoice с двумя связанными с ней вариантами работы с STN.
  
## <a name="assigning-a-voice-routing-policy"></a>Назначение политики маршрутной голосовой почты

Независимо от того, используете ли вы глобальную политику маршрутинга голосовой почты или политику для отдельных пользователей, для назначения политики пользователю используйте следующие действия.
  
### <a name="to-assign-the-voice-routing-policy"></a>Назначение политики маршрутки голосовой почты

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**
    
3. Назначьте существующую политику голосовой связи пользователю:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Пример:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

В этом примере пользователю с отображаемым именем Bob Kelly назначена ранее созданная политика голосовой связи с именем HybridVoice.
  
For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015,](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

