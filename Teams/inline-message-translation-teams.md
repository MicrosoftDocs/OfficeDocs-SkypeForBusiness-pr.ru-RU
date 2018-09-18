---
title: Использование встроенного перевода сообщений в Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании встроенного перевода сообщений в Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882910"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Использование встроенного перевода сообщений в Microsoft Teams 
=================================================

Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.

Встроенный перевод сообщений развертывается для вашей организации по умолчанию. Чтобы разрешить пользователям использовать эту функцию в клиенте Teams, нужно включить эту настройку с помощью PowerShell. Сейчас этот параметр недоступен в Microsoft Teams и Центре администрирования Skype для бизнеса, но скоро он там появится.

> [!NOTE]
>Этот выпуск исключен из подписок на Office 365 в наших средах облака сообщества для государственных организаций Office 365 и Office 365 Germany. 

## <a name="enable-by-using-powershell"></a>Включение с помощью PowerShell

Вы можете включить встроенный перевод сообщений с помощью политики обмена сообщениями. 

1. Включите эту политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. Ее применение занимает несколько минут. Возможно, пользователям потребуется выйти из Teams и снова войти в него.

## <a name="enable-by-using-the-teams-admin-center"></a>Включение с помощью Центра администрирования Teams

Скоро появится возможность включить встроенный перевод сообщений с помощью Центра администрирования Teams.

> [!NOTE]
>Перевод осуществляется исключительно на стороне клиента и не влияет на содержимое, фиксируемое в целях обеспечения соответствия. Дополнительные сведения о переводе см. в статье [Что такое Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).