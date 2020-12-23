---
title: Включить перевод в текстовом сообщении
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как включить в Microsoft Teams возможность перевода с помощью Центра администрирования Microsoft Teams или PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395388"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Отключение перевода в текстовом сообщении в Microsoft Teams
=================================================

Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.

По умолчанию для организации в организации перевод сообщений в тексте. Вам не нужно вносить изменения, если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams.

> [!NOTE]
>Эта раздатка исключается из подписок на Office 365 в среде Сообщества государственных организаций Office 365 и Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Отключение перевода в текстовом сообщении с помощью PowerShell

Вы можете использовать политику обмена сообщениями, чтобы отключить перевод в текстовом сообщении.

Отключите политику с помощью [cmdlet Set-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Применение политики займет несколько минут. Пользователям может потребоваться выйти и снова войти в Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Отключение перевода в текстовом сообщении с помощью Центра администрирования Microsoft Teams

В Центре **администрирования** Microsoft  Teams выберите "Политики обмена сообщениями" в области навигации слева, а затем создайте новую политику или отредактйте существующую политику и установите для параметра **"Перевести** сообщения" параметр **"Отключено".**

> [!NOTE]
> Служба переводит его и передает клиенту, не влияя на содержимое, записанное в записях соответствия требованиям. Подробнее о переводе см. в [подмносях "Что такое Microsoft Translator?".](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
