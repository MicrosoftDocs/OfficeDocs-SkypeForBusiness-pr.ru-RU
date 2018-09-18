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
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="e676c-103">Использование встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e676c-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="e676c-104">Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.</span><span class="sxs-lookup"><span data-stu-id="e676c-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="e676c-105">Встроенный перевод сообщений развертывается для вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e676c-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="e676c-106">Чтобы разрешить пользователям использовать эту функцию в клиенте Teams, нужно включить эту настройку с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e676c-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on by using PowerShell.</span></span> <span data-ttu-id="e676c-107">Сейчас этот параметр недоступен в Microsoft Teams и Центре администрирования Skype для бизнеса, но скоро он там появится.</span><span class="sxs-lookup"><span data-stu-id="e676c-107">Currently, this option is not available in the Microsoft Teams and Skype for Business Admin Center, but will be soon.</span></span>

> [!NOTE]
><span data-ttu-id="e676c-108">Этот выпуск исключен из подписок на Office 365 в наших средах облака сообщества для государственных организаций Office 365 и Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="e676c-108">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span> 

## <a name="enable-by-using-powershell"></a><span data-ttu-id="e676c-109">Включение с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e676c-109">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="e676c-110">Вы можете включить встроенный перевод сообщений с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e676c-110">You can turn on the inline message translation feature by using the Messaging Policy.</span></span> 

1. <span data-ttu-id="e676c-111">Включите эту политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e676c-111">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="e676c-112">Ее применение занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e676c-112">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="e676c-113">Возможно, пользователям потребуется выйти из Teams и снова войти в него.</span><span class="sxs-lookup"><span data-stu-id="e676c-113">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-teams-admin-center"></a><span data-ttu-id="e676c-114">Включение с помощью Центра администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="e676c-114">Enable by using the Teams Admin Center</span></span>

<span data-ttu-id="e676c-115">Скоро появится возможность включить встроенный перевод сообщений с помощью Центра администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="e676c-115">The option to turn on the inline message translation feature by using the Teams Admin Center is coming soon.</span></span>

> [!NOTE]
><span data-ttu-id="e676c-116">Перевод осуществляется исключительно на стороне клиента и не влияет на содержимое, фиксируемое в целях обеспечения соответствия.</span><span class="sxs-lookup"><span data-stu-id="e676c-116">Translation is strictly client-side and has no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="e676c-117">Дополнительные сведения о переводе см. в статье [Что такое Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="e676c-117">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>