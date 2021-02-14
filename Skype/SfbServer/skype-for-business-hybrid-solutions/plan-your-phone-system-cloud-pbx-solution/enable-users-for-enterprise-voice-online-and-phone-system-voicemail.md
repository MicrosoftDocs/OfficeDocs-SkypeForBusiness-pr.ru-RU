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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Узнайте, как включить службы голосовой связи телефонной системы для пользователей Skype для бизнеса.
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625115"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Предоставление пользователям доступа к корпоративной голосовой связи через сеть и к голосовой почте по телефонной линии
 
> [!Important]
> Skype для бизнеса Online будет отменен 31 июля 2021 г., после чего служба станет недоступна.  Кроме того, подключение по STN между локальной средой через Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.  Узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутки.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Узнайте, как включить службы голосовой связи телефонной системы для пользователей Skype для бизнеса.
  
Последний шаг в развертывании телефонной системы с локальной связью через STN — включить для пользователей телефонную систему и голосовую почту. Чтобы включить эти возможности, необходимо быть пользователем с ролью глобального администратора и иметь возможность запускать удаленную точки PowerShell. В этом разделе необходимо выполнять действия для всех учетных записей пользователей, для Корпоративная голосовая связь в Skype для бизнеса Online.
  
## <a name="enable-phone-system-voice-services"></a>Включить голосовую службу телефонной системы

Чтобы включить для пользователя голосовую связь и голосовую почту телефонной системы, необходимо выполнить некоторые начальные действия, например проверить, развернут ли на серверах skype для бизнеса Online Connector, и включить для пользователей размещенную голосовую почту.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Чтобы пользователи могли использовать голосовую и голосовую почту телефонной системы

> [!NOTE]
> Skype для бизнеса Online Connector в настоящее время входит в состав последнего модуля Teams PowerShell.
> Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

