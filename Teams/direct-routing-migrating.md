---
title: Переход на прямой маршрутизации
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Сведения, необходимые для переноса в прямой маршрутизации из Скайп для бизнеса в Интернет и перспективы конфигурации группы.
ms.openlocfilehash: 4a1cb3d96d6f5d024b8da6a42288b09b3a8cde3d
ms.sourcegitcommit: 2f3d105203edbc21bbbb9c17390b1d3011ef4546
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "20084595"
---
# <a name="migrating-to-direct-routing"></a>Переход на прямой маршрутизации

В этой статье описываются необходимые для переноса в прямой маршрутизации из Скайп для бизнеса в Интернет и группами Майкрософт перспективы конфигурации. В этой статье обсуждается переход из следующих вариантов: 
 
- Планы Office 365 телефонной системой мыши (для групп и Скайп для бизнеса Интернет-версия) 
- Office 365 телефонной системой с локального подключения к ТСОП в Скайп Business Server (для Скайп для бизнеса Интернет-версия)  
- Office 365 телефонной системой с локального подключения к ТСОП с помощью соединителя облака (для Скайп для бизнеса в Интернет)

  
Помимо этих шагов по настройке конфигурации также требуется на пограничный контроллер сеансов (SBC) для маршрутизации вызовов для нового маршрута. Которое выходит за рамки этого документа. Для получения дополнительных сведений обратитесь к документации поставщика SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Конечное состояние для различные варианты подключения к ТСОП подготовки пользователей 

В следующей таблице показаны конечное состояние для пользователя, подготовленными для выбранной конфигурации подключения к ТСОП с телефонной системой Office 365. Отображаются только атрибутов для голосовой связи.

|Атрибуты объекта пользователя |Телефонная система с планами звонков|Phone системы с локального подключения к ТСОП через Скайп для Business Server|Телефон системы с локального подключения к ТСОП через соединитель облако|Телефон системы с локального подключения к ТСОП с помощью прямой маршрутизации|
|---|---|---|---|---|
|Client|Скайп для бизнеса или группами |Skype для бизнеса |Skype для бизнеса |Teams|
|Лицензии|Business Скайп Интернет-версия</br>План 2</br></br>MCOProfessional или MCOSTANDARD)</br></br></br>Телефонной системой (MCOEV)</br></br></br>Планы звонков</br>Teams|Скайп Business Online (план 2) (MCOProfessional или MCOSTANDARD)</br></br></br>Телефонной системой (MCOEV)|Скайп Business Online (план 2) (MCOProfessional или MCOSTANDARD)</br></br></br>Телефонной системой (MCOEV)|Скайп Business Online (план 2) (MCOProfessional или MCOSTANDARD</br></br></br>Телефонной системой (MCOEV)</br></br>Teams|
OnPremLineURI |Н/Д|Номер телефона должен быть синхронизирован из локальной AD. |Номер телефона может осуществляться в локальной службе Active Directory или в Azure Active Directory.|Номер телефона может осуществляться в локальной службе Active Directory или в Azure Active Directory. Тем не менее если в организации в локальной Скайп для бизнеса, номер должен синхронизирован из локального Active Directory.|
|LineURI|Вызов ТСОП номер телефона|Автоматической установки с помощью параметра OnPremLineURI|Автоматической установки с помощью параметра OnPremLineURI|Автоматической установки с помощью параметра OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Имеет значение|Имеет значение|Имеет значение|Н/Д|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Имеет значение|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly или о-ва|$Null|$Null|О-ва или TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient – Прочитайте примечание ниже.|Группы или SfB |SfB|SfB|Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|Н/Д|Н/Д|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|Н/Д|Н/Д|True|
||||||

<sup>1</sup> Выбор правой режим TeamsUpgradePolicy зависит от сценария. Прочитайте о качества голосовой связи в различных режимах в [миграции и рекомендации по организации взаимодействия с помощью команды Скайп для бизнеса](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Как ранее вышеперечисленные TeamsInteropPolicy будет из эксплуатации (предназначенной для конечных Q3) и консолидированной среды его функциональные возможности в TeamsUpgradePolicy. Взаимодействие и миграция будут управляться в режиме «совместная работа», определяемой на TeamsUpgradePolicy, который теперь доступен. Выбор режима пользователя имеют преимущественную силу маршрутизации входящих вызовов и чатов и в которой клиентские пользователя можно инициировать чаты и звонков или планировать собрания. Во время будет не поддерживается TeamsInteropPolicy, он все еще необходимо задать параллельно с TeamsUpgradePolicy во время phaseout.  

В рамках этой работы недавно были обновлены в «Microsoft групп & Скайп для бизнеса Центр администрирования» (также известной как современные портал) в соответствии с новой модели управления на основании режимы сосуществования. В современных портала Настройка будет TeamsUpgradePolicy теперь автоматически также необходимо задать TeamsInteropPolicy согласованные значения, поэтому TeamsInteropPolicy больше не отображается в интерфейсе пользователя. Тем не менее с помощью PowerShell "Администраторы" по-прежнему необходимо задать как TeamsUpgradePolicy и TeamsInteropPolicy друг с другом для обеспечения правильной маршрутизации. После завершения перехода на TeamsUpgradePolicy оно больше не будет необходимо также установить TeamsInteropPolicy.

Для получения дополнительных сведений обратитесь к [миграции и взаимодействие руководство для организаций, с помощью команды Скайп для бизнеса](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Миграция с Тарифные планы

Дополнительные сведения о миграции с вызова планы можно:

- [Настройка планов звонков](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [SET-CsOnlineVoice пользователя](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/en-us/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Рекомендуется удалить сведения о лицензировании план previouslycconfigured следующим образом:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Миграция с телефонной системой Office 365 с помощью локального подключения к ТСОП в Скайп for Business Server

Дополнительные сведения о миграции с телефонной системой с локального подключения к ТСОП в Скайп for Business Server см.:

- [Планирование](https://technet.microsoft.com/en-us/library/mt455212.aspx)
- [Развертывание](https://technet.microsoft.com/en-us/library/mt634319.aspx) 

Рекомендуется удалить ранее настроенные голосовой связи, сведений о маршрутизации следующим образом:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Миграция с Office 365 телефонной системой локального подключения к ТСОП через облако соединителя Edition 

Дополнительные сведения о миграции с телефонной системой с локального подключения к ТСОП через соединитель облачных см.:

- [Планирование](https://technet.microsoft.com/en-us/library/mt605227.aspx)  
- [Развертывание](https://technet.microsoft.com/en-us/library/mt634319.aspx)
- [Пользовательская конфигурация](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Рекомендуется удалить ранее настроенные голосовой связи, сведений о маршрутизации следующим образом:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>ССЫЛКИ ПО ТЕМЕ

[Руководство по миграции и взаимодействия для организаций, с помощью команды Скайп для бизнеса](migration-interop-guidance-for-teams-with-skype.md)

[Предоставление CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[Новый CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[SET-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[SET-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

