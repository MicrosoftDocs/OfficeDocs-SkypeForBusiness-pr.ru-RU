---
title: Настройка для live события в группами Майкрософт
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Узнайте, действия по настройке live для событий в Майкрософт для групп, включая подготовке сети, назначение лицензий, включение live события расписания для пользователей и настройка поставщика eCDN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354366"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Настройка для live события в группами Майкрософт
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

При установке для событий в реальном времени, существует несколько этапов, которые необходимо выполнить.

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Этап 1: Настройка сети для live событий в группах Microsoft
События live краткое требуют по [подготовке сети вашей организации для групп Майкрософт](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Шаг 2. Покупка и назначение лицензий
Убедитесь, у вас есть правильные лицензии назначения для [пользователей, которые можно создавать и планирования событий в реальном времени?](#who-can-create-and-schedule-live-events) и [пользователей, которые можно посмотреть событий в реальном времени?](#who-can-watch-live-events).

## <a name="step-3-enable-live-event-scheduling-for-users"></a>Шаг 3: Включите трансляция расписание для пользователей
Планирование Live события включен по умолчанию для группы пользователей, но если которым требуется пользователям планировать кодировщика внешних событий, которые существуют дополнительные действия, которые необходимо выполнить.

### <a name="for-quick-start-events"></a>Для события быстрого запуска
Параметр *AllowBroadcastScheduling* в **TeamsMeetingBroadcastPolicy** в команды PowerShell для управления ли пользователь может создавать событий в реальном времени в группах, или нет. Дополнительные сведения об управлении TeamsMeetingBroadcastPolicy [здесь](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Если вы еще не пользовательскую политику, назначенная для пользователей, пользователи будут получать *глобальной* политики, которая имеет запись по умолчанию.

Убедитесь, что параметр *AllowBroadcastScheduling* задано значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Назначьте пользователя в *глобальную* политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a>Пользовательские сценарии
**Требуется, чтобы все пользователи в вашей компании, чтобы иметь возможность создания событий в реальном времени.**

Если пользователи которым назначена политика *Glocal* , запустите и убедитесь, что *AllowBroadcastScheduling* * имеет значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Если пользователи назначена политика, отличный от *глобальной* политики, выполните следующую команду и убедитесь, что *- AllowBroadcastScheduling* задано значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Требуется трансляция планирования, чтобы быть отключено 100% внутри организации.**

Отключение широковещательного планирования, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначение всех пользователей в вашей организации для *глобальной* политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Требуется большое число пользователи должны иметь возможность создания событий в реальном времени, но для предотвращения их создания группы пользователей.**

Назначение политики *Global* , с помощью **Grant-CsTeamsMeetingBroadcastPolicy** для некоторых пользователей (включено), но сначала выполните следующую команду и убедитесь, что *AllowBroadcastScheduling* задано значение *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Назначьте одного или нескольких пользователей в *глобальную* политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создайте и назначьте политику для отключения планирования с помощью командлета **Grant-CsTeamsMeetingBroadcastPolicy** другим пользователям, (требуется выключить). 

Создание новой политики с ним этот параметр отключен, выполните:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Отключить расписание, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
Затем назначение пользователей для этой политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Хотите live события требуется запретить для большого числа пользователей, но требуется разрешить пользователям создавать их набор.**

Отключение широковещательного планирования, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Назначьте этих пользователей в *глобальную* политику, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Создание и назначение политики для включения планирования, выполните:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Включить расписание, выполните:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
Затем назначение пользователей для этой политики, выполните:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a>Для кодирования внешних событий
Необходимо выполнить следующие действия, чтобы включить трансляция расписания для этих пользователей.

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Шаг 1: Включение потока Майкрософт для пользователей в вашей организации **
Поток Microsoft доступна как часть подходящими подписки на Office 365 или как автономную службу. В разделе [Общие сведения о лицензировании потока](https://docs.microsoft.com/stream/license-overview) более подробных сведений.

> ! [ПРИМЕЧАНИЕ] Поток Майкрософт не включены в Business Essentials или бизнеса расширенный планов.  

Дополнительные сведения о как обеспечить [Назначение лицензий для пользователей в Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) , чтобы пользователи могут получить доступ к потоку Microsoft. Убедитесь, что поток Microsoft не блокируются для пользователей, как определено в [этой статье](https://docs.microsoft.com/stream/disable-user-organization).

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Шаг 2: Убедитесь, что пользователи имеют разрешение создания live событий в Microsoft потока **
По умолчанию администраторы могут создавать внешние кодировщика событий в реальном времени. Администратор Microsoft потока можно [Включить дополнительные пользователей для создания live события](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) в потоке.  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Шаг 3: Убедитесь live события, которое организаторов согласие политики в компании, задание с потока admin **
Если администратор Microsoft потока [Настройте политику рекомендации по организации](https://docs.microsoft.com/stream/company-policy-and-consent) и требует, чтобы сотрудники на прием данной политики перед сохранением контента, затем пользователей необходимо сделать перед созданием live события (с внешним кодировщика окончательные) в группах. Перед развертыванием функции событий в реальном времени в организации убедитесь, что пользователи, ответственных за создание участие в мероприятиях согласие в политике. 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Шаг 4: Установка поставщика eCDN для live события в группами Майкрософт 
Воспроизведение видео трансляция использует адаптивный скорость потоковая передача (ABR), но это одноадресной рассылки потока, что означает, что каждый средства просмотра начало собственные потока видео из Интернета. Для событий в реальном времени или видео, отправляемые большей части организации может быть значительное пропускной способности сети, используемый службами средств просмотра. Для организаций, чтобы уменьшить трафик Интернета для событий в реальном времени live события, для которых интегрированных решений с корпорации Майкрософт доверенных партнеров доставки видео предлагают программного обеспечения определенные сетей (SDNs) или корпоративной сети доставки содержимого (eCDNs). Эти SDN аудио- и eCDN платформы позволяют организациям для оптимизации пропускной способности сети без ущерба для конечного пользователя Просмотр каждый раз. Наши партнеры могут помочь включение легче масштабируются и эффективного распределение видео в корпоративной сети.

**Покупки и настройка решения за пределами группами Майкрософт** Справка: экспертов масштабирование доставки видео с помощью надежных доставки видео партнеров Майкрософт. Прежде чем включить поставщик видео доставки для использования с группами необходимо приобрести и настройка решения SDN/eCDN, находящиеся за пределами организации и отдельно от групп.

Следующие решения SDN/eCDN предварительно встроенные и может быть программы установки для использования с Microsoft потока.

- **Куст потоковая передача** предоставляет мощные и простые решения для рассылки видео и по запросу enterprise. Куст — это программное решение, которое не требует дополнительного оборудования или пропускной способности и обеспечивает безопасный способ включения тысячи одновременных средства просмотра видео без воздействия на вашей сети. Для клиентов, которым требуется понять, что наличие видео воздействия на своей сети перед приобретении решения на базе SDN/eCDN также куст потоковая передача предоставляет решения на основе браузера аналитики для клиентов корпорации Майкрософт. [Дополнительные сведения](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** — это облачная, смарт-авторами рассылки платформа, использующая инфраструктуры сети доставки содержимого, во многих формах, (live потоковое видео, видео по запросу, обновлений программного обеспечения, исправлений безопасности, и т.д.), быстрее надежно и с меньшей пропускной способности. Наш безопасной платформы является надежным, с крупнейших финансовых учреждениях в мире и с без дополнительного оборудования, настройки и обслуживания можно без труда. [Дополнительные сведения](http://www.kollective.com).
 
- **OmniCache увеличения** предоставляет рассылки следующего поколения сети и гарантирует удобства доставки видео в глобальной глобальных, как помочь поставщики событий оптимизации пропускной способности сети и поддержки успешные live мероприятий и по запросу Потоковая передача. Поддержка для увеличения OmniCache краткое live событий в ближайшее время.  [Дополнительные сведения](http://www.ramp.com). 
 
> [!NOTE] 
> Решение выбранного eCDN зависит от выбранного **стороннего поставщика условия политики конфиденциальности и службы**, какие будут управляет использование поставщика eCDN решения. Использование поставщика eCDN решение не будет использоваться условия лицензирования Майкрософт тома или Online Services терминов. Если вы не согласны с **условиями стороннего поставщика**, не включите eCDN решения в группах. 

**Настройка eCDN «Быстрый запуск» событий в реальном времени** Можно настроить поставщика eCDN для событий в реальном времени в группах, с помощью PowerShell. 

> [!NOTE] 
> Поставщик единого eCDN можно настроить для вашей организации. 

***Куст*** Командлет [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell можно использовать для настройки поставщика eCDN. Приобрести лицензии идентификатор и API URL-адрес шаблона от вашей куст контакта, затем выполните следующую команду:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** Командлет [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell можно использовать для настройки поставщика eCDN. Сначала получить маркер API и URL-адрес шаблона API из Kollective контакт, а затем выполните следующую команду:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Настройка eCDN для событий в реальном времени «Внешние кодировщика»** 

Если планируется создание live событий, использующих внешний кодировщики, необходимо также [настроить поставщика eCDN с Microsoft потока](https://docs.microsoft.com/stream/network-caching) . 

## <a name="next-steps"></a>Дальнейшие действия
Перейдите к [группам Confgure события](configure-teams-live-events.md).
