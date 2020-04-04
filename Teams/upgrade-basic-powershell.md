---
title: Основное обновление оболочки PowerShell | Microsoft Teams | Предоставление политики взаимодействия по обновлению
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Stopgap для перехода на Teams, если центр администрирования не горит в вашем клиенте.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84ecfb8b9286b749e5b1bf6d34cdf0c8c8fd4113
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139678"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="5b056-103">Обновление пользователей из Skype для бизнеса Online в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5b056-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="5b056-104">Команды, описанные в этой статье, предназначены для использования в качестве части базового контрольного списка [обновления](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="5b056-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="5b056-105">Благодаря техническим аспектам миграции ваши пользователи получат уведомление о том, что Skype для бизнеса будет обновлен до Teams, а затем перейдет в режим " **только для Team** ".</span><span class="sxs-lookup"><span data-stu-id="5b056-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="5b056-106">Эти действия можно выполнить с помощью удаленного сеанса Windows PowerShell в Skype для бизнеса или через центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5b056-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="5b056-107">Мы активно выстраиваете средства обновления в [центре администрирования Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md), и он должен быть доступен только в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="5b056-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="5b056-108">По мере их появления вы можете найти сведения о переносе пользователей с [помощью настройки сосуществования и обновления](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="5b056-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="5b056-109">Если вы готовы обновить уже сегодня, вы можете использовать команды [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) , указанные в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="5b056-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="5b056-110">Основные действия по обновлению #</span><span class="sxs-lookup"><span data-stu-id="5b056-110">Upgrade Basic step #</span></span> | <span data-ttu-id="5b056-111">Режиме</span><span class="sxs-lookup"><span data-stu-id="5b056-111">Mode</span></span> | <span data-ttu-id="5b056-112">Команда PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b056-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="5b056-113">5</span><span class="sxs-lookup"><span data-stu-id="5b056-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="5b056-114">О-ва + уведомление пользователей Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5b056-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="5b056-115">(Используйте эту команду, если в настоящее время пользователи находятся в режиме " **острова** " (по умолчанию)).</span><span class="sxs-lookup"><span data-stu-id="5b056-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="5b056-116">*(например, $SipAddress = "TestUser@contoso.com")*</span><span class="sxs-lookup"><span data-stu-id="5b056-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="5b056-117">5</span><span class="sxs-lookup"><span data-stu-id="5b056-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="5b056-118">Только Skype для бизнеса + уведомление пользователей Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5b056-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="5b056-119">(Используйте эту команду, если в настоящее время пользователи находятся в режиме " **только Skype для бизнеса** ").</span><span class="sxs-lookup"><span data-stu-id="5b056-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="5b056-120">7</span><span class="sxs-lookup"><span data-stu-id="5b056-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="5b056-121">Только для Teams</span><span class="sxs-lookup"><span data-stu-id="5b056-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
