---
title: Включение пользователей для корпоративной голосовой связи через Интернет и телефонной системой в голосовой почты Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Узнайте, как включить телефонной системой в службах Office 365 голосовой связи для вашей Скайп для коммерческих пользователей.
ms.openlocfilehash: 9f11e52a3992e484643cfea06d0720d12e3f0e77
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657470"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Включение пользователей для корпоративной голосовой связи через Интернет и телефонной системой в голосовой почты Office 365
 
Узнайте, как включить телефонной системой в службах Office 365 голосовой связи для вашей Скайп для коммерческих пользователей.
  
— Это последний этап в развертывании телефонной системой в Office 365 с помощью подключения к ТСОП в локальной Включение пользователей для телефонной системой в Office 365 и голосовую почту. Активировать эти возможности может пользователь Office 365 с ролью "Глобальный администратор", который может управлять PowerShell в удаленном режиме. Выполните действия, описанные в этом разделе, с учетными записями всех пользователей, для которых еще не активирована корпоративная голосовая связь для Skype для бизнеса Online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Включение телефонной системой голосовых служб Office 365

Чтобы разрешить пользователям работу с телефонной системой в Office 365 голосовой связи и голосовой почты, необходимо выполнить некоторые начальные действия, как проверка для просмотра, если Скайп для Business Online Connector развертывается на серверах и включить пользователей для размещенной голосовой почты.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Чтобы включить пользователей для телефонной системой в Office 365 голосовой связи и голосовой почты

