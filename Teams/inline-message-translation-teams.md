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
description: Узнайте, как включить в текстовом Microsoft Teams с помощью Microsoft Teams или PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 719f97e72f099edb4d14c22ef9d5a3de0f787ea7411f42f1d777ea842bcc4e27
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339647"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Отключение перевода в текстовом сообщении Microsoft Teams

Перевод в текстовом сообщении Microsoft Teams, который позволяет пользователям переводить сообщения Teams на язык, заданный их личными языковыми настройками. [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)

Для организации по умолчанию в организации отобрален перевод сообщений в текстовом режиме. Вам не нужно вносить изменения, если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams клиента.

> [!NOTE]
>Эта разетка исключается из Office 365 подписок в Office 365 для государственных организаций Community и Office 365 Германии.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Отключение перевода в текстовом сообщении с помощью PowerShell

Вы можете использовать политику обмена сообщениями, чтобы отключить перевод в текстовом сообщении.

Отключите политику с помощью [cmdlet Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) Применение политики займет несколько минут. Пользователям может потребоваться выйти и снова войти в Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Отключение перевода Microsoft Teams в Центре администрирования

В центре **администрирования** Microsoft Teams выберите  Политики сообщений в области навигации слева, затем создайте новую  политику или отредактируете существующую политику и установите для параметра Перевод сообщений параметр **Выключить**.

> [!NOTE]
> Служба переводит его и передает клиенту, не влияя на содержимое, записанное в записях соответствия требованиям. Дополнительные информацию о переводе см. в [Переводчик Майкрософт?](/azure/cognitive-services/translator/translator-info-overview)