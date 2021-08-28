---
title: Настройка параметров трансляции в Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Узнайте, как управлять настройками Teams трансляций, которые проводятся в вашей организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8eccc6e885cef67d4f6240483d3995df88d7cfc
ms.sourcegitcommit: 25fd720c008dcf1573344e50d736131a20c3ac7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2021
ms.locfileid: "58683313"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Настройка параметров трансляции в Microsoft Teams

Используйте Teams трансляций, чтобы настроить параметры трансляций, которые проводятся в вашей организации. Вы можете настроить URL-адрес службы поддержки и стороного поставщика видеоконференции. Эти параметры применяются для всех трансляций, созданных в организации.

Вы можете легко управлять этими настройками в Microsoft Teams администрирования. В левой области навигации перейдите к **настройкам трансляций**  >  **собраний**.

![Снимок экрана: Teams трансляций](../media/teams-live-events-settings.png "Снимок экрана: Teams трансляций, которые можно настроить в Центре Microsoft Teams администрирования")

## <a name="set-up-event-support-url"></a>Настройка URL-адреса поддержки событий

Этот URL-адрес отображается для участников трансляции. Добавьте URL-адрес службы поддержки вашей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время трансляции.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. В левой области навигации перейдите в **параметры события**  >  **Meetings Live**.
2. В **области URL-адрес** службы поддержки введите URL-адрес службы поддержки вашей организации.

    ![Параметр URL-адреса поддержки для трансляций в Центре администрирования](../media/teams-live-events-settings-supporturl.png "Снимок экрана: URL-адрес службы поддержки для Teams трансляций")

### <a name="using-windows-powershell"></a>Использование Windows PowerShell

Выполните следующее:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Дополнительные сведения [см. в настройках Set-CsTeamsMeetingBroadcastConfiguration.](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>Настройка стороного поставщика видеоконференции 

Если вы приобрели и настроили программное решение для сети (SDN) или корпоративной сети доставки содержимого (eCDN) через партнера Майкрософт по доставке видео, настройте поставщика для трансляций в Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. В левой области навигации перейдите в **параметры события**  >  **Meetings Live**.
2. В **области Сторонние поставщики видеоконференции** выполните следующие этапы: 

    ![Параметры сторонного поставщика видеоконференции в Центре администрирования](../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры сторонного поставщика видеоконференции для трансляций")

    - **Использование стороного поставщика рассылки** Включим эту возможность, чтобы включить стороного поставщика видеоконференции.
    - **Имя поставщика SDN** Выберите поставщика, который вы используете.
    - **Ключ лицензии поставщика** Введите номер лицензии, который вы получили у своего поставщика.
    - **URL-адрес шаблона API SDN** Введите URL-адрес шаблона API, который вы получили от своего поставщика услуг.

### <a name="using-windows-powershell"></a>Использование Windows PowerShell
Получите от своего контакта ИД лицензии или маркер API и шаблон API, а затем запустите один из следующих решений в зависимости от используемого поставщика:

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

Дополнительные сведения [см. в настройках Set-CsTeamsMeetingBroadcastConfiguration.](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> Если вы планируете создавать трансляции с помощью внешнего приложения или устройства, вам также потребуется настроить поставщика [eCDN в Microsoft Stream.](/stream/network-caching) 

>[!Note]
> Переход с использования Microsoft Stream на [OneDrive для бизнеса и SharePoint для записей собраний](../tmr-meeting-recording-change.md) будет поэтапным процессом. При запуске вы сможете согласиться на использование этого интерфейса. В ноябре потребуется отказаться от использования, если вы хотите продолжить использование Stream. В начале 2021 г. мы сделаем использование OneDrive для бизнеса и SharePoint для новых записей собраний обязательным для всех пользователей.

>[!Note]
> Выбранное решение eCDN регулируется условиями обслуживания и политикой конфиденциальности сторон, которые регулируют использование решения поставщика eCDN. Использование решения поставщика eCDN не будет под тем же соглашением об использовании корпоративного лицензирования Майкрософт или Условиями онлайн-сервисов. Если вы не согласны с условиями сторонних поставщиков, не в включаете решение eCDN в Microsoft Teams.

### <a name="related-topics"></a>Статьи по теме
- [Что такое прямые трансляции Teams?](what-are-teams-live-events.md)
- [Планирование прямых трансляций Teams](plan-for-teams-live-events.md)
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