1. Прежде чем начать, проверьте, что Скайп для Business Connector Online (модуля Windows PowerShell) развертывается на серверах переднего плана. Если он не установлен, его можно загрузить из [центра загрузки Майкрософт](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Можно найти дополнительные сведения об использовании в этом модуле рассматривается настройка [компьютера для Скайп для бизнеса в Интернет управления](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Запустите Windows PowerShell от имени администратора.
    
3. Введите следующую команду и нажмите клавишу ВВОД.
    
   ```
   Import-Module skypeonlineconnector
   ```

4. Введите следующую команду и нажмите клавишу ВВОД.
    
   ```
   $cred = Get-Credential
   ```

    После нажатия клавиши ВВОД появится диалоговое окно "Учетные данные Windows PowerShell".
    
5. Введите имя пользователя администратора клиента и пароль, нажмите клавишу **ОК**.
    
6. В окне PowerShell введите следующую команду и нажмите клавишу ВВОД.
    
   ```
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Импортируйте сеанс с помощью следующего командлета.
    
   ```
   Import-PSSession $Session -AllowClobber
   ```

    Время выполнения PowerShell на Скайп для Business Server, локального Скайп по командлетам Business уже загружен при открытии PowerShell. Необходимо указать параметр - AllowClobber, чтобы разрешить командлеты online на перезапись локальных командлетов с тем же именем.
    
8. Выполните командлет Set-CsUser, чтобы назначить свойства $EnterpriseVoiceEnabled и $HostedVoiceMail пользователю:
    
   ```
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Например:
    
   ```
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > Вы можете определить пользователя по адресу SIP, по имени участника-пользователя (UPN), по имени домена и имени пользователи (домен\имя пользователя) и по отображаемому имени Active Directory (Bob Kelly). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Обновление URI линии и абонентская группа для пользователей, включенных в телефонной системой в Office 365

В этом разделе описывается, как обновить URI линии и абонентская группа для пользователей, включенных в телефонной системой в Office 365. 
  
### <a name="to-update-the-line-uri"></a>Обновление URI линии

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Откройте панель управления Skype для бизнеса Server, используя меню "Пуск" или ярлык на рабочем столе.
    
    > [!NOTE]
    > Кроме того, можно открыть окно браузера и ввести URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
  
3. На панели навигации слева щелкните **Пользователи**.
    
4. В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.
    
5. В таблице щелкните учетную запись пользователя Skype для бизнеса, для которой необходимо изменить URI линии.
    
6. Щелкните **URI строки** и введите уникальный нормализованный номер телефона (например, tel:+14255550200). Нажмите кнопку **Сохранить**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Обновление абонентской группы с использованием локальных командлетов Windows PowerShell

Пользователя можно назначить абонентских групп с помощью командлета [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) и Windows PowerShell. Можно выполнить этот командлет из Скайп для Business Server 2015 или из удаленного сеанса Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Назначение абонентской группы на уровне пользователей отдельному пользователю

- Командлет [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) используется для назначения абонентской группы на пользователей RedmondDialPlan пользователю Ken Myer:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Назначение абонентской группы на уровне пользователей нескольким пользователям

- Следующая команда назначает абонентскую группу на уровне пользователей RedmondDialPlan всем пользователям, работающим в городе Редмонд (Redmond). Дополнительные сведения о параметр LdapFilter, используемые в этой команде обратитесь к документации для командлета [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Для пользователей в сети можно использовать глобальные или пользовательские абонентские группы. Невозможно использовать абонентские группы сайта, так как они применимы только к тем пользователям, которые размещены локально и которым назначен локальный сайт. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Назначение абонентской группы на уровне пользователей

- Командлет [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Отмена назначения абонентской любого пользователя, ранее назначенную пользователю Ken Myer. После отмены назначения абонентской группы на уровне пользователей управление пользователем Ken Myer автоматически осуществляется с помощью глобальной абонентской группы или абонентской группы уровня службы, назначенной его службе Registrar или шлюзу ТСОП. Абонентская группа уровня службы обладает приоритетом по отношению к глобальной абонентской группе.
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Обновление политик маршрутизации голосовых вызовов с помощью локальных командлетов Windows PowerShell

В этом разделе описывается, как обновить политики маршрутизации голосовой связи для пользователей, включенных в телефонной системой в Office 365.
  
Система телефона в Office 365 пользователи должны иметь политики маршрутизации голосовой связи, назначенные им для вызовов перенаправлять успешно. В этом заключается отличие от локальных пользователей голосовой бизнес-связи, которым необходимо назначить политику голосовой связи для успешной маршрутизации вызовов. Политика маршрутизации голосовой связи должны содержать случаев использования PSTN, которые определяют авторизованного звонки и маршруты для телефонной системой в пользователей Office 365. Можно скопировать эти параметры из существующих политик голосовых вызовов в новые политики маршрутизации голосовых вызовов. Дополнительные сведения см. в разделе [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Все телефонной системой в Office 365 Пользователи назначаются же online политики голосовой связи с именем BusinessVoice, которая определяет телефонных функций разрешено; Например разрешить одновременный звонок. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Назначение политики маршрутизации голосовых вызовов на уровне пользователя одному пользователю

- Командлет [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) назначение политики маршрутизации голосовой связи redmondvoiceroutingpolicy, настроенную на пользователя пользователю Ken Myer:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Назначение политики маршрутизации голосовых вызовов на уровне пользователя для нескольких пользователей

- Далее команда назначает политику маршрутизации голосовой связи RedmondVoiceRoutingPolicy пользователя для всех пользователей, работающих в города Редмонд. Дополнительные сведения о параметр LdapFilter, используемый в эту команду [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)см.
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Для пользователей в сети можно использовать глобальные или пользовательские политики маршрутизации голосовых вызовов. Невозможно использовать политики маршрутизации голосовых вызовов сайта, так как они применимы только к тем пользователям, которые размещены локально и которым назначен локальный сайт. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Отмена назначения политики маршрутизации голосовых вызовов на уровне пользователя

- Используйте командлет Grant-CsVoiceRoutingPolicy, чтобы отменить любого пользователя голосовой маршрутизации политику, ранее назначенную пользователю Ken Myer. После отмены политики на уровне пользователя к пользователю Ken Myer будет автоматически применяться глобальная политика маршрутизации голосовых звонков.
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Дополнительные сведения см. в разделе [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

