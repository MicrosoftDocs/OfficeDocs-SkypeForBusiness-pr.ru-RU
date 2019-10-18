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
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Сведения об использовании встроенного перевода сообщений в Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f6c6a2eca313b70640dbf61a87c6c5742ea318
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570739"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="9820a-103">Включение встроенного перевода сообщений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9820a-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="9820a-104">Преобразование встроенных сообщений — это новая функция Microsoft Teams, которая позволяет пользователям переводить сообщения Teams на [язык](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) , заданный их личными языковыми параметрами для Office 365.</span><span class="sxs-lookup"><span data-stu-id="9820a-104">Inline message translation is a new Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="9820a-105">Встроенный перевод сообщений развертывается для вашей организации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9820a-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="9820a-106">Если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams, необходимо включить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="9820a-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="9820a-107">Этот выпуск исключен из подписок на Office 365 в облаке сообщества Office 365 для государственных организаций и Office 365 для Германии.</span><span class="sxs-lookup"><span data-stu-id="9820a-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="9820a-108">Включение встроенного перевода сообщений с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9820a-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="9820a-109">Чтобы включить перевод встроенных сообщений, можно использовать политику сообщений.</span><span class="sxs-lookup"><span data-stu-id="9820a-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="9820a-110">Включите политику с помощью командлета [Set-кстеамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9820a-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="9820a-111">Для применения политики требуется несколько минут.</span><span class="sxs-lookup"><span data-stu-id="9820a-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="9820a-112">Пользователям может потребоваться выйти из Teams и войти в нее снова.</span><span class="sxs-lookup"><span data-stu-id="9820a-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="9820a-113">Включение встроенного перевода сообщений с помощью центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9820a-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="9820a-114">В **центре администрирования Microsoft Teams**выберите **политики обмена сообщениями** в левой области навигации, а затем создайте новую политику или измените существующую, а затем установите для параметра **Разрешить пользователей перевод сообщений** **на вкл**.</span><span class="sxs-lookup"><span data-stu-id="9820a-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="9820a-115">Служба выполняет перевод и доставляет его клиенту без воздействия на содержимое, захваченное в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9820a-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="9820a-116">Чтобы узнать больше о переводе, ознакомьтесь со статьей [Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span><span class="sxs-lookup"><span data-stu-id="9820a-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>