---
title: Потоковая Teams собраний
author: mkbond007
ms.author: mabond
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
description: Узнайте, как настроить потоковую передачу для собраний Teams и управлять ими.
ms.openlocfilehash: 352a0c2e7a0584640e466b5e46456906e4912d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646348"
---
# <a name="stream-teams-meetings"></a>Потоковая Teams собраний

Эта статья поможет вам настроить потоковую передачу для Teams собраний.

## <a name="what-is-streaming-and-how-does-it-work"></a>Что такое потоковая передача и как она работает?

Потоковая передача позволяет вашей организации расширить доступ к собранию и предоставляет участникам собрания дополнительные возможности. При включении потоковой передачи организаторы могут передавать собрания и вебинары во внешние конечные точки, предоставляя URL-адрес и ключ протокола Real-Time (RTMP) для встроенного приложения пользовательской потоковой передачи в Teams.

> [!NOTE]
> Потоковая трансляция не поддерживается.

## <a name="set-up-streaming-with-powershell"></a>Настройка потоковой передачи с помощью PowerShell

Вы можете настроить в организации потоковую передачу с помощью PowerShell. В настоящее время эта политика недоступна в Teams администрирования. Политика для каждого пользователя используется, чтобы указать, **кто** может включить потоковую трансляцию. Она по умолчанию отключена.

Для настройки потоковой передачи можно использовать следующий атрибут в Windows PowerShell **Set-CsTeamsMeetingPolicy**. Дополнительные сведения о командлете см. в [разделе Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

**Задайте для LiveStreamingMode** значение **Enabled**, чтобы включить возможности потоковой передачи для одного или нескольких пользователей.

> [!IMPORTANT]
> Необходимо включить регистрацию собрания, прежде чем организаторы смогут выполнять потоковую передачу вебинары. Дополнительные сведения см [. в разделе "Настройка вебинары"](set-up-webinars.md).

### <a name="assign-the-policy"></a>Назначение политики

Дополнительные сведения о назначении политик с помощью PowerShell см. в [Teams.](policy-assignment-overview.md)

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик в Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Краткая инструкция — собрания, вебинары и трансляции](quick-start-meetings-live-events.md)