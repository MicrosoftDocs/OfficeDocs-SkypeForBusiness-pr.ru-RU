---
title: Устранение неполадок с гостевым доступом в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0ce7744aa18fe8ffe3fc83ca40649672f521bbba
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346360"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="ba415-103">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba415-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="ba415-104">Чтобы узнать, знаем ли мы о вашей проблеме, ознакомьтесь со службой [поддержки Teams в вашей организации.](Known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="ba415-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="ba415-105">Чтобы ознакомиться с текущими проблемами поддержки с гостевым доступом в Teams, перейдите в раздел [устранения неполадок в Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="ba415-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="ba415-106">Гости — это люди за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ba415-106">Guests are people outside your organization.</span></span> <span data-ttu-id="ba415-107">Если пользователь находится внутри вашей организации (включая ваших сотрудников, подрядчиков на площадке или агентов на площадке), его нельзя добавить в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="ba415-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="ba415-108">То же касается ваших аффилированных лиц.</span><span class="sxs-lookup"><span data-stu-id="ba415-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="ba415-109">Узнавайте о новых и обновленных функциях гостевого доступа из [Дорожной карты Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="ba415-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="ba415-110">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="ba415-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="ba415-111">Если у гостей возникают ошибки лицензирования</span><span class="sxs-lookup"><span data-stu-id="ba415-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="ba415-112">Гостевой доступ в Teams использует взаимодействие "бизнес-бизнес" (B2B) Azure Active Directory (Azure AD) и соответствующую модель лицензирования.</span><span class="sxs-lookup"><span data-stu-id="ba415-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="ba415-113">Функция гостевого доступа включена во все подписки Microsoft 365 бизнес стандарт, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="ba415-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ba415-114">Дополнительная лицензия Microsoft 365 или Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="ba415-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="ba415-115">Для входа и использования Teams в качестве гостя в другом (ресурсе) клиенте для гостей должна быть включена возможность использования Teams в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="ba415-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="ba415-116">Если вы видите ошибки лицензирования, ознакомьтесь с моделью вы выставления счета для внешних удостоверений [Azure AD,](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) чтобы определить требования лицензирования для гостевого доступа в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ba415-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="ba415-117">Гостевые лицензии учитываются в приглашающей организации.</span><span class="sxs-lookup"><span data-stu-id="ba415-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="ba415-118">Это следует иметь в виду при подсчете количества необходимых лицензий.</span><span class="sxs-lookup"><span data-stu-id="ba415-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="ba415-119">Лицензии учитываются в вашей организации независимо от того, были ли приглашенные гости из другой организации Microsoft 365 или используют их личные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ba415-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="ba415-120">Поддержка типов пользователей B2B</span><span class="sxs-lookup"><span data-stu-id="ba415-120">Support for B2B User types</span></span>

<span data-ttu-id="ba415-121">В настоящее время Teams поддерживает гостевых пользователей только с состояниями 1 и 2 [согласно определению Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="ba415-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba415-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ba415-122">Related topics</span></span>

[<span data-ttu-id="ba415-123">Гостевой доступ в Teams</span><span class="sxs-lookup"><span data-stu-id="ba415-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="ba415-124">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="ba415-124">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)