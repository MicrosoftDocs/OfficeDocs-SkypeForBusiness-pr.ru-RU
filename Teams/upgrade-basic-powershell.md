---
title: Базовая обновлению PowerShell | Группами Майкрософт | Предоставление обновления политики взаимодействия (en)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Временное для обновления до групп, если не включен в центр администрирования клиента
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 281938456c4fca695b2254e7cf6e50078bb32c80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920434"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="afd76-103">Обновление пользователей с Скайп для бизнеса в Интернет для групп Майкрософт</span><span class="sxs-lookup"><span data-stu-id="afd76-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="afd76-104">Команды, приведенные в этой статье предназначены для использования в качестве части [Обновления базовой](https://aka.ms/UpgradeBasic) контрольного списка.</span><span class="sxs-lookup"><span data-stu-id="afd76-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="afd76-105">Технические миграции аспектов обновления связаны уведомления пользователей, что Скайп для бизнеса будет обновления до групп и перемещая их в режим **только для групп** .</span><span class="sxs-lookup"><span data-stu-id="afd76-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="afd76-106">Эти действия можно сделать с помощью Скайп для бизнеса удаленного сеанса Windows PowerShell или с помощью центра администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="afd76-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="afd76-107">Мы активно выполняется развертывание произвести обновление, создание в [Центр администрирования группами Майкрософт](manage-teams-skypeforbusiness-admin-center.md), и он должен быть доступен только на вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="afd76-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="afd76-108">Как только доступен, можно найти сведения о миграции пользователей в [параметр вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="afd76-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="afd76-109">Если вы будете готовы к обновлению сегодня, можно использовать команды [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) , перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="afd76-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="afd76-110">Обновление базовой шаг #</span><span class="sxs-lookup"><span data-stu-id="afd76-110">Upgrade Basic step #</span></span> | <span data-ttu-id="afd76-111">Режим</span><span class="sxs-lookup"><span data-stu-id="afd76-111">Mode</span></span> | <span data-ttu-id="afd76-112">Команда PowerShell</span><span class="sxs-lookup"><span data-stu-id="afd76-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="afd76-113">5</span><span class="sxs-lookup"><span data-stu-id="afd76-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="afd76-114">О-ва + уведомить Скайп для бизнес-пользователя</span><span class="sxs-lookup"><span data-stu-id="afd76-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="afd76-115">(Используйте эту команду, если пользователи находятся в режиме **острова** (по умолчанию))</span><span class="sxs-lookup"><span data-stu-id="afd76-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="afd76-116">*(например, $SipAddress = «TestUser@contoso.com»)*</span><span class="sxs-lookup"><span data-stu-id="afd76-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="afd76-117">5</span><span class="sxs-lookup"><span data-stu-id="afd76-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="afd76-118">Скайп для бизнеса только + уведомить Скайп для бизнес-пользователя</span><span class="sxs-lookup"><span data-stu-id="afd76-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="afd76-119">(Используйте эту команду, если пользователи находятся в режиме **Скайп для бизнеса только** )</span><span class="sxs-lookup"><span data-stu-id="afd76-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="afd76-120">7</span><span class="sxs-lookup"><span data-stu-id="afd76-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="afd76-121">Только группы</span><span class="sxs-lookup"><span data-stu-id="afd76-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |
