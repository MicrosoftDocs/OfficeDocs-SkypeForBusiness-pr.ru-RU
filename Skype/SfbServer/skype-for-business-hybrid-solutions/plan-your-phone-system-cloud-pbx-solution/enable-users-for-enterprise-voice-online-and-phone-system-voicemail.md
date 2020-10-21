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
> Skype для бизнеса Online будет прекращен до 31 июля, 2021 после чего служба станет недоступна.  Кроме того, связь по протоколу PSTN между локальной средой и в Skype для бизнеса Server или Cloud Connector Edition и Skype для бизнеса Online больше не будет поддерживаться.  Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Узнайте, как включить службы голосовой связи телефонной системы для пользователей Skype для бизнеса.
  
Последним шагом в развертывании телефонной системы с локальной сетью PSTN является предоставление пользователям доступа к телефонной системе и голосовой почте. Чтобы включить эти возможности, необходимо быть пользователем с ролью глобального администратора и иметь возможность запускать удаленную оболочку PowerShell. Необходимо выполнить действия, описанные в этом разделе, для всех учетных записей пользователей, для которых еще не включена поддержка корпоративной голосовой связи в Skype для бизнеса Online.
  
## <a name="enable-phone-system-voice-services"></a>Включение служб голосовой связи телефонной системы

Чтобы включить поддержку голосовой и голосовой почты для телефонной системы, необходимо выполнить некоторые начальные действия, например проверить, развернут ли соединитель Skype для бизнеса Online на ваших серверах и разрешить ли пользователям размещенную голосовую почту.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Предоставление пользователям голосовой и голосовой почты телефонной системы

