---
title: Основное обновление оболочки PowerShell | Microsoft Teams | Предоставление политики взаимодействия по обновлению
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Стопгап для перехода на Teams, если центр администрирования не горит в вашем клиенте
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 945422f6bb61fca8d2b17379a7c9bf4695e7dd09
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236545"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="32699-103">Обновление пользователей из Skype для бизнеса Online в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32699-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="32699-104">Команды, описанные в этой статье, предназначены для использования в качестве части базового контрольного списка [обновления](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="32699-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="32699-105">Благодаря техническим аспектам миграции ваши пользователи получат уведомление о том, что Skype для бизнеса будет обновлен до Teams, а затем перейдет в режим " **только для Team** ".</span><span class="sxs-lookup"><span data-stu-id="32699-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="32699-106">Эти действия можно выполнить с помощью удаленного сеанса Windows PowerShell в Skype для бизнеса или через центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="32699-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="32699-107">Мы активно выстраиваете средства обновления в [центре администрирования Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md), и он должен быть доступен только в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="32699-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="32699-108">По мере их появления вы можете найти сведения о переносе пользователей с [помощью настройки сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="32699-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="32699-109">Если вы готовы обновить уже сегодня, вы можете использовать команды [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) , указанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="32699-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="32699-110">Основные действия по обновлению #</span><span class="sxs-lookup"><span data-stu-id="32699-110">Upgrade Basic step #</span></span> | <span data-ttu-id="32699-111">Режиме</span><span class="sxs-lookup"><span data-stu-id="32699-111">Mode</span></span> | <span data-ttu-id="32699-112">Команда PowerShell</span><span class="sxs-lookup"><span data-stu-id="32699-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="32699-113">5</span><span class="sxs-lookup"><span data-stu-id="32699-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="32699-114">О-ва + уведомление пользователей Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="32699-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="32699-115">(Используйте эту команду, если в настоящее время пользователи находятся в режиме " **острова** " (по умолчанию)).</span><span class="sxs-lookup"><span data-stu-id="32699-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="32699-116">*(например, $SipAddress = "TestUser@contoso.com")*</span><span class="sxs-lookup"><span data-stu-id="32699-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="32699-117">5</span><span class="sxs-lookup"><span data-stu-id="32699-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="32699-118">Только Skype для бизнеса + уведомление пользователей Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="32699-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="32699-119">(Используйте эту команду, если в настоящее время пользователи находятся в режиме " **только Skype для бизнеса** ").</span><span class="sxs-lookup"><span data-stu-id="32699-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="32699-120">7</span><span class="sxs-lookup"><span data-stu-id="32699-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="32699-121">Только для Teams</span><span class="sxs-lookup"><span data-stu-id="32699-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
