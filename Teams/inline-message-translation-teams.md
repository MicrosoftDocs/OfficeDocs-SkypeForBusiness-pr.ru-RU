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
ms.openlocfilehash: 0fabdbde6f8307694457d4861d67c6ed2eb22ac1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905811"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Включение встроенного перевода сообщений в Microsoft Teams 
=================================================

Преобразование встроенных сообщений — это новая функция Microsoft Teams, которая позволяет пользователям переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , заданный их личными языковыми параметрами для Office 365.

Встроенный перевод сообщений развертывается для вашей организации по умолчанию. Если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams, необходимо включить этот параметр.

> [!NOTE]
>Этот выпуск исключен из подписок на Office 365 в облаке сообщества Office 365 для государственных организаций и Office 365 для Германии.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Включение встроенного перевода сообщений с помощью PowerShell

Чтобы включить перевод встроенных сообщений, можно использовать политику сообщений.

Включите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . Для применения политики требуется несколько минут. Пользователям может потребоваться выйти из Teams и войти в нее снова.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Включение встроенного перевода сообщений с помощью центра администрирования Microsoft Teams

В **центре администрирования Microsoft Teams**выберите **политики обмена сообщениями** в левой области навигации, а затем создайте новую политику или измените существующую, а затем установите для параметра **Разрешить пользователей перевод сообщений** **на вкл**.

> [!NOTE]
> Служба выполняет перевод и доставляет его клиенту без воздействия на содержимое, захваченное в записях соответствия требованиям. Чтобы узнать больше о переводе, ознакомьтесь со статьей [Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).