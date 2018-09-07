---
title: Использовать встроенный перевод сообщений в группах Майкрософт
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Priority
search.appverid: MET150
description: Узнайте, как использовать встроенный перевод в группами Майкрософт.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb7876d015fb736785fdaab99b1ed71b8e05b9dc
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855823"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Использовать встроенный перевод сообщений в группах Майкрософт 
=================================================

Встроенный перевод сообщение — это новая возможность группами Майкрософт, которая позволяет пользователям автоматически преобразовывать сообщения команды на [языка](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , указанного идентификатором личных языковых параметров для Office 365.

Встроенный перевод сообщений предназначенных для развертывания по умолчанию для вашей организации. Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр с помощью PowerShell. В настоящее время этот параметр недоступен в группами Майкрософт и Скайп по центру администрирования бизнес, но скоро будет.

> [!NOTE]
>В этом выгрузка данных исключается из подписки Office 365 в нашем в среде Office 365 облако сообщества госучреждений и Германия Office 365. 

## <a name="enable-by-using-powershell"></a>Включить с помощью PowerShell

Встроенное средство перевода сообщения можно включить с помощью политики обмена сообщениями. 

1. Включите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. Политики занимает несколько минут, чтобы применить. Пользователям необходимо выйти и снова выполнить вход в группы.

## <a name="enable-by-using-the-teams-admin-center"></a>Включить с помощью центра администрирования группы

Параметр, чтобы включить функцию преобразования встроенного сообщения с помощью центра администрирования группами в ближайшее время.

> [!NOTE]
>Перевод строго со стороны клиента и имеет не влияет на содержимое, записываемые в записях соответствия требованиям. Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).