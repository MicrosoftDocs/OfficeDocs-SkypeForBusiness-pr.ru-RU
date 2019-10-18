---
title: Настройка параметров трансляции в Microsoft Teams
author: chuckedmonson
ms.author: chucked
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
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb2b0f6c29af383061877562e8e6762965937f5f
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570194"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Настройка параметров трансляции в Microsoft Teams

Используйте параметры Teams Live Events, чтобы настроить параметры для событий Live Events, которые хранятся в Организации. Вы можете настроить URL-адрес службы поддержки и настроить стороннего поставщика услуг для рассылки видео. Эти параметры применяются ко всем динамическим событиям, созданным в Организации. 

Эти параметры можно легко настроить в центре администрирования Microsoft Teams. На панели навигации слева перейдите к параметрам **собраний** > **Live Events**. 

![Снимок экрана с параметрами команд Live Events](../media/teams-live-events-settings.png "Снимок экрана с параметрами команд Live Events, которые можно настроить в центре администрирования Microsoft Teams") 

## <a name="set-up-event-support-url"></a>Настройка URL-адреса службы поддержки событий

Этот URL-адрес отображается участникам интерактивных событий. Добавьте URL-адрес поддержки своей организации, чтобы предоставить участникам возможность обратиться в службу поддержки во время события Live.

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Значок, показывающий логотип Microsoft Teams](../media/teams-logo-30x30.png) Использование центра администрирования Microsoft Teams

1. На панели навигации слева перейдите к параметрам **собраний** > **Live Event**.
2. В разделе **URL-адрес службы поддержки**введите URL-адрес своей организации. 

    ![URL-адрес службы поддержки для событий Live в центре администрирования](../media/teams-live-events-settings-supporturl.png "Снимок экрана с параметром "URL-адрес поддержки" для событий Teams в реальном времени")

### <a name="using-windows-powershell"></a>Использование Windows PowerShell
Выполните следующее:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Дополнительные сведения можно найти в разделе [Set-кстеамсмитингброадкастконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Настройка стороннего поставщика услуг распространения видео 

Если вы приобрели и настроили решение для передачи данных по сети (SDN) или корпоративную сеть доставки содержимого (Екдн) через партнера по доставке Microsoft Video, настройте поставщика для событий Live Events в Teams. 

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Значок, показывающий логотип Microsoft Teams](../media/teams-logo-30x30.png) Использование центра администрирования Microsoft Teams

1. На панели навигации слева перейдите к параметрам **собраний** > **Live Event**.
2. В разделе **сторонние поставщики средств распространения видео**выполните указанные ниже действия. 

    ![Параметры стороннего поставщика услуг распространения видео в центре администрирования](../media/teams-live-events-settings-distribution-provider.png "Снимок экрана: параметры стороннего поставщика услуг распространения видео для событий Live")

    - **Использование стороннего поставщика услуг дистрибуции** Включите этот параметр, чтобы включить стороннего поставщика услуг для рассылки видео.
    - **Имя поставщика Sdn** Выберите поставщика, который вы используете.
    - **Лицензионный ключ поставщика** Введите идентификатор лицензии, полученный от контакта поставщика.
    - **URL-адрес шаблона API Sdn** Введите URL-адрес шаблона API, полученный от контакта поставщика.

### <a name="using-windows-powershell"></a>Использование Windows PowerShell
Получите идентификатор лицензии или токен API и шаблон API из контакта поставщика, а затем выполните одно из указанных ниже действий в зависимости от используемого поставщика.

**Куст** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**коллективе** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Дополнительные сведения можно найти в разделе [Set-кстеамсмитингброадкастконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Если вы планируете создавать события Live с помощью внешнего приложения или устройства, вам также потребуется [настроить поставщик екдн с помощью Microsoft Stream](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Статьи по теме
- [Что такое прямые трансляции Teams?](what-are-teams-live-events.md)
- [Планирование прямых трансляций Teams](plan-for-teams-live-events.md)
- [Настройка прямых трансляций Teams](set-up-for-teams-live-events.md)