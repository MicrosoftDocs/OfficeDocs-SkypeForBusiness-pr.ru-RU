---
title: Потоковая Teams собраний
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Узнайте, как настроить потоковую передачу и управлять Teams собраниями.
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127553"
---
# <a name="stream-teams-meetings"></a>Потоковая Teams собраний

Эта статья поможет вам настроить потоковую передачу для Teams собраний.

## <a name="what-is-streaming-and-how-does-it-work"></a>Что такое потоковая передача и как она работает?

Потоковая передача позволяет вашей организации расширить ваши возможности и предоставляет участникам собрания дополнительные параметры собрания. Если вы включаете потоковую передачу, организаторы могут передавать собрания и вебинары во внешние конечные точки, предоставляя URL-адрес протокола Real-Time (RTMP) и ключ для встроенного пользовательского приложения потоковой передачи в Teams.

> [!NOTE]
> Трансляция трансляций не может быть потоковой.

## <a name="set-up-streaming-with-powershell"></a>Настройка потоковой передачи с помощью PowerShell

Вы можете настроить в организации потоковую передачу с помощью PowerShell. В настоящее время эта политика недоступна в Teams администрирования. Политика "на пользователя" используется для указания пользователей, **которые** могут включить потоковую передачу. Она по умолчанию отключена.

Для этого в Windows PowerShell **Set-CsTeamsMeetingPolicy** можно использовать следующий атрибут: Дополнительные сведения о этом cmdlet см. в [сведениях о Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

- LiveStreamingMode

Чтобы включить потоковую  передачу для одного или более пользователей, установите для LiveStreamingMode (Включено) режим **LiveStreamingMode.**

> [!IMPORTANT]
> Чтобы организаторы могли передавать вебинары, необходимо включить регистрацию на собрании. Дополнительные сведения см. [в странице Настройка вебинары.](set-up-webinars.md)

### <a name="assign-the-policy"></a>Назначение политики

Дополнительные сведения о назначении политик с помощью PowerShell см. в [Teams.](policy-assignment-overview.md)

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик в Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Краткая инструкция — собрания, вебинары и трансляции](quick-start-meetings-live-events.md)