---
title: Устранение неполадок с гостевым доступом в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Узнайте, как устранить неполадки с гостевым доступом в Microsoft Teams и устранить проблемы с ним.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e0a3530b7a1f9029d9f671d0a02ef58cbb7907bf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871735"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="19737-103">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19737-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="19737-104">Чтобы изменения вступили в силу, возможно, потребуется подождать до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="19737-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="19737-105">Для проверки текущих проблем с доступом к гостевой службе в Teams перейдите в раздел [Устранение неполадок команды Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="19737-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="19737-106">Чтобы узнать, что мы знаем о проблеме, ознакомьтесь со статьей [Известные проблемы в Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="19737-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="19737-107">Гости — это пользователи за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="19737-107">Guests are users outside your organization.</span></span> <span data-ttu-id="19737-108">Если кто-то входит в вашу организацию (в том числе на ваших сотрудников, подрядчиков или агентах по сайту), их нельзя добавить в качестве гостей.</span><span class="sxs-lookup"><span data-stu-id="19737-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="19737-109">То же касается ваших аффилированных лиц.</span><span class="sxs-lookup"><span data-stu-id="19737-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="19737-110">Узнайте о предстоящих новых и обновленных функциях гостевого доступа в [планах Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="19737-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="19737-111">Расскажите нам, что вам нужно, в [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="19737-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="19737-112">Если гости видят ошибки лицензий</span><span class="sxs-lookup"><span data-stu-id="19737-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="19737-113">Гостевой доступ в Teams использует бизнес-компанию Azure Active Directory (Azure AD) для бизнеса (B2B) и модель лицензирования.</span><span class="sxs-lookup"><span data-stu-id="19737-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="19737-114">Функция гостевого доступа включена во все подписки Office 365 бизнес премиум, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="19737-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="19737-115">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="19737-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="19737-116">Если вы видите ошибки лицензирования, ознакомьтесь с [рекомендациями по лицензированию Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , чтобы определить требования к лицензированию в соответствии с вашими потребностями для гостевого доступа в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="19737-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="19737-117">Гостевые лицензии подсчитываются с помощью приглашенной Организации.</span><span class="sxs-lookup"><span data-stu-id="19737-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="19737-118">Это следует помнить при расчете количества лицензий, которые вам понадобятся.</span><span class="sxs-lookup"><span data-stu-id="19737-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="19737-119">Лицензии будут учитываться в вашей организации, независимо от того, приходят ли приглашенные гости другим клиентам Office 365 или используют их личные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="19737-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="19737-120">Поддержка типов пользователей B2B</span><span class="sxs-lookup"><span data-stu-id="19737-120">Support for B2B User types</span></span>
<span data-ttu-id="19737-121">В настоящее время поддерживаются только типы "состояние 1" и "состояние 2" для гостевых пользователей [в соответствии с определением Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="19737-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="19737-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="19737-122">Related topics</span></span>

[<span data-ttu-id="19737-123">Гостевой доступ в Teams</span><span class="sxs-lookup"><span data-stu-id="19737-123">Guest access in Teams</span></span>](guest-access.md)


