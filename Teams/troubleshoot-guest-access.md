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
description: Справка по устранению неполадок и исправлению проблем с гостевым доступом в Microsoft Teams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 52d3922bc68e942ad1cd58e40861fa8820ee6614
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778405"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="67e77-103">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="67e77-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="67e77-104">Чтобы изменения вступили в силу, может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="67e77-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="67e77-105">Чтобы ознакомиться с текущими проблемами поддержки с гостевым доступом в Teams, перейдите в раздел [устранения неполадок в Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="67e77-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="67e77-106">Чтобы узнать, известно ли нам о вашей проблеме, ознакомьтесь со статьей [Известные проблемы для Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="67e77-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="67e77-107">Гости — это пользователи из-за пределов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="67e77-107">Guests are users outside your organization.</span></span> <span data-ttu-id="67e77-108">Если пользователь находится внутри вашей организации (включая ваших сотрудников, подрядчиков на площадке или агентов на площадке), его нельзя добавить в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="67e77-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="67e77-109">То же касается ваших аффилированных лиц.</span><span class="sxs-lookup"><span data-stu-id="67e77-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="67e77-110">Узнавайте о новых и обновленных функциях гостевого доступа из [Дорожной карты Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="67e77-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="67e77-111">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="67e77-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="67e77-112">Если у гостей возникают ошибки лицензирования</span><span class="sxs-lookup"><span data-stu-id="67e77-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="67e77-113">Гостевой доступ в Teams использует взаимодействие "бизнес-бизнес" (B2B) Azure Active Directory (Azure AD) и соответствующую модель лицензирования.</span><span class="sxs-lookup"><span data-stu-id="67e77-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="67e77-114">Гостевой доступ входит в состав всех Microsoft 365 Business Standard, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="67e77-114">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="67e77-115">Дополнительная лицензия Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="67e77-115">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="67e77-116">Для использования гостевых групп в качестве гостя на другом клиенте (ресурсе) Teams необходимо включить в домашнюю страницу гостя.</span><span class="sxs-lookup"><span data-stu-id="67e77-116">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="67e77-117">Если вы видите ошибки лицензирования, ознакомьтесь с [рекомендациями по лицензированию Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , чтобы определить требования к лицензированию в соответствии с вашими потребностями для гостевого доступа в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="67e77-117">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="67e77-118">Гостевые лицензии учитываются в приглашающей организации.</span><span class="sxs-lookup"><span data-stu-id="67e77-118">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="67e77-119">Это следует иметь в виду при подсчете количества необходимых лицензий.</span><span class="sxs-lookup"><span data-stu-id="67e77-119">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="67e77-120">Лицензии будут учитываться для вашей организации, независимо от того, приходят ли приглашенные гости из другой организации Office 365 или используют их личные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="67e77-120">Licenses are counted against your organization whether the invited guests come from another Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="67e77-121">Поддержка типов пользователей B2B</span><span class="sxs-lookup"><span data-stu-id="67e77-121">Support for B2B User types</span></span>
<span data-ttu-id="67e77-122">В настоящее время Teams поддерживает гостевых пользователей только с состояниями 1 и 2 [согласно определению Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="67e77-122">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="67e77-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="67e77-123">Related topics</span></span>

[<span data-ttu-id="67e77-124">Гостевой доступ в Teams</span><span class="sxs-lookup"><span data-stu-id="67e77-124">Guest access in Teams</span></span>](guest-access.md)


