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
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="cb89f-103">Использование встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb89f-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="cb89f-104">Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb89f-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="cb89f-105">Встроенный перевод сообщений предназначенных для развертывания по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="cb89f-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="cb89f-106">Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb89f-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="cb89f-107">В настоящее время этот параметр недоступен в группами Майкрософт и Скайп по центру администрирования бизнес, но скоро будет.</span><span class="sxs-lookup"><span data-stu-id="cb89f-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="cb89f-108">Этот выпуск исключен из подписок на Office 365 в наших средах облака сообщества для государственных организаций Office 365 и Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="cb89f-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="cb89f-109">Включение с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb89f-109">Enable by using PowerShell</span></span>

<span data-ttu-id="cb89f-110">Вы можете включить встроенный перевод сообщений с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="cb89f-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="cb89f-111">Включите эту политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cb89f-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="cb89f-112">Политики занимает несколько минут, чтобы применить.</span><span class="sxs-lookup"><span data-stu-id="cb89f-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="cb89f-113">Пользователям необходимо выйти и снова выполнить вход в группы.</span><span class="sxs-lookup"><span data-stu-id="cb89f-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="cb89f-114">Включение с помощью Центра администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="cb89f-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="cb89f-115">Скоро появится возможность включить встроенный перевод сообщений с помощью Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="cb89f-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="cb89f-116">Перевод строго со стороны клиента и имеет не влияет на содержимое, записываемые в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cb89f-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="cb89f-117">Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="cb89f-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>