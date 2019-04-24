---
title: Использование встроенного перевода сообщений в Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании встроенного перевода сообщений в Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58e6fb04dd015e939125b75d604fe9692a32c0e2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222327"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="7d055-103">Использование встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d055-103">Use inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="7d055-104">Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d055-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="7d055-105">Встроенный перевод сообщений развертывается для вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d055-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="7d055-106">Если требуется разрешить пользователям использовать этот компонент в клиенте групп, необходимо включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="7d055-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="7d055-107">В этом выгрузка данных исключается из подписки Office 365 в нашем в среде Office 365 облако сообщества госучреждений и Германия Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d055-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="enable-by-using-powershell"></a><span data-ttu-id="7d055-108">Включить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d055-108">Enable by using PowerShell</span></span>

<span data-ttu-id="7d055-109">Встроенное средство перевода сообщения можно включить с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7d055-109">You can turn on the inline message translation feature by using the Messaging Policy.</span></span>

1. <span data-ttu-id="7d055-110">Включите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7d055-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span>
2. <span data-ttu-id="7d055-111">Политики занимает несколько минут, чтобы применить.</span><span class="sxs-lookup"><span data-stu-id="7d055-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="7d055-112">Пользователям необходимо выйти и снова выполнить вход в группы.</span><span class="sxs-lookup"><span data-stu-id="7d055-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="enable-by-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="7d055-113">Включить с помощью центра администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7d055-113">Enable by using the Microsoft Teams admin center</span></span>

<span data-ttu-id="7d055-114">**Центр администрирования группами Майкрософт**выберите **Политики обмена сообщениями** в левой панели, затем либо создать новую политику или изменить существующую политику и установить для параметра **Разрешить пользователям включать поддержку для перевода сообщений** **на**.</span><span class="sxs-lookup"><span data-stu-id="7d055-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left-hand bar, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
><span data-ttu-id="7d055-115">Перевод выполняется службой и доставлено клиенту не оказывает влияния на содержимое, записываемые в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7d055-115">Translation is done by the service and delivered to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="7d055-116">Чтобы узнать больше о перевода, обратитесь к разделу [возможности Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="7d055-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>