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
ms.openlocfilehash: 2afc1d0374333fdbb0bec9246d04224c6a82f032
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532704"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="6cafb-103">Использование встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cafb-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="6cafb-104">Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cafb-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="6cafb-105">Встроенный перевод сообщений развертывается для вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6cafb-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="6cafb-106">Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="6cafb-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="6cafb-107">В этом выгрузка данных исключается из подписки Office 365 в нашем в среде Office 365 облако сообщества госучреждений и Германия Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cafb-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="6cafb-108">Включить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cafb-108">Enable by using PowerShell</span></span>

<span data-ttu-id="6cafb-109">Встроенное средство перевода сообщения можно включить с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="6cafb-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="6cafb-110">Включите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="6cafb-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="6cafb-111">Политики занимает несколько минут, чтобы применить.</span><span class="sxs-lookup"><span data-stu-id="6cafb-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="6cafb-112">Пользователям необходимо выйти и снова выполнить вход в группы.</span><span class="sxs-lookup"><span data-stu-id="6cafb-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="6cafb-113">Включить с помощью команды Microsoft & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="6cafb-113">Enable by using the Microsoft Teams & Skype for Business Admin Center</span></span>

<span data-ttu-id="6cafb-114">В **группами Майкрософт & Скайп по центру администрирования бизнеса**выберите **Политики обмена сообщениями** в левой панели, затем либо создать новую политику или изменить существующую политику и установите флажок **Разрешить пользователям включать поддержку для перевода сообщений** для \*\*на \*\*.</span><span class="sxs-lookup"><span data-stu-id="6cafb-114">In the **Microsoft Teams & Skype for Business Admin Center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="6cafb-115">Перевод выполняется службой и доставлено клиенту не оказывает влияния на содержимое, записываемые в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6cafb-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="6cafb-116">Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="6cafb-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>