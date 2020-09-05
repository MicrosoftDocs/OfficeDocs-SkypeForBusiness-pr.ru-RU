---
title: Включение встроенного перевода сообщений
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
description: Сведения о включении встроенного перевода в Microsoft Teams с помощью центра администрирования Microsoft Teams или PowerShell.
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
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Отключение перевода встроенных сообщений в Microsoft Teams
=================================================

Преобразование встроенных сообщений — это функция Microsoft Teams, которая позволяет пользователям переводить сообщения группы в [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , заданный их личными языковыми параметрами.

Перевод встроенных сообщений выполняется по умолчанию для вашей организации. Если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams, вам не нужно вносить изменения.

> [!NOTE]
>Этот выпуск исключен из подписок на Office 365 в облаке сообщества Office 365 для государственных организаций и Office 365 для Германии.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Отключение перевода встроенных сообщений с помощью PowerShell

Вы можете отключить перевод встроенных сообщений с помощью политики обмена сообщениями.

Отключите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . Для применения политики требуется несколько минут. Пользователям может потребоваться выйти из Teams и войти в нее снова.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Отключение перевода встроенных сообщений с помощью центра администрирования Microsoft Teams

В **центре администрирования Microsoft Teams**выберите **политики обмена сообщениями** в левой области навигации, а затем создайте новую политику или измените существующую, а затем установите для параметра **перевод сообщений** значение **отключено**.

> [!NOTE]
> Служба выполняет перевод и доставляет его клиенту без воздействия на содержимое, захваченное в записях соответствия требованиям. Чтобы узнать больше о переводе, ознакомьтесь со статьей [Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
