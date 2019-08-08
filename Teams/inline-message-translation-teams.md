---
title: Включение встроенного перевода сообщений в Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
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
ms.openlocfilehash: 8b6da80dda90c57a55a75c885b42bc08a824b613
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245353"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="72e2b-103">Включение встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72e2b-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="72e2b-104">Встроенный перевод сообщений — это новая функция Microsoft Teams, позволяющая пользователям автоматически переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194), указанный в персональных настройках языка для Office 365.</span><span class="sxs-lookup"><span data-stu-id="72e2b-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="72e2b-105">Встроенный перевод сообщений развертывается для вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72e2b-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="72e2b-106">Если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams, необходимо включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="72e2b-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="72e2b-107">Этот выпуск исключен из подписок на Office 365 в облаке сообщества Office 365 для государственных организаций и Office 365 для Германии.</span><span class="sxs-lookup"><span data-stu-id="72e2b-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="72e2b-108">Включение встроенного перевода сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="72e2b-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="72e2b-109">Чтобы включить перевод встроенных сообщений, можно использовать политику сообщений.</span><span class="sxs-lookup"><span data-stu-id="72e2b-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="72e2b-110">Включите политику с помощью командлета [Set-кстеамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="72e2b-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="72e2b-111">Для применения политики требуется несколько минут.</span><span class="sxs-lookup"><span data-stu-id="72e2b-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="72e2b-112">Пользователям может потребоваться выйти из Teams и войти в нее снова.</span><span class="sxs-lookup"><span data-stu-id="72e2b-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="72e2b-113">Включение встроенного перевода сообщений с помощью центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="72e2b-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="72e2b-114">В **центре администрирования Microsoft Teams**выберите **политики обмена сообщениями** в левой области навигации, а затем создайте новую политику или измените существующую, а затем установите для параметра **Разрешить пользователей перевод сообщений** **на вкл**.</span><span class="sxs-lookup"><span data-stu-id="72e2b-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="72e2b-115">Служба выполняет перевод и доставляет его клиенту без воздействия на содержимое, захваченное в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="72e2b-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="72e2b-116">Чтобы узнать больше о переводе, ознакомьтесь со статьей [Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="72e2b-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>