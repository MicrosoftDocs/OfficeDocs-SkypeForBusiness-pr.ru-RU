---
title: Включение встроенного перевода сообщений
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Сведения о включении встроенного перевода в Microsoft Teams с помощью центра администрирования Microsoft Teams или PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395388"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="4a399-103">Отключение перевода встроенных сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a399-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="4a399-104">Преобразование встроенных сообщений — это функция Microsoft Teams, которая позволяет пользователям переводить сообщения группы в [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , заданный их личными языковыми параметрами.</span><span class="sxs-lookup"><span data-stu-id="4a399-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="4a399-105">Перевод встроенных сообщений выполняется по умолчанию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4a399-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="4a399-106">Если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams, вам не нужно вносить изменения.</span><span class="sxs-lookup"><span data-stu-id="4a399-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="4a399-107">Этот выпуск исключен из подписок на Office 365 в облаке сообщества Office 365 для государственных организаций и Office 365 для Германии.</span><span class="sxs-lookup"><span data-stu-id="4a399-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="4a399-108">Отключение перевода встроенных сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a399-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="4a399-109">Вы можете отключить перевод встроенных сообщений с помощью политики обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="4a399-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="4a399-110">Отключите политику с помощью командлета [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4a399-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4a399-111">Для применения политики требуется несколько минут.</span><span class="sxs-lookup"><span data-stu-id="4a399-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="4a399-112">Пользователям может потребоваться выйти из Teams и войти в нее снова.</span><span class="sxs-lookup"><span data-stu-id="4a399-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="4a399-113">Отключение перевода встроенных сообщений с помощью центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a399-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="4a399-114">В **центре администрирования Microsoft Teams**выберите **политики обмена сообщениями** в левой области навигации, а затем создайте новую политику или измените существующую, а затем установите для параметра **перевод сообщений** значение **отключено**.</span><span class="sxs-lookup"><span data-stu-id="4a399-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="4a399-115">Служба выполняет перевод и доставляет его клиенту без воздействия на содержимое, захваченное в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="4a399-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="4a399-116">Чтобы узнать больше о переводе, ознакомьтесь со статьей [Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="4a399-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
