---
title: Настройка параметров трансляции в Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
description: Узнайте, как управлять параметрами трансляций Teams, которые хранятся в вашей организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd870acf26300b38ceb4b1e54b6e3bbdcbf1b92d
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614562"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Настройка параметров трансляции в Microsoft Teams

Используйте параметры трансляций Teams для настройки параметров для трансляций, которые хранятся в вашей организации. Вы можете настроить URL-адрес службы поддержки и сторонний поставщик распространения видео. Эти параметры применяются ко всем трансляциям, созданным в вашей организации.

Вы можете легко управлять этими параметрами в Центре администрирования Microsoft Teams. В области навигации слева перейдите к параметрам **трансляций** > **собраний**.

![Снимок экрана: параметры трансляций Teams.](../media/teams-live-events-settings-new.png "Снимок экрана: параметры трансляций Teams, которые можно настроить в Центре администрирования Microsoft Teams")

## <a name="set-up-event-support-url"></a>Настройка URL-адреса поддержки событий

Этот URL-адрес отображается для участников трансляции. Добавьте URL-адрес службы поддержки для своей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время трансляции.

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к **параметрам трансляции** > **собраний**.
2. В **поле "URL-адрес** службы поддержки" введите URL-адрес службы поддержки вашей организации.

    ![Поддержка параметра URL-адреса для трансляций в Центре администрирования.](../media/teams-live-events-settings-supporturl.png "Снимок экрана: параметр URL-адреса поддержки для трансляций Teams")

### <a name="using-windows-powershell"></a>Использование Windows PowerShell

Выполните следующее:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Дополнительные сведения см. в [разделе Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).
## <a name="configure-a-third-party-video-distribution-provider"></a>Настройка стороннего поставщика распространения видео 

Если вы приобрели и настроили решение программно-определяемой сети (SDN) или решение корпоративной сети доставки содержимого (eCDN) через партнера майкрософт по доставке видео, настройте поставщика для трансляций в Teams. 

### <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к **параметрам трансляции** > **собраний**.
2. В **разделе сторонних поставщиков распространения видео** выполните следующие действия. 

    ![Параметры стороннего поставщика распространения видео в Центре администрирования.](../media/teams-live-events-settings-distribution-provider-new.png "Снимок экрана: параметры стороннего поставщика распространения видео для трансляций")

    - **Сторонний поставщик дистрибутивов** Включите этот параметр, чтобы включить стороннего поставщика распространения видео.
    - **Имя поставщика SDN** Выберите поставщика, который вы используете.
    - **Конфигурация SDN** Введите сведения о конфигурации SDN.
        
### <a name="using-windows-powershell"></a>Использование Windows PowerShell
Получите идентификатор лицензии или маркер API и шаблон API от контакта поставщика, а затем выполните одно из следующих действий в зависимости от поставщика, который вы используете:

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```
**Peer5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

Дополнительные сведения см. в [разделе Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true).

> [!NOTE]
> Если вы планируете создавать трансляции с помощью внешнего приложения или устройства, необходимо также настроить поставщик [eCDN](/stream/network-caching) с помощью Microsoft Stream. 

>[!Note]
> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.

>[!Note]
> Выбранное решение eCDN регулируется условиями обслуживания и политикой конфиденциальности выбранного стороннего поставщика, которая будет регулировать использование решения поставщика eCDN. На использование решения поставщика eCDN не распространяются условия корпоративного лицензирования Майкрософт или условия использования веб-служб. Если вы не согласны с условиями стороннего поставщика, не включите решение eCDN в Microsoft Teams.

### <a name="related-topics"></a>См. также
- [Что такое прямые трансляции Teams?](what-are-teams-live-events.md)
- [Планирование трансляций Teams](plan-for-teams-live-events.md)
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
