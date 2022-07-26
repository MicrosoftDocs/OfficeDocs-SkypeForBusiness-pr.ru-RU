---
title: Журналы браузера и трассировка для Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Узнайте о журналах Браузера и WebRTC, созданных Microsoft Teams, где их можно найти, как собирать журналы с помощью служба поддержки Майкрософт и как они могут помочь в мониторинге и устранении неполадок.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005483"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Журналы браузера и трассировка для Teams

Для некоторых категорий ошибок служба поддержки Майкрософт может потребоваться сбор трассировки браузера. Эти сведения могут содержать важные сведения о состоянии клиента Teams при возникновении ошибки. В этой статье описывается сбор журналов браузера и WebRTC для Teams.

## <a name="browser-logs"></a>Журналы браузера

Перед запуском трассировки браузера убедитесь, что вы вошли в Teams. Это важно сделать перед запуском трассировки, чтобы трассировка не содержала конфиденциальные сведения о входе.

После входа выберите одну из следующих ссылок, соответствующую браузеру, и выполните указанные ниже действия. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Пограничный сервер](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Сафари](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> На этом этапе замените все ссылки на портал Azure клиентом Teams.
  
## <a name="webrtc-logs-in-browsers"></a>Журналы WebRTC в браузерах

Журналы WebRTC могут служба поддержки Майкрософт, предоставляя сведения о подключении для аудио- и видеозвонков. Выполните действия, чтобы получить доступ к журналам WebRTC в Edge (Chromium) или Chrome:
  
1. Откройте новую вкладку и перейдите по одному из следующих URL-адресов:
    - Edge (Chromium):`edge://webrtc-internals/`
    - Хром: `chrome://webrtc-internals/`
  
2. Откройте веб-приложение Teams и воспроизведите проблему.
  
3. Назад на вкладку, доступ к которой был выполнен на шаге 1, и вы увидите по крайней мере две вкладки:
    - Запросы GetUserMedia
    - `https://teams.microsoft.com/url`

4. Выберите вкладку с именем приложения Teams и сохраните содержимое страницы.

## <a name="related-topics"></a>Статьи по теме

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)

[Настройка файлов журналов для мониторинга и устранения неполадок в Teams](/MicrosoftTeams/log-files)
