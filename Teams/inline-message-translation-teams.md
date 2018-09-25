---
title: Использование встроенного перевода сообщений в Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
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
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016839"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Использование встроенного перевода сообщений в Microsoft Teams 
=================================================

Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.

Встроенный перевод сообщений предназначенных для развертывания по умолчанию для вашей организации. Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр с помощью PowerShell. В настоящее время этот параметр недоступен в группами Майкрософт и Скайп по центру администрирования бизнес, но скоро будет.

> [!NOTE]
>Этот выпуск исключен из подписок на Office 365 в наших средах облака сообщества для государственных организаций Office 365 и Office 365 Germany. 

## <a name="enable-by-using-powershell"></a>Включение с помощью PowerShell

Вы можете включить встроенный перевод сообщений с помощью политики обмена сообщениями. 

1. Включите эту политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. Политики занимает несколько минут, чтобы применить. Пользователям необходимо выйти и снова выполнить вход в группы.

## <a name="enable-by-using-the-teams-admin-center"></a>Включение с помощью Центра администрирования Teams

Скоро появится возможность включить встроенный перевод сообщений с помощью Центра администрирования Teams.

> [!NOTE]
>Перевод строго со стороны клиента и имеет не влияет на содержимое, записываемые в записях соответствия требованиям. Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).