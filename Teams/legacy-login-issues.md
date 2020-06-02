---
title: Проблемы с получением сообщений и звонков на старые системы в Teams
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
description: Устранение неполадок, связанных с получением сообщений и звонков в старых системах
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489168"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Проблемы с получением сообщений и звонков в устаревших системах
==============================================================

Пользователи могут столкнуться с проблемами при получении сообщений или звонков, если они используют старые версии Teams или вошли в систему с другими приложениями.

## <a name="legacy-adu-setups"></a>Устаревшие настройки ADU

 Если пользователи выполнили вход на компьютере, подключенном к домену, и вы **не хотите, чтобы их имена предварительно добавлялись на экран входа в Teams**, администраторы могут настроить следующий раздел реестра Windows для отключения предварительного заполнения имени пользователя (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Пропуск или игнорирование предварительного добавления имен пользователей, оканчивающихся на ".local" или ".corp", включено по умолчанию, поэтому вам не нужно настраивать раздел реестра для их отключения.

Дополнительные сведения можно найти в разделе [Вход в Microsoft Teams с использованием современной проверки подлинности](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Отзыв маркеров Skype

При изменении или сбросе пароля старые клиенты не смогут получать сообщения и звонки в течение часа. Чтобы устранить эту проблему, перезапустите приложение или перейдите к новым клиентам.
