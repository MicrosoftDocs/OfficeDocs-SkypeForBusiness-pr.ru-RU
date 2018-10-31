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
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851570"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="1b72f-103">Использование встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1b72f-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="1b72f-104">Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b72f-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="1b72f-105">Встроенный перевод сообщений развертывается для вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b72f-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="1b72f-106">Чтобы разрешить пользователям использовать эту функцию в клиенте Teams, нужно включить эту настройку с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b72f-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="1b72f-107">Сейчас этот параметр недоступен в Microsoft Teams и Центре администрирования Skype для бизнеса, но скоро он там появится.</span><span class="sxs-lookup"><span data-stu-id="1b72f-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="1b72f-108">Этот выпуск исключен из подписок на Office 365 в наших средах облака сообщества для государственных организаций Office 365 и Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="1b72f-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="1b72f-109">Включение с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b72f-109">Enable by using PowerShell</span></span>

<span data-ttu-id="1b72f-110">Вы можете включить встроенный перевод сообщений с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1b72f-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="1b72f-111">Включите эту политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b72f-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="1b72f-112">Ее применение занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="1b72f-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="1b72f-113">Возможно, пользователям потребуется выйти из Teams и снова войти в него.</span><span class="sxs-lookup"><span data-stu-id="1b72f-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="1b72f-114">Включить с помощью команды Microsoft & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="1b72f-114">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="1b72f-115">Параметр, чтобы включить встроенное средство преобразования сообщений, с помощью групп Майкрософт & Скайп по центру администрирования бизнес в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="1b72f-115">The option to turn on the inline message translation feature using the Microsoft Teams & Skype for Business Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="1b72f-116">Перевод осуществляется исключительно на стороне клиента и не влияет на содержимое, фиксируемое в целях обеспечения соответствия.</span><span class="sxs-lookup"><span data-stu-id="1b72f-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="1b72f-117">Дополнительные сведения о переводе см. в статье [Что такое Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="1b72f-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>