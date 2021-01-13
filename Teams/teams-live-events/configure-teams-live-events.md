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
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
- enabler-strategic
description: Узнайте, как управлять настройками трансляций Teams, которые проводятся в вашей организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c62b7ed2afcfdb9baa779c57f3fcf566295053b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831199"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Настройка параметров трансляции в Microsoft Teams

Используйте параметры трансляций Teams для настройки параметров трансляций, которые проводятся в вашей организации. Вы можете настроить URL-адрес службы поддержки и сторонних поставщиков видеоконференции. Эти параметры применяются для всех трансляций, созданных в организации.

Вы можете легко управлять этими настройками в Центре администрирования Microsoft Teams. В области навигации слева перейдите к **настройкам**  >  **трансляций собраний.**

![Снимок экрана: параметры трансляций Teams](../media/teams-live-events-settings.png "Снимок экрана: параметры трансляций Teams, которые можно настроить в Центре администрирования Microsoft Teams")

## <a name="set-up-event-support-url"></a>НАСТРОЙКА URL-адреса поддержки событий

Этот URL-адрес отображается для участников трансляции. Добавьте URL-адрес службы поддержки для вашей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время трансляции.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к **настройкам**  >  **трансляции собраний.**
2. Введите **URL-адрес** службы поддержки своей организации.

    ![Параметр URL-адреса поддержки трансляций в Центре администрирования](../media/teams-live-events-settings-supporturl.png "Снимок экрана: параметр URL-адреса поддержки для трансляций Teams")

### <a name="using-windows-powershell"></a>Использование Windows PowerShell

Выполните следующее:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Дополнительные сведения [см. в set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>Настройка стороного поставщика видеоконференции 

Если вы приобрели и настроили программное решение для сети (SDN) или корпоративной сети доставки содержимого (eCDN) через партнера Майкрософт по доставке видео, настройте его для трансляций в Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. В области навигации слева перейдите к **настройкам**  >  **трансляции собраний.**
2. В **области сторонних поставщиков видеоконференции** выполните следующие этапы: 

    ![Параметры стороного поставщика видеоконференции в Центре администрирования](../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры сторонного поставщика видеоконференции для трансляций")

    - **Использование стороного поставщика рассылки** Включим эту возможность, чтобы включить стороного поставщика видеоконференции.
    - **Имя поставщика SDN** Выберите поставщика.
    - **Ключ лицензии поставщика** Введите номер лицензии, который вы получили у своего контакта поставщика.
    - **URL-адрес шаблона API SDN** Введите URL-адрес шаблона API, который вы получили у своего поставщика.

### <a name="using-windows-powershell"></a>Использование Windows PowerShell
Получите У контакта поставщика ИД лицензии или маркер API и шаблон API, а затем запустите один из следующих методов в зависимости от поставщика, который вы используете:

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

Дополнительные сведения [см. в set-CsTeamsMeetingBroadcastConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> Если вы планируете создавать трансляции с помощью внешнего приложения или устройства, необходимо также настроить поставщика [услуг eCDN в Microsoft Stream.](https://docs.microsoft.com/stream/network-caching) 

>[!Note]
> Переход с использования Microsoft Stream на [OneDrive для бизнеса и SharePoint для записей собраний](../tmr-meeting-recording-change.md) будет поэтапным процессом. При запуске вы сможете согласиться на использование этого интерфейса. В ноябре потребуется отказаться от использования, если вы хотите продолжить использование Stream. В начале 2021 г. мы сделаем использование OneDrive для бизнеса и SharePoint для новых записей собраний обязательным для всех пользователей.

### <a name="related-topics"></a>Статьи по теме
- [Что такое прямые трансляции Teams?](what-are-teams-live-events.md)
- [Планирование прямых трансляций Teams](plan-for-teams-live-events.md)
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)
