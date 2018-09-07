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
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="0e1c4-103">Использовать встроенный перевод сообщений в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0e1c4-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="0e1c4-104">Встроенный перевод сообщение — это новая возможность группами Майкрософт, которая позволяет пользователям автоматически преобразовывать сообщения команды на [языка](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , указанного идентификатором личных языковых параметров для Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="0e1c4-105">Встроенный перевод сообщений предназначенных для развертывания по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="0e1c4-106">Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="0e1c4-107">В настоящее время этот параметр недоступен в группами Майкрософт и Скайп по центру администрирования бизнес, но скоро будет.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="0e1c4-108">В этом выгрузка данных исключается из подписки Office 365 в нашем в среде Office 365 облако сообщества госучреждений и Германия Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="0e1c4-109">Включить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e1c4-109">Enable by using PowerShell</span></span>

<span data-ttu-id="0e1c4-110">Встроенное средство перевода сообщения можно включить с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="0e1c4-111">Включите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0e1c4-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="0e1c4-112">Политики занимает несколько минут, чтобы применить.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="0e1c4-113">Пользователям необходимо выйти и снова выполнить вход в группы.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="0e1c4-114">Включить с помощью центра администрирования группы</span><span class="sxs-lookup"><span data-stu-id="0e1c4-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="0e1c4-115">Параметр, чтобы включить функцию преобразования встроенного сообщения с помощью центра администрирования группами в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="0e1c4-116">Перевод строго со стороны клиента и имеет не влияет на содержимое, записываемые в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0e1c4-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="0e1c4-117">Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="0e1c4-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>