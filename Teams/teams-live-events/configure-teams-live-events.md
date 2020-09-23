---
title: Настройка параметров трансляции в Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Сведения о том, как управлять параметрами для событий Teams, которые хранятся в Организации.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0e949b2773baa2cc819629133396020dee7d7d7
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203952"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Настройка параметров трансляции в Microsoft Teams

Используйте параметры Teams Live Events, чтобы настроить параметры для событий Live Events, которые хранятся в Организации. Вы можете настроить URL-адрес службы поддержки и настроить стороннего поставщика услуг для рассылки видео. Эти параметры применяются ко всем динамическим событиям, созданным в Организации.

Эти параметры можно легко настроить в центре администрирования Microsoft Teams. На панели навигации слева перейдите к параметрам **собраний**  >  **Live Events**.

![Снимок экрана с параметрами команд Live Events](../media/teams-live-events-settings.png "Снимок экрана с параметрами команд Live Events, которые можно настроить в центре администрирования Microsoft Teams")

## <a name="set-up-event-support-url"></a>Настройка URL-адреса службы поддержки событий

Этот URL-адрес отображается участникам интерактивных событий. Добавьте URL-адрес поддержки своей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время события Live.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. На панели навигации слева перейдите к параметрам **собраний**  >  **Live Event**.
2. В разделе **URL-адрес службы поддержки**введите URL-адрес своей организации.

    ![URL-адрес службы поддержки для событий Live в центре администрирования](../media/teams-live-events-settings-supporturl.png "Снимок экрана с параметром "URL-адрес поддержки" для событий Teams в реальном времени")

### <a name="using-windows-powershell"></a>Использование Windows PowerShell

Выполните следующее:

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
Дополнительные сведения можно найти в разделе [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Настройка стороннего поставщика услуг распространения видео 

Если вы приобрели и настроили решение для передачи данных по сети (SDN) или корпоративную сеть доставки содержимого (eCDN) через партнера по доставке Microsoft Video, настройте поставщика для событий Live Events в Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](../media/teams-logo-30x30.png) С помощью Центра администрирования Microsoft Teams

1. На панели навигации слева перейдите к параметрам **собраний**  >  **Live Event**.
2. В разделе **сторонние поставщики средств распространения видео**выполните указанные ниже действия. 

    ![Параметры стороннего поставщика услуг распространения видео в центре администрирования](../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры стороннего поставщика услуг распространения видео для событий Live")

    - **Использование стороннего поставщика услуг дистрибуции** Включите этот параметр, чтобы включить стороннего поставщика услуг для рассылки видео.
    - **Имя поставщика Sdn** Выберите поставщика, который вы используете.
    - **Лицензионный ключ поставщика** Введите идентификатор лицензии, полученный от контакта поставщика.
    - **URL-адрес шаблона API Sdn** Введите URL-адрес шаблона API, полученный от контакта поставщика.

### <a name="using-windows-powershell"></a>Использование Windows PowerShell
Получите идентификатор лицензии или токен API и шаблон API из контакта поставщика, а затем выполните одно из указанных ниже действий в зависимости от используемого поставщика.

**Куст** 
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

Дополнительные сведения можно найти в разделе [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Если вы планируете создавать события Live с помощью внешнего приложения или устройства, вам также потребуется [настроить поставщик eCDN с помощью Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

>[!Note]
> Поэтапный подход к изменению с помощью Microsoft Stream для [OneDrive для бизнеса и SharePoint для записей собраний](../tmr-meeting-recording-change.md) . На этапе запуска вы сможете принять участие в этой службе, в ноябре вам придется отказаться от использования потока, и в некоторых случаях на раннем этапе 2021 мы постараемся, чтобы все пользователи могли использовать OneDrive для бизнеса и SharePoint для новых записей о собраниях.

### <a name="related-topics"></a>Статьи по теме
- [Что такое прямые трансляции Teams?](what-are-teams-live-events.md)
- [Планирование прямых трансляций Teams](plan-for-teams-live-events.md)
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)