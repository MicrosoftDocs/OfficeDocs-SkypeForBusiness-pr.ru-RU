---
title: Переход на прямую маршрутизацию
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, что необходимо для перехода на прямую маршрутизацию применительно к Skype для бизнеса Online и настройке Teams.
ms.openlocfilehash: 11bf4ffe7e5e0f1c2fb177531c2eba36d081bf47
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359425"
---
# <a name="migrate-to-direct-routing"></a>Переход на прямую маршрутизацию

В этой статье описывается, что необходимо для перехода на прямую маршрутизацию применительно к Skype для бизнеса Online и настройке Microsoft Teams. Эта статья охватывает переход для следующих компонентов: 
 
- Телефонная система с планами звонков (для Teams и Skype для бизнеса Online) 
- Телефонная система с локальной связью через ПС в Skype для бизнеса Server (для Skype для бизнеса Online)  
- Телефонная система с возможностью подключения к локальной сети STN с помощью Cloud Connector Edition (для Skype для бизнеса Online)


В дополнение к этим этапам настройки, для пограничного контроллера сеансов также требуется настройка для маршрутизации вызовов на новый маршрут. Этот документ не охватывает данный аспект. Дополнительные сведения см. в документации поставщика пограничного контроллера сеансов.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Конечное состояние подготовки пользователей для различных вариантов подключения к ТСОП 

В следующей таблице показано, в чем конечный состояние пользователя, для пользователя, который должен подключаться к выбранным вариантам связи через телефонную систему. Отображаются только те атрибуты, которые относятся к голосовой связи.

|Атрибуты объекта-пользователя |Телефонная система с планами звонков|Телефонная система с возможностью подключения к локальной ТСОП через Skype для бизнеса Server|Телефонная система с возможностью подключения к локальной ТСОП через Cloud Connector|Телефонная система с возможностью подключения к локальной ТСОП через прямую маршрутизацию|
|---|---|---|---|---|
|Клиент|Skype для бизнеса или Teams |Skype для бизнеса |Skype для бизнеса |В Teams|
|Лицензии|Skype для бизнеса Online</br>План 2</br></br>(MCOProfessional или MCOSTANDARD)</br></br></br>Телефонная система (MCOEV)</br></br></br>Планы звонков</br>Teams|Skype для бизнеса Online план 2 (MCOProfessional или MCOSTANDARD)</br></br></br>Телефонная система (MCOEV)|Skype для бизнеса Online план 2 (MCOProfessional или MCOSTANDARD)</br></br></br>Телефонная система (MCOEV)|Skype для бизнеса Online план 2 (MCOProfessional или MCOSTANDARD)</br></br></br>Телефонная система (MCOEV)</br></br>Teams|
OnPremLineURI |Недоступно|Номер телефона должен быть синхронизирован с локальной службой AD. |Управлять номером телефона можно как в локальной службе Active Directory, так и в службе Azure Active Directory.|Управлять номером телефона можно как в локальной службе Active Directory, так и в службе Azure Active Directory. Тем не менее, если в организации используется локальная среда Skype для бизнеса, необходимо синхронизировать номер из локальной службы Active Directory.|
|LineURI|Номер телефона для вызовов по ТСОП|Автоматическая настройка из параметра OnPremLineURI|Автоматическая настройка из параметра OnPremLineURI|Автоматическая настройка из параметра OnPremLineURI|
|EnterpriseVoiceEnabled|Верно|Да|Да|Верно|
|HostedVoiceMail |Верно|Да|Да|Верно|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Имеет значение|Имеет значение|Имеет значение|Недоступно|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Имеет значение|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|Верно|Недоступно|Недоступно|Верно|
|TeamsCallingPolicy</br>AllowGroupCalling|Верно|Недоступно|Недоступно|Верно|
||||||

<sup>1</sup> Выбор нужного режима TeamsUpgradePolicy зависит от сценария. Прочитайте о различных режимах голосовой связи в статье [Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md)

В рамках этого процесса корпорация Майкрософт недавно обновила "центр администрирования Microsoft Teams" (также известный как современный портал) для отражения новой модели управления на основе режимов сосуществования. В Современном портале при настройкеTeamsUpgradePolicy будет автоматически установлен параметр TeamsInteropPolicy для обеспечения согласованного значения, поэтому TeamsInteropPolicy больше не отображается в пользовательском интерфейсе. Тем не менее, администраторы, использующие PowerShell должны настраивать оба параметра TeamsUpgradePolicy и TeamsInteropPolicy вместе, чтобы обеспечить надлежащую маршрутизацию. После завершения перехода на TeamsUpgradePolicy, больше не потребуется настраивать также TeamsInteropPolicy.

Дополнительные сведения см. в статье [Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md)

## <a name="migrating-from-calling-plans"></a>Переход с тарифных планов

Дополнительные сведения о переходе с тарифных планов см. в разделах:

- [Настройка планов звонков](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice User](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Рекомендуется удалить сведения о ранее настроенном тарифном плане, как указано ниже: 
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Переход с телефонной системы Office 365 с возможностью подключения к локальной ТСОП в Skype для бизнеса Server

Дополнительные сведения о переходе с телефонной системы с возможностью подключения к локальной ТСОП в Skype для бизнеса Server см. в следующих статьях:

- [Планирование](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Развертывание](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Рекомендуется удалить сведения о ранее настроенной маршрутизации голосовй связи, как указано ниже: 

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> Если настроена глобальная политика CsVoiceRoutingPolicy, рекомендуется удалить все связанные с этой глобальной политикой использование ННР. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Переход с телефонной системы Office 365 с возможностью подключения к локальной ТСОП через Cloud Connector Edition 

> [!Important]
> Выпуск Cloud Connector Edition будет отсюду 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления организации до Teams узнайте, как подключить свою локальное телефонную сеть к Teams с помощью прямой [маршрутизации.](direct-routing-landing-page.md)

Дополнительные сведения о переходе с телефонной системы с возможностью подключения к локальной ТСОП через Cloud Connector см. в следующих статьях:

- [Планирование](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Развертывание](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Пользовательская конфигурация](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Рекомендуется удалить сведения о ранее настроенной маршрутизации голосовй связи, как указано ниже: 
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Связанные ссылки

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

