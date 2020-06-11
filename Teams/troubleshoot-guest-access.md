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
ms.openlocfilehash: 32a334f4866c1874f60e85e3b74908f161d45a33
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691555"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="a2c2e-103">Устранение неполадок с гостевым доступом в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a2c2e-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

- <span data-ttu-id="a2c2e-104">Чтобы узнать, что мы знаем о проблеме, изучите [команды поддержки в своей организации](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a2c2e-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="a2c2e-105">Чтобы ознакомиться с текущими проблемами поддержки с гостевым доступом в Teams, перейдите в раздел [устранения неполадок в Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="a2c2e-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="a2c2e-106">Гости — это пользователи из-за пределов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-106">Guests are users outside your organization.</span></span> <span data-ttu-id="a2c2e-107">Если пользователь находится внутри вашей организации (включая ваших сотрудников, подрядчиков на площадке или агентов на площадке), его нельзя добавить в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="a2c2e-108">То же касается ваших аффилированных лиц.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="a2c2e-109">Узнавайте о новых и обновленных функциях гостевого доступа из [Дорожной карты Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="a2c2e-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="a2c2e-110">Сообщите, какие функции нужны вам, на сайте [UserVoice, посвященном Teams](https://aka.ms/TeamsUserVoice).</span><span class="sxs-lookup"><span data-stu-id="a2c2e-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="a2c2e-111">Если у гостей возникают ошибки лицензирования</span><span class="sxs-lookup"><span data-stu-id="a2c2e-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="a2c2e-112">Гостевой доступ в Teams использует взаимодействие "бизнес-бизнес" (B2B) Azure Active Directory (Azure AD) и соответствующую модель лицензирования.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="a2c2e-113">Функция гостевого доступа включена во все подписки Microsoft 365 бизнес стандарт, Office 365 корпоративный и Office 365 для образования.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="a2c2e-114">Дополнительная лицензия Microsoft 365 или Office 365 не требуется.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="a2c2e-115">Для использования гостевых групп в качестве гостя на другом клиенте (ресурсе) Teams необходимо включить в домашнюю страницу гостя.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="a2c2e-116">Если вы видите ошибки лицензирования, ознакомьтесь с [рекомендациями по лицензированию Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , чтобы определить требования к лицензированию в соответствии с вашими потребностями для гостевого доступа в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-116">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="a2c2e-117">Гостевые лицензии учитываются в приглашающей организации.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="a2c2e-118">Это следует иметь в виду при подсчете количества необходимых лицензий.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="a2c2e-119">Лицензия учитывается в вашей организации в том случае, если приглашенные гости поступают из другой организации Microsoft 365 или Office 365 или используют свои личные адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a2c2e-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 or Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="a2c2e-120">Поддержка типов пользователей B2B</span><span class="sxs-lookup"><span data-stu-id="a2c2e-120">Support for B2B User types</span></span>
<span data-ttu-id="a2c2e-121">В настоящее время Teams поддерживает гостевых пользователей только с состояниями 1 и 2 [согласно определению Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="a2c2e-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2c2e-122">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a2c2e-122">Related topics</span></span>

[<span data-ttu-id="a2c2e-123">Гостевой доступ в Teams</span><span class="sxs-lookup"><span data-stu-id="a2c2e-123">Guest access in Teams</span></span>](guest-access.md)


