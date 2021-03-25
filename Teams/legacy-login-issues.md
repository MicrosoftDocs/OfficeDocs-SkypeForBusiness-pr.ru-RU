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
ms.openlocfilehash: 1c209d1acc83e63792722b00b63be5a6b9f3721a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120610"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Проблемы с получением сообщений и вызовов в устаревших системах
==============================================================

У пользователей могут возникнуть проблемы с получением сообщений или звонков, если они используют более старые версии Teams или вошли в другие приложения.

## <a name="legacy-adu-setups"></a>Устаревшие настройки ADU

 Если пользователи выполнили вход на компьютере, подключенном к домену, и вы **не хотите, чтобы их имена предварительно добавлялись на экран входа в Teams**, администраторы могут настроить следующий раздел реестра Windows для отключения предварительного заполнения имени пользователя (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Пропуск или игнорирование предварительного добавления имен пользователей, оканчивающихся на ".local" или ".corp", включено по умолчанию, поэтому вам не нужно настраивать раздел реестра для их отключения.

Дополнительные [сведения см. в документе "Вход в Microsoft Teams с использованием современной проверки](sign-in-teams.md) подлинности".

## <a name="skype-token-revocation"></a>Отзыв маркера Skype

При изменении или сбросе пароля старые клиенты не будут получать сообщения и звонки в течение часа. Чтобы устранить эту проблему, перезапустите приложение или переходить на более новые клиенты.


## <a name="related-topics"></a>Статьи по теме

[Устранение неполадок Teams](/MicrosoftTeams/troubleshoot/teams)