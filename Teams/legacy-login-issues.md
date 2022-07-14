---
title: Проблемы с получением сообщений и вызовов в устаревших системах в Teams
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Устранение неполадок, связанных с получением сообщений и вызовов в устаревших системах
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56499af9534c3559cdfa3311a360caa60d06d3d7
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789524"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Проблемы с получением сообщений и вызовов в устаревших системах

У пользователей могут возникнуть проблемы с получением сообщений или звонков, если они используют более старые версии Teams или выполнили вход с другими приложениями.

## <a name="legacy-adu-setups"></a>Устаревшие настройки ADU

 Если пользователи выполнили вход на компьютере, подключенном к домену, и вы **не хотите, чтобы их имена предварительно добавлялись на экран входа в Teams**, администраторы могут настроить следующий раздел реестра Windows для отключения предварительного заполнения имени пользователя (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Пропуск или игнорирование предварительного добавления имен пользователей, оканчивающихся на ".local" или ".corp", включено по умолчанию, поэтому вам не нужно настраивать раздел реестра для их отключения.

[Дополнительные сведения см. в статье "Вход в Microsoft Teams](sign-in-teams.md) с использованием современной проверки подлинности".

## <a name="skype-token-revocation"></a>Отзыв токена Skype

При изменении или сбросе пароля старые клиенты не будут получать сообщения и вызовы в течение часа. Чтобы устранить эту проблему, перезапустите приложение или перейдите на более новые клиенты.


## <a name="related-topics"></a>Статьи по теме

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)