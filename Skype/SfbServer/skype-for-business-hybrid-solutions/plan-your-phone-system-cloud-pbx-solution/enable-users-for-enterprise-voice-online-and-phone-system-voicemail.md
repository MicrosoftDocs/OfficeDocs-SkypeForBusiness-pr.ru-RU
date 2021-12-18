---
title: Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Узнайте, как включить телефонная система голосовых служб для Skype для бизнеса пользователей.
ms.openlocfilehash: 9c9123b79a1fd5557d0d31db7b4b150bcda80af3
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563442"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии
 
> [!Important]
> Skype для бизнеса Online была отменена 31 июля 2021 г. И подключение КПС между локальной средой, будь то Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online, больше не поддерживается.  Узнайте, как подключить сеть локальной телефонии к Teams с помощью [прямого маршрутного маршрутинга.](/MicrosoftTeams/direct-routing-landing-page)

Узнайте, как включить телефонная система голосовых служб для Skype для бизнеса пользователей.
  
Последний шаг в развертывании телефонная система с локальной подключением PSTN — это включить пользователей для телефонная система и голосовой почты. Чтобы включить эти возможности, необходимо быть пользователем с ролью глобального администратора и иметь возможность запуска удаленной PowerShell. Необходимо следовать шагам в этом разделе для всех учетных записей пользователей, у Корпоративная голосовая связь для Skype для бизнеса Online.
  
## <a name="enable-phone-system-voice-services"></a>Включить телефонная система голосовых служб

Чтобы включить пользователя для телефонная система голосовой и голосовой почты, необходимо выполнить некоторые начальные действия, например проверить, развернут ли Skype для бизнеса Online Connector на ваших серверах и включить пользователей для размещенной голосовой почты.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Чтобы включить пользователей для телефонная система голосовой почты и голосовой почты

> [!NOTE]
> Skype для бизнеса в настоящее время является частью последнего Teams PowerShell Module.
> Если вы используете последний общедоступный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.

1. Перед началом убедитесь, что Teams PowerShell установлен на переднем сервере. Если это не так, установите с помощью инструкций в Teams [PowerShell Module Installation](/microsoftteams/teams-powershell-install).
    
2. Начните Windows PowerShell в качестве администратора.
    
3. Введите следующее и нажмите кнопку Ввод:
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Используйте Set-CsUser для назначения свойств $EnterpriseVoiceEnabled и $HostedVoiceMail пользователю следующим образом:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Например:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Вы также можете указать пользователя по его SIP-адресу, основному имени пользователя (UPN), домену и имени пользователя (domain\username) и отобразить имя в Active Directory ("Боб Келли"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Обновление строки URI и набора номера для пользователей, включенных для телефонная система

В этом разделе описывается обновление строки URI и набора номера для пользователей, включенных для телефонная система. 
  
### <a name="to-update-the-line-uri"></a>Обновление строки URI

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Используйте клавишу меню или настольного компьютера, чтобы открыть панель Skype для бизнеса Server управления.
    
    > [!NOTE]
    > Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть Skype для бизнеса Server панели управления. 
  
3. На левой панели навигации щелкните **Пользователи**.
    
4. В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.
    
5. В таблице щелкните Skype для бизнеса учетную запись пользователя, которую необходимо изменить строку URI.
    
6. Щелкните **строку URI** и введите уникальный, нормализованный номер телефона (например, tel:+14255550200). Затем нажмите **кнопку Фиксация**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Обновление набора набора с помощью локального Windows PowerShell-кодлетов

Вы можете назначить номера для каждого пользователя с помощью Windows PowerShell и [cmdlet Grant-CsDialPlan.](/powershell/module/skype/grant-csdialplan?view=skype-ps) Вы можете запустить этот комлет либо из Skype для бизнеса Server 2015 г., либо из удаленного сеанса Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Назначение набора для каждого пользователя одному пользователю

- Чтобы назначить пользователю Кену Мьеру наборную плану RedmondDialPlan для каждого пользователя, используйте коммюнике [Grant-CsDialPlan:](/powershell/module/skype/grant-csdialplan?view=skype-ps)
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Назначение набора для каждого пользователя нескольким пользователям

- Следующая команда назначает для каждого пользователя наборную плану RedmondDialPlan всем пользователям, которые работают в городе Редмонд. Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. в документации для [командлета Get-CsUser:](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Вы можете использовать глобальные или пользовательские наборные планы для пользователей в Интернете. Планы набора веб-сайтов нельзя использовать, так как они применяются только к пользователям, которые находятся в помещении и назначены локальному сайту. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Чтобы отоименить телефонную плану для каждого пользователя

- Используйте [комлет Grant-CsDialPlan,](/powershell/module/skype/grant-csdialplan?view=skype-ps) чтобы отогнать любую заданную ранее телефонную плану на одного пользователя Кену Myer. После того, как телефонная система для каждого пользователя не назначена, управление кеном Myer будет автоматически происходить с помощью глобальной шкалы или набора номера службы, назначенного его шлюзу Registrar или PSTN. Перед глобальной шкалой набора номеров области службы имеется преимущество:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Обновление политик маршрутики голосовой маршрутики с помощью локального Windows PowerShell-кодлетов

В этом разделе описывается обновление политик маршрутивки голосовой связи для пользователей, включенных для телефонная система.
  
телефонная система пользователям должна быть назначена политика маршрутизов голосовой почты для успешного маршрута звонков. Это отличается от локального бизнеса голосовых пользователей, которым требуется, чтобы им была назначена голосовая политика для успешного маршрута вызовов. Политика маршрутизации голосовой почты должна содержать использование PSTN, определяющие разрешенные вызовы и маршруты для телефонная система пользователей. Эти ПСПС можно скопировать из существующих голосовых политик в новые политики маршрутивки голосовой почты. Дополнительные сведения см. [в рублях New-CsVoiceRoutingPolicy.](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)
  
> [!NOTE]
> Всем телефонная система пользователям назначена та же политика голосовой почты в Интернете с именем BusinessVoice, которая определяет разрешенные функции вызова; например, Разрешить одновременное кольцо. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Назначение политики маршрутинга голосовых данных для каждого пользователя одному пользователю

- Используйте [кодлет Grant-CsVoiceRoutingPolicy,](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) чтобы назначить политику маршрутизации голосовой маршрутизации для каждого пользователя RedmondVoiceRoutingPolicy пользователю Кену Мойеру:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Назначение политики маршрутинга голосовой маршрутики для каждого пользователя нескольким пользователям

- Следующая команда назначает политику маршрутизации голосовых данных для каждого пользователя RedmondVoiceRoutingPolicy всем пользователям, которые работают в городе Редмонд. Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. [в пункте Get-CsUser.](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Вы можете использовать политики маршрутинга голосовой маршрутики global или User для пользователей в Интернете. Политики маршрутинга голосового голоса на сайте не могут использоваться, поскольку они применяются только к пользователям, которые находятся в помещении и назначены локальному сайту. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Чтобы отогласить политику маршрутизования голосовых данных для каждого пользователя

- Используйте Grant-CsVoiceRoutingPolicy, чтобы отогнать любую политику маршрутизования голосовых данных для каждого пользователя, ранее назначенную Кену Myer. После того, как политика маршрутизировки голосовых данных для каждого пользователя не назначена, управление ken Myer будет автоматически происходить с помощью глобальной политики маршрутизировки голосовых данных.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Дополнительные сведения см. [в рублях Grant-CsVoiceRoutingPolicy.](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)