1. Перед началом убедитесь, что модуль Teams PowerShell установлен на серверах переднего сервера. Если это не так, установите его с помощью инструкций в установке модуля [Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Начните Windows PowerShell администратором.
    
3. Введите следующую кнопку и нажмите ввод:
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. Введите следующую кнопку и нажмите ввод:
    
   ```powershell
   $cred = Get-Credential
   ```

    После нажатие на ввод должно отвести Windows PowerShell учетных данных.
    
5. Введите имя пользователя и пароль администратора клиента и нажмите кнопку **"ОК".**
    
6. В окне PowerShell введите следующую кнопку и нажмите ввод:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Импорт сеанса путем ввода следующего cmdlet:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    При запуске PowerShell в Skype для бизнеса Server локальные cmdlets Skype для бизнеса уже загружаются при запуске PowerShell. Необходимо указать параметр -AllowClobber, чтобы разрешить сетевым cmdlets переоценку локального cmdlets с тем же именем.
    
8. Используйте Set-CsUser для назначения свойств $EnterpriseVoiceEnabled и $HostedVoiceMail пользователю следующим образом:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Пример:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Вы также можете указать пользователя по его SIP-адресу, имени пользователя-пользователя, домену и имени пользователя (домен\имя пользователя) и отображаемом имени в Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Обновление URI линии и телефонной линии для пользователей с включенной телефонной системой

В этом разделе описывается обновление URI линии и телефонной линии для пользователей с включенной телефонной системой. 
  
### <a name="to-update-the-line-uri"></a>Обновление URI линии

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Используйте меню "Пуск" или ярлык на рабочем столе, чтобы открыть панель управления Skype для бизнеса Server.
    
    > [!NOTE]
    > Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
  
3. На левой панели навигации щелкните **Пользователи**.
    
4. В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.
    
5. В таблице щелкните учетную запись пользователя Skype для бизнеса, которую вы хотите изменить URI строки.
    
6. Щелкните **URI** линии и введите уникальный нормализованный номер телефона (например, tel:+14255550200). Затем нажмите **кнопку "Зафиксировать".**
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Обновление телефонной системы с помощью Windows PowerShell локальной системы

Вы можете назначать пользовательские наборы с помощью Windows PowerShell и с помощью Windows PowerShell [Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Вы можете запустить этот этотлет в Skype для бизнеса Server 2015 или в удаленном сеансе Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Назначение отдельной пользовательской телефонной плана одному пользователю

- Используйте для назначения пользователю Ken Myer пользовательской телефонной плана RedmondDialPlan с помощьюлета [Grant-CsDialPlan:](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Назначение набора номера на пользователя нескольким пользователям

- Следующая команда назначает пользовательскую телефонную план RedmondDialPlan всем пользователям, которые работают в городе Редмонд. Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. в документации по командлету [Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Вы можете использовать глобальные или пользовательские наборы для пользователей в Интернете. Нельзя использовать наборные планы сайта, так как они применяются только к пользователям, которые находятся локально и назначены локальному сайту. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Чтобы отоименовать телефонную план на пользователя

- Используйте для [этого cmdlet Grant-CsDialPlan,](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) чтобы отоименовать любую пользовательская телефонная плана, ранее назначенная пользователю Ken Myer. После того как на уровне пользователей не назначена, управление пользователем Ken Myer будет автоматически происходить с помощью глобальной или на уровне службы, назначенной его регистратору или шлюзу STN. Над глобальной телефонной сетью имеет приоритет dial plan области службы:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Обновление политик маршрутки голосовой почты с помощью Windows PowerShell локальной системы

В этом разделе описывается обновление политик маршрутки голосовых данных для пользователей, включенных в телефонную систему.
  
Для успешной маршрутки звонков пользователям телефонной системы должна быть назначена политика маршрутов голосовой связи. Это отличается от пользователей локальной бизнес-голосовой связи, которым требуется, чтобы им была назначена политика голосовой связи для успешной маршрутки вызовов. Политика маршрутизации голосовой связи должна содержать использование PSTN, определяющие авторизованные вызовы и маршруты для пользователей телефонной системы. Вы можете скопировать эти функции работы с PSTN из существующих политик голосовой почты в новые политики маршрутной голосовой почты. Дополнительные сведения см. в [new-CsVoiceRoutingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)
  
> [!NOTE]
> Всем пользователям телефонной системы назначена та же политика голосовой связи в Интернете с именем BusinessVoice, которая определяет разрешенные функции звонков; например, разрешить одновременный звонок. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Назначение политики маршрутки голосовой почты на одного пользователя одному пользователю

- Чтобы назначить политику маршрутизации голосовой почты на пользователя RedmondVoiceRoutingPolicy пользователю Ken Myer, используйте его с помощью cmdlet [Grant-CsVoiceRoutingPolicy:](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Назначение политики маршрутки голосовой почты на пользователя нескольким пользователям

- Следующая команда назначает политику маршрутизации голосовых данных на пользователя RedmondVoiceRoutingPolicy всем пользователям, которые работают в городе Редмонд. Дополнительные сведения о параметре LdapFilter, используемом в этой команде, см. в командной [команде Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Вы можете использовать глобальные или пользовательские политики маршрутинга голосовой почты для пользователей в Интернете. Политики маршрутки голосовой почты сайта нельзя использовать, так как они применяются только к пользователям, которые находятся локально и назначены локальному сайту. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Чтобы отоименовать политику маршрутизатики голосовой почты на пользователя, необходимо

- Используйте эту Grant-CsVoiceRoutingPolicy, чтобы отоименовать любую политику маршрутки голосовой почты на пользователя, ранее назначенную пользователю Ken Myer. После того как политика маршрутки голосовой почты на уровне пользователя не назначена, ken Myer будет автоматически управляться с помощью глобальной политики маршрутизировки голосовой почты.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Дополнительные сведения [см. в поддоме "Grant-CsVoiceRoutingPolicy".](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)
    

