---
title: Настройка параметров live события в группами Майкрософт
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Узнайте, как управлять параметрами для групп live события, которые хранятся в вашей организации.
f1keywords: ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8e12b6b85b61bb8c6312054be07dc37365c62c0
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "25748151"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Настройка параметров live события в группами Майкрософт
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Используйте параметры групп событий в реальном времени для настройки параметров для live события, которые хранятся в вашей организации. Можно настроить URL-адрес поддержки и настроить распределение видео стороннего поставщика. Эти параметры применяются ко всем событиям live, которые созданы в вашей организации. 

Можно легко управлять эти параметры в группами Майкрософт & Скайп по центру администрирования бизнеса. В левой области переходов, перейдите к **собраниям** > **Параметры событий в реальном времени**. 

![Live — событие settings.png] (../media/teams-live-events-settings.png "Снимок экрана команды live настройки событий, которые можно настроить в группами Майкрософт & Скайп по центру администрирования бизнеса") 

## <a name="set-up-event-support-url"></a>Настройка URL-адрес поддержки событий

Этот URL-адрес отображается в live участников события. Добавление поддержки URL-адрес для своей организации для предоставления возможности обратиться в службу поддержки во время события live участников.

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![команды логотип 30x30.png](../media/teams-logo-30x30.png) Использование групп Майкрософт & Скайп по центру администрирования бизнеса

1. В левой области переходов, перейдите к **собраниям** > **Параметры Live событий**.
2. В группе **Поддержки URL-адрес**введите URL-адрес поддержки вашей организации. 

    ![Параметр URL-адреса поддержки для live события в группами Майкрософт & Скайп по центру администрирования бизнеса] (../media/teams-live-events-settings-supporturl.png "Снимок экрана поддерживает URL-адрес, задание для групп событий в реальном времени")

### <a name="using-windows-powershell"></a>С помощью Windows PowerShell
Выполните следующее:
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
Для получения дополнительных сведений см [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).
## <a name="configure-a-third-party-video-distribution-provider"></a>Настройка распределение видео стороннего поставщика 

Если приобретается и настройка решения сети (SDN) определенного программного обеспечения или корпоративной сети (eCDN) решение через партнером Майкрософт и видео доставки настройте поставщика для событий в реальном времени в группах. 

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams--skype-for-business-admin-center"></a>![команды логотип 30x30.png](../media/teams-logo-30x30.png) Использование групп Майкрософт & Скайп по центру администрирования бизнеса

1. В левой области переходов, перейдите к **собраниям** > **Параметры Live событий**.
2. В разделе **сторонние поставщики распределение видео**установите следующие параметры. 

    ![Параметры поставщика распределение видео сторонних производителей в группами Майкрософт & Скайп по центру администрирования Business] (../media/teams-live-events-settings-distribution-provider.png "Снимок экрана параметров поставщика распределение видео сторонних производителей для события")

    - **Использование рассылки стороннего поставщика** Отключите этот вход в систему включить распределение видео стороннего поставщика.
    - **Имя поставщика SDN** Выберите поставщика, который вы используете.
    - **Ключ многократной установки поставщика** Введите код лицензии, полученный из контактов поставщика.
    - **URL-адрес шаблона SDN API** Введите URL-адрес шаблона API, полученный от поставщика контакт.

### <a name="using-windows-powershell"></a>С помощью Windows PowerShell
Получение маркера лицензии идентификатор или интерфейса API и шаблона API из контактов поставщика и затем выполните одно из следующих действий в зависимости от поставщика, который вы используете:

**Куст** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
Для получения дополнительных сведений см [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).

> [!NOTE]
> Если планируется создание live событий, использующих внешний кодировщики, необходимо также [настроить поставщика eCDN с Microsoft потока](https://docs.microsoft.com/stream/network-caching). 

### <a name="related-topics"></a>Связанные разделы
- [Что такое группы live событий?](what-are-teams-live-events.md)
- [Планирование групп событий в реальном времени](plan-for-teams-live-events.md)
- [Настройка для групп событий в реальном времени](set-up-for-teams-live-events.md)