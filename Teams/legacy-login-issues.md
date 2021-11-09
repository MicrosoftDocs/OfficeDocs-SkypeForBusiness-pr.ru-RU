---
title: Проблемы с получением сообщений и звонков в устаревших системах в Teams
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Устранение неполадок, связанных с получением сообщений и звонков в устаревших системах
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 69a3f070b247507e0d22535179353860434e94ad
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857146"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Проблемы с получением сообщений и звонков в устаревших системах

У пользователей могут возникнуть проблемы с получением сообщений или звонков, если они используют более старые версии Teams или вошли в другие приложения.

## <a name="legacy-adu-setups"></a>Устаревшие настройки ADU

 Если пользователи выполнили вход на компьютере, подключенном к домену, и вы **не хотите, чтобы их имена предварительно добавлялись на экран входа в Teams**, администраторы могут настроить следующий раздел реестра Windows для отключения предварительного заполнения имени пользователя (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Пропуск или игнорирование предварительного добавления имен пользователей, оканчивающихся на ".local" или ".corp", включено по умолчанию, поэтому вам не нужно настраивать раздел реестра для их отключения.

Дополнительные [сведения см. в Microsoft Teams с помощью современной](sign-in-teams.md) проверки подлинности.

## <a name="skype-token-revocation"></a>Skype отзыва маркера

При изменении или сбросе пароля старые клиенты не будут получать сообщения и звонки в течение часа. Чтобы устранить эту проблему, перезапустите приложение или перезапустите новые клиенты.


## <a name="related-topics"></a>Статьи по теме

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)