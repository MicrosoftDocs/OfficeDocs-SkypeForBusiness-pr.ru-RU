---
title: Проверка готовности среды для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Сведения о проверке готовности среды для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1794b87beb1c6b1f1e499c214cde8d3e0b9b0a34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235407"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a><span data-ttu-id="257f1-103">Проверка готовности среды для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="257f1-103">Check your environment’s readiness for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="257f1-104">Каждая организация переходит в облако по-своему, а текущее состояние среды может влиять на работу Teams.</span><span class="sxs-lookup"><span data-stu-id="257f1-104">The transition to the cloud will vary by each organization, and current state may have an impact on how Teams will function.</span></span>

<span data-ttu-id="257f1-105">Учебные заведения, настоятельно рекомендуется для [развертывания синхронизации данных School](https://docs.microsoft.com/schooldatasync/) перед развертыванием группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="257f1-105">Educational institutions are strongly encouraged to [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span> <span data-ttu-id="257f1-106">Синхронизация данных School использует данные участников SIS вашей школы для автоматического создания классов и группы для групп Майкрософт и другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="257f1-106">School Data Sync uses your school’s SIS roster data to automatically create classes and groups for Microsoft Teams and other applications.</span></span>

<span data-ttu-id="257f1-107">Чтобы обеспечить оптимальное взаимодействие с Teams, вашей организации следует сначала развернуть Exchange Online и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="257f1-107">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="257f1-108">Также необходимо убедиться, что текущая среда готова для групп.</span><span class="sxs-lookup"><span data-stu-id="257f1-108">You must also ensure that your current environment is ready for Teams.</span></span>  <span data-ttu-id="257f1-109">Ссылаться на эти ссылки для получения справки:</span><span class="sxs-lookup"><span data-stu-id="257f1-109">Refer to these links for help:</span></span>

-   <span data-ttu-id="257f1-110">Если ваша организация не развернула никакие рабочие нагрузки Office 365, см. статью [Приступая к работе с Office 365 бизнес](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="257f1-110">If your organization has not deployed any Office 365 workloads, see [Getting Started with Office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span></span>

-   <span data-ttu-id="257f1-111">Если ваша организация не добавила или не настроила проверенный домен для Office 365, см. статью [Проверка домена Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="257f1-111">If your organization has not added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="257f1-112">Если ваша организация не синхронизировала удостоверения в Azure Active Directory, см. статью [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="257f1-112">If your organization has not synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="257f1-113">Если ваша организация не использует Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="257f1-113">If your organization does not have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="257f1-114">Если ваша организация не использует SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="257f1-114">If your organization does not have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="257f1-115">Если ваша организация заведения и использовать учебы сведения о системе (SIS), [Развертывание синхронизации данных School](https://docs.microsoft.com/schooldatasync/) перед развертыванием группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="257f1-115">If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="257f1-116">Если в вашей организации есть существующих Скайп локального развертывания Business Server (или Lync Server), необходимо настроить подключение Azure AD для синхронизации локального каталога с Office 365.</span><span class="sxs-lookup"><span data-stu-id="257f1-116">If your organization has an existing on-premises Skype for Business Server (or Lync Server) deployment, you must configure Azure AD Connect to synchronize your on-premises directory with Office 365.</span></span>  <span data-ttu-id="257f1-117">Для получения дополнительных сведений см [Настройка Azure AD для групп и Скайп для бизнеса](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="257f1-117">For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span></span>