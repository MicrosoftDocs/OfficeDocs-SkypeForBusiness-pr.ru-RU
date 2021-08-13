---
title: Проблемы с получением сообщений и звонков в устаревших системах Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 4626f7d675f5b6d5f4899f9b0f1cd6d8eb81776de383c3a0c573e2fd78967cb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348982"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Проблемы с получением сообщений и звонков в устаревших системах
==============================================================

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