> [!NOTE]
> Skype для бизнеса Online Connector входит в состав последней версии модуля PowerShell Teams.
> Если вы используете последний [общедоступный выпуск Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.

1. Прежде чем приступать к работе, убедитесь, что на серверах переднего плана установлен модуль Teams PowerShell. Если это не так, установите их, выполнив инструкции [установки модуля Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Запустите Windows PowerShell от имени администратора.
    
3. Введите следующую команду и нажмите клавишу ВВОД:
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. Введите следующую команду и нажмите клавишу ВВОД:
    
   ```powershell
   $cred = Get-Credential
   ```

    После нажатия клавиши Ввод появится диалоговое окно учетные данные Windows PowerShell.
    
5. Введите имя пользователя и пароль администратора клиента и нажмите кнопку **ОК**.
    
6. В окне PowerShell введите следующую команду и нажмите клавишу ВВОД:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Чтобы импортировать сеанс, введите следующий командлет:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    При запуске PowerShell в Skype для бизнеса Server локальные командлеты Skype для бизнеса уже загружены при открытии PowerShell. Необходимо указать параметр-Алловклоббер, чтобы разрешить интерактивным командлетам перезаписать локальные командлеты с тем же именем.
    
8. Используйте командлет Set-CsUser, чтобы назначить пользователю свойства $EnterpriseVoiceEnabled и $HostedVoiceMail следующим образом:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Например,
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Вы также можете указать пользователя по его адресу SIP, имени участника-пользователя (UPN), имени домена и имени пользователя (домен \ имя_пользователя) и отображаемому имени в Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Обновление URI линии и абонентской группы для пользователей, поддерживающих телефонную систему

В этом разделе описывается обновление универсального кода ресурса (URI) и абонентской группы для пользователей с включенной поддержкой телефонной системы. 
  
### <a name="to-update-the-line-uri"></a>Обновление URI линии

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Используйте меню "Пуск" или ярлык на рабочем столе, чтобы открыть панель управления Skype для бизнеса Server.
    
    > [!NOTE]
    > Вы также можете открыть окно браузера, а затем ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
  
3. На левой панели навигации щелкните **Пользователи**.
    
4. В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.
    
5. В таблице щелкните учетную запись пользователя Skype для бизнеса, для которой требуется изменить URI линии.
    
6. Щелкните **URI строки**и введите уникальный нормализованный номер телефона (например, Tel: + 14255550200). Затем нажмите кнопку **сохранить**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Обновление абонентской группы с помощью локальных командлетов Windows PowerShell

Абонентские группы для отдельных пользователей можно назначить с помощью Windows PowerShell и командлета [Grant – CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Этот командлет можно выполнить как из Skype для бизнеса Server 2015, так и из удаленного сеанса Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Назначение абонентской группы отдельных пользователей одному пользователю

- С помощью командлета [Grant – CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) назначьте абонентскую абонентскую систему абонентскую redmonddialplan пользователю Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Назначение абонентской группы на уровне пользователей нескольким пользователям

- Следующая команда назначает абонентскую абонентскую систему абонентскую redmonddialplan всем пользователям, которые работают в городе Redmond. Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Для пользователей в сети можно использовать как глобальные, так и пользовательские абонентские группы. Абонентские группы сайта не могут использоваться, так как они применимы только к пользователям, размещенным локально и назначены локальному сайту. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Отмена назначения абонентской группы на уровне пользователя

- Используйте командлет [Grant – CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , чтобы отменить назначение абонентской группы на уровне пользователей, ранее назначенных Ken Myer. После назначения абонентской группы на уровне пользователя Ken Myer будет автоматически управляться с помощью глобальной абонентской группы или абонентской группы уровня службы, назначенной регистратору или шлюзу PSTN. Абонентская абонентская область службы имеет приоритет над глобальной абонентской группы.
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Обновление политик маршрутизации голосовых вызовов с помощью локальных командлетов Windows PowerShell

В этом разделе описывается, как обновить политики маршрутизации голосовых вызовов для пользователей, для которых включена поддержка телефонной системы.
  
Пользователям телефонной системы должна быть назначена политика маршрутизации голосовой связи для успешной маршрутизации звонков. Это отличается от пользователей локальной деловой голосовой связи, которым необходимо назначить политику голосовой связи, чтобы разрешить успешные звонки. Политика маршрутизации голосовой связи должна содержать сведения об использовании PSTN, определяющие авторизованные вызовы и маршруты для пользователей телефонной системы. Вы можете скопировать использование PSTN из существующих политик голосовой связи в новые политики маршрутизации голосовой связи. Дополнительные сведения см. в статье [New – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Всем пользователям телефонной системы назначается одна и та же политика голосовой связи с именем BusinessVoice, которая определяет разрешенные функции звонков; Например, разрешить Одновременный звонок. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Назначение политики маршрутизации голосовых вызовов для отдельных пользователей одному пользователю

- Используйте командлет [Grant – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) для назначения политики маршрутизации голосовых вызовов на уровне пользователя RedmondVoiceRoutingPolicy пользователю Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Назначение политики маршрутизации голосовых вызовов на уровне пользователей нескольким пользователям

- Следующая команда назначает политику маршрутизации голосовых вызовов на уровне пользователя RedmondVoiceRoutingPolicy всем пользователям, которые работают в городе Redmond. Для получения дополнительных сведений о параметре LdapFilter, используемом в этой команде, обратитесь к разделу [Get – CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Для пользователей Online можно использовать глобальные или пользовательские политики маршрутизации голосовых вызовов. Политики маршрутизации голосовой связи сайта не могут использоваться, так как они применяются только к пользователям, размещенным локально и назначенные локальному сайту. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Отмена назначения политики маршрутизации голосовых вызовов на уровне пользователя

- Используйте Grant-CsVoiceRoutingPolicy, чтобы отменить назначение любой политики маршрутизации голосовых вызовов на уровне пользователя, которая ранее была назначена Ken Myer. После назначения политики маршрутизации голосовых вызовов на уровне пользователя Ken Myer будет автоматически управляться с помощью глобальной политики маршрутизации голосовых вызовов.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Дополнительные сведения см. в разделе [Grant – CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

