---
title: Включить перевод в текстовом сообщении
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
description: Узнайте, как включить в текстовом Microsoft Teams с помощью Microsoft Teams или PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78282b464dd1d9cb25c5d4d2b338c74a2c91d374
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855928"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="1f118-103">Отключение перевода в текстовом сообщении в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f118-103">Turn off inline message translation in Microsoft Teams</span></span>

<span data-ttu-id="1f118-104">Перевод в текстовом сообщении Microsoft Teams, который позволяет пользователям переводить сообщения Teams на язык, заданный их личными языковыми настройками. [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194)</span><span class="sxs-lookup"><span data-stu-id="1f118-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="1f118-105">Для организации по умолчанию в организации отобрален перевод сообщений в текстовом режиме.</span><span class="sxs-lookup"><span data-stu-id="1f118-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="1f118-106">Вам не нужно вносить изменения, если вы хотите разрешить пользователям использовать эту функцию в клиенте Teams клиента.</span><span class="sxs-lookup"><span data-stu-id="1f118-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="1f118-107">Эта разетка исключается из Office 365 подписок в Office 365 для государственных организаций Community и Office 365 Германии.</span><span class="sxs-lookup"><span data-stu-id="1f118-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="1f118-108">Отключение перевода в текстовом сообщении с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f118-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="1f118-109">Вы можете использовать политику обмена сообщениями, чтобы отключить перевод в текстовом сообщении.</span><span class="sxs-lookup"><span data-stu-id="1f118-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="1f118-110">Отключите политику с помощью [cmdlet Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1f118-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="1f118-111">Применение политики займет несколько минут.</span><span class="sxs-lookup"><span data-stu-id="1f118-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="1f118-112">Пользователям может потребоваться выйти и снова войти в Teams.</span><span class="sxs-lookup"><span data-stu-id="1f118-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="1f118-113">Отключение перевода Microsoft Teams в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="1f118-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="1f118-114">В центре **администрирования** Microsoft Teams выберите  Политики сообщений в области навигации слева, затем создайте новую  политику или отредактируете существующую политику и установите для параметра Перевод сообщений параметр **Выключить**.</span><span class="sxs-lookup"><span data-stu-id="1f118-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="1f118-115">Служба переводит его и передает клиенту, не влияя на содержимое, записанное в записях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1f118-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="1f118-116">Дополнительные информацию о переводе см. в этой [Переводчик?](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="1f118-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>