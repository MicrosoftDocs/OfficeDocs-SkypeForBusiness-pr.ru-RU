---
title: Потоковая передача собраний Teams
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
description: Узнайте, как настроить потоковую передачу для собраний Teams и управлять ими.
ms.openlocfilehash: 5e1e84fc3b0b4ed2f81b3f3a8c84450dc3cee56c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270184"
---
# <a name="stream-teams-meetings"></a>Потоковая передача собраний Teams

Эта статья поможет вам настроить потоковую передачу для собраний Teams.

## <a name="what-is-streaming-and-how-does-it-work"></a>Что такое потоковая передача и как она работает?

Потоковая передача позволяет вашей организации расширить доступ к собранию и предоставляет участникам собрания дополнительные возможности. При включении потоковой передачи организаторы могут передавать собрания и вебинары во внешние конечные точки, предоставляя URL-адрес и ключ протокола Real-Time (RTMP) для встроенного приложения пользовательской потоковой передачи в Teams.

> [!NOTE]
> Потоковая трансляция не поддерживается.

## <a name="set-up-streaming-with-powershell"></a>Настройка потоковой передачи с помощью PowerShell

Вы можете настроить в организации потоковую передачу с помощью PowerShell. В настоящее время эта политика недоступна в Центре администрирования Teams. Политика для каждого пользователя используется, чтобы указать, **кто** может включить потоковую трансляцию. Она по умолчанию отключена.

Для настройки потоковой передачи можно использовать следующий атрибут в Windows PowerShell **Set-CsTeamsMeetingPolicy**. Дополнительные сведения о командлете см. в [разделе Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

**Задайте для LiveStreamingMode** значение **Enabled**, чтобы включить возможности потоковой передачи для одного или нескольких пользователей.

> [!IMPORTANT]
> Необходимо включить регистрацию собрания, прежде чем организаторы смогут выполнять потоковую передачу вебинары. Дополнительные сведения см [. в разделе "Настройка вебинары"](set-up-webinars.md).

### <a name="assign-the-policy"></a>Назначение политики

Дополнительные сведения о назначении политик с помощью PowerShell см. в разделе ["Назначение политик в Teams"](policy-assignment-overview.md).

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик в Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Краткая инструкция — собрания, вебинары и трансляции](quick-start-meetings-live-events.md)