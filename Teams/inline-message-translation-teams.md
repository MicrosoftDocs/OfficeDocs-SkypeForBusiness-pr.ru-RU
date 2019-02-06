---
title: Использование встроенного перевода сообщений в Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании встроенного перевода сообщений в Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 466160616adea80a2fcb6a3bfd035ca397d73754
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754428"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Использование встроенного перевода сообщений в Microsoft Teams 
=================================================

Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.

Встроенный перевод сообщений развертывается для вашей организации по умолчанию. Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр.

> [!NOTE]
>В этом выгрузка данных исключается из подписки Office 365 в нашем в среде Office 365 облако сообщества госучреждений и Германия Office 365.

## <a name="enable-by-using-powershell"></a>Включить с помощью PowerShell

Встроенное средство перевода сообщения можно включить с помощью политики обмена сообщениями.

1. Включите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. Политики занимает несколько минут, чтобы применить. Пользователям необходимо выйти и снова выполнить вход в группы.

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a>Включить с помощью центра администрирования группами Майкрософт

**Центр администрирования группами Майкрософт**выберите **Политики обмена сообщениями** в левой панели, затем либо создать новую политику или изменить существующую политику и установить для параметра **Разрешить пользователям включать поддержку для перевода сообщений** **на**.

> [!NOTE]
>Перевод выполняется службой и доставлено клиенту не оказывает влияния на содержимое, записываемые в записях соответствия требованиям. Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).