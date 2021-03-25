---
title: PowerShell для базового обновления| Microsoft Teams| Политика предоставления обновления для interop
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о том, как остановить обновление до Microsoft Teams, если Центр администрирования не загорелся в вашем клиенте.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120548"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="0e195-103">Переход с Skype для бизнеса Online на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e195-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="0e195-104">Описанные в этой статье команды предназначены для использования [](./upgrade-start-here.md) в контрольном списке "Базовая обновление".</span><span class="sxs-lookup"><span data-stu-id="0e195-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="0e195-105">Аспекты технической миграции при обновлении необходимо уведомить пользователей о том, что Skype для бизнеса будет обновляться до Teams, а затем перенано в режим **только Teams.**</span><span class="sxs-lookup"><span data-stu-id="0e195-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="0e195-106">Эти действия можно выполнить в удаленном сеансе удаленного Windows PowerShell Skype для Windows PowerShell центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0e195-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="0e195-107">Мы активно развертываем средства обновления в Центре администрирования [Microsoft Teams,](manage-teams-skypeforbusiness-admin-center.md)и они должны стать доступны в ближайшее время в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="0e195-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="0e195-108">Как только она станет доступна, сведения о переносе пользователей можно найти в параметрах сосуществования и [обновления.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0e195-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="0e195-109">Если вы готовы к обновлению, воспользуйтесь командами [PowerShell,](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) перечисленными в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="0e195-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="0e195-110">Шаг "Основные обновления" #</span><span class="sxs-lookup"><span data-stu-id="0e195-110">Upgrade Basic step #</span></span> | <span data-ttu-id="0e195-111">Режим</span><span class="sxs-lookup"><span data-stu-id="0e195-111">Mode</span></span> | <span data-ttu-id="0e195-112">Команда PowerShell</span><span class="sxs-lookup"><span data-stu-id="0e195-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="0e195-113">5</span><span class="sxs-lookup"><span data-stu-id="0e195-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="0e195-114">Islands + Уведомить пользователя Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e195-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="0e195-115">(Используйте эту команду, если пользователи находятся **в** режиме "Острова" (по умолчанию))</span><span class="sxs-lookup"><span data-stu-id="0e195-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="0e195-116">*(Например, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="0e195-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="0e195-117">5</span><span class="sxs-lookup"><span data-stu-id="0e195-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="0e195-118">Только Skype для бизнеса + Уведомление пользователя Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e195-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="0e195-119">(Используйте эту команду, если пользователи в настоящее время находятся в **режиме только Skype для** бизнеса)</span><span class="sxs-lookup"><span data-stu-id="0e195-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="0e195-120">7</span><span class="sxs-lookup"><span data-stu-id="0e195-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="0e195-121">Только в Teams</span><span class="sxs-lookup"><span data-stu-id="0e195-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |