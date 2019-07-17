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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Сведения о том, что необходимо для перехода на прямую маршрутизацию с точки зрения конфигурации в Skype для бизнеса Online и Teams.
ms.openlocfilehash: 49980a0364e729fc41e6fe716de336a8a28f85bb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759010"
---
# <a name="migrate-to-direct-routing"></a>Переход на прямую маршрутизацию

В этой статье описано, что необходимо для перехода на прямую маршрутизацию с точки зрения настройки Skype для бизнеса Online и Microsoft Teams. В этой статье рассматриваются следующие вопросы миграции. 
 
- Телефонная система Office 365 с тарифными планами (для Teams и Skype для бизнеса Online) 
- Телефонная система Office 365 с локальной связью по протоколу КТСОП в Skype для бизнеса Server (для Skype для бизнеса Online)  
- Телефонная система Office 365 с локальным подключением PSTN с помощью облачного соединителя (для Skype для бизнеса Online)

  
Помимо этих шагов настройки, для связи с новым маршрутом также требуется настройка на контроллере границ сеанса (SBC). За пределами области этого документа. Дополнительные сведения можно найти в документации поставщика SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Конечное состояние подготовки пользователей для различных параметров подключения по протоколу PSTN 

В приведенной ниже таблице показано конечное состояние для пользователя, предоставленного для выбранных параметров подключения по протоколу PSTN с помощью телефонной системы Office 365. Отображаются только те атрибуты, которые имеют отношение к голосовым звонкам.

|Атрибуты объекта "пользователь" |Телефонная система с тарифными планами|Телефонная система с подключением через локальную сеть PSTN через Skype для бизнеса Server|Телефонная система с локальным подключением КТСОП через облачный соединитель|Телефонная система с подключением через локальную сеть PSTN через прямую маршрутизацию|
|---|---|---|---|---|
|Клиент|Skype для бизнеса или Teams |Skype для бизнеса |Skype для бизнеса |Teams|
|Лицензирования|Skype для бизнеса Online</br>План 2</br></br>Мкопрофессионал или МКОСТАНДАРД)</br></br></br>Телефонная система (МКОЕВ)</br></br></br>Планы звонков</br>Команды|Skype для бизнеса Online (план 2) (Мкопрофессионал или МКОСТАНДАРД)</br></br></br>Телефонная система (МКОЕВ)|Skype для бизнеса Online (план 2) (Мкопрофессионал или МКОСТАНДАРД)</br></br></br>Телефонная система (МКОЕВ)|Skype для бизнеса Online (план 2) (Мкопрофессионал или МКОСТАНДАРД</br></br></br>Телефонная система (МКОЕВ)</br></br>Команды|
Онпремлинеури |Н/Д|Номер телефона должен быть синхронизирован из локальной рекламы. |Телефонный номер можно управлять либо в локальной службе каталогов Active Directory, либо в службе Azure Active Directory.|Телефонный номер можно управлять либо в локальной службе каталогов Active Directory, либо в службе Azure Active Directory. Тем не менее, если организация использует локальную версию Skype для бизнеса, необходимо синхронизировать номер из локальной службы каталогов Active Directory.|
|Линеури|Телефонный номер для звонков по PSTN|Задается автоматически из параметра Онпремлинеури|Задается автоматически из параметра Онпремлинеури|Задается автоматически из параметра Онпремлинеури|
|Ентерприсевоицеенаблед|True|True|True|True|
|Хостедвоицемаил |True|True|True|True|
|Воицеполици|Бусинессвоице|Хибридвоице|Хибридвоице|Хибридвоице|
|Хостедвоицемаилполици |Бусинессвоице|Бусинессвоице|Бусинессвоице|Бусинессвоице|
|Воицераутингполици|Имеет значение|Имеет значение|Имеет значение|Н/Д|
|Онлиневоицераутингполици|$Null|$Null|$Null|Имеет значение|
|Теамсупградеполици<sup>1</sup>|Теамсонли, Сфбонли или острова|$Null|$Null|О-ва или Теамсонли|
|Теамсинтерполици<sup>2</sup></br>Каллингдефаултклиент – ознакомьтесь с заметкой ниже.|Teams или SfB |SfB|SfB|Команды|
|Теамскаллингполици</br>Алловприватекаллинг|True|Н/Д|Н/Д|True|
|Теамскаллингполици</br>Алловграупкаллинг|True|Н/Д|Н/Д|True|
||||||

<sup>1</sup> Выбор правильного режима Теамсупградеполици зависит от сценария. Ознакомьтесь со сведениями о голосовых интерфейсах в разных режимах [, а также в руководстве по миграции и взаимодействии для организаций, использующих Teams в Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Как было объявлено ранее, Теамсинтеропполици будет прекращен (ориентирован на конец Q3), и его функции будут объединены в Теамсупградеполици. Взаимодействие и миграция будут управляться с использованием режима сосуществования, который определяется Теамсупградеполици, который теперь доступен. Выбор режима пользователя влияет на маршрутизацию входящих звонков и чатов, а также на то, какой клиент может инициировать разговоры и звонки, а также планировать собрания. Несмотря на то, что Теамсинтеропполици будет удалено, оно по-прежнему должно быть настроено параллельно с Теамсупградеполици на этапе.  

В ходе этого усилия Корпорация Майкрософт обновила "центр администрирования Microsoft Teams" (также называемый современным порталом) для отражения новой модели управления на основе режима сосуществования. В современных порталах при настройке Теамсупградеполици будет автоматически задано Теамсинтеропполици на постоянную величину, поэтому Теамсинтеропполици больше не отображается в пользовательском интерфейсе. Однако администраторы, использующие PowerShell, должны по-прежнему устанавливать и Теамсупградеполици, и Теамсинтеропполици вместе для обеспечения надлежащей маршрутизации. После того как переход на Теамсупградеполици завершится, он больше не понадобится для настройки Теамсинтеропполици.

Дополнительные сведения можно найти в [статье Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Переход с планов звонков

Дополнительные сведения о переходе с планов звонков можно найти в следующих статьях:

- [Настройка планов звонков](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-Ксонлиневоице User](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-Ксонлинелислокатион](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Рекомендуется удалить ранее настроенные сведения о плане лицензирования, как описано ниже.
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Переход с телефонной системы Office 365 с использованием локальной сети PSTN в Skype для бизнеса Server

Дополнительные сведения о переходе с телефонной системы на локальную сеть PSTN в Skype для бизнеса Server можно найти в следующих статьях:

- [Планирование](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Ворачивани](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

Рекомендуется удалить предварительно настроенные данные для голосовой маршрутизации, как описано ниже.

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Переход с телефонной системы Office 365 с использованием локальной сети PSTN с помощью Cloud Connector Edition 

Дополнительные сведения о переходе с телефонной системы на локальную сеть PSTN через облачный соединитель можно найти в следующих статьях:

- [Планирование](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Ворачивани](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Пользовательская конфигурация](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

Рекомендуется удалить предварительно настроенные данные для голосовой маршрутизации, как описано ниже.
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>ДОПОЛНИТЕЛЬНЫЕ ССЫЛКИ

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md)

[Grant-Кстеамсупградеполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-Кстеамсупградеполици](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-Кстеамсупградеполици](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-Кстеамсупградеполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-Кстеамсупградеполици](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-Кстеамсупградеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-Кстеамсупградеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

