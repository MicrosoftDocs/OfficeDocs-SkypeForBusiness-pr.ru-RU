---
title: Проверка готовности среды для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: Сведения о проверке готовности среды для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c0609efd8ac0286857b44996939378e57ce2702f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234923"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a><span data-ttu-id="4f1a1-103">Проверка готовности среды для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4f1a1-103">Check your environment’s readiness for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="4f1a1-104">Каждая организация переходит в облако по-своему, а текущее состояние среды может влиять на работу Teams.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-104">The transition to the cloud will vary by each organization, and current state may have an impact on how Teams will function.</span></span>

<span data-ttu-id="4f1a1-105">Образовательные учреждения настоятельно рекомендуется [развертывать School Data Sync](https://docs.microsoft.com/schooldatasync/) перед развертыванием Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-105">Educational institutions are strongly encouraged to [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span> <span data-ttu-id="4f1a1-106">School Data Sync использует данные подсписка SIS для учебного заведения, чтобы автоматически создавать классы и группы для Microsoft Teams и других приложений.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-106">School Data Sync uses your school’s SIS roster data to automatically create classes and groups for Microsoft Teams and other applications.</span></span>

<span data-ttu-id="4f1a1-107">Чтобы обеспечить оптимальное взаимодействие с Teams, вашей организации следует сначала развернуть Exchange Online и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-107">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="4f1a1-108">Кроме того, необходимо убедиться, что текущая среда готова для Teams.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-108">You must also ensure that your current environment is ready for Teams.</span></span>  <span data-ttu-id="4f1a1-109">Дополнительные сведения можно найти по следующим ссылкам:</span><span class="sxs-lookup"><span data-stu-id="4f1a1-109">Refer to these links for help:</span></span>

-   <span data-ttu-id="4f1a1-110">Если ваша организация не развернула никакие рабочие нагрузки Office 365, см. статью [Приступая к работе с Office 365 бизнес](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="4f1a1-110">If your organization has not deployed any Office 365 workloads, see [Getting Started with Office 365 for business.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span></span>

-   <span data-ttu-id="4f1a1-111">Если ваша организация не добавила или не настроила проверенный домен для Office 365, см. статью [Проверка домена Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="4f1a1-111">If your organization has not added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

-   <span data-ttu-id="4f1a1-112">Если ваша организация не синхронизировала удостоверения в Azure Active Directory, см. статью [Модели удостоверений и проверка подлинности в Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4f1a1-112">If your organization has not synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

-   <span data-ttu-id="4f1a1-113">Если ваша организация не использует Exchange Online, см. статью [Взаимодействие Exchange и Microsoft Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="4f1a1-113">If your organization does not have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

-   <span data-ttu-id="4f1a1-114">Если ваша организация не использует SharePoint Online, см. статью [Взаимодействие SharePoint Online и OneDrive для бизнеса с Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="4f1a1-114">If your organization does not have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="4f1a1-115">Если ваша организация — образовательное учреждение и вы используете систему информации об учащихся (SIS), выполните [развертывание School Data Sync](https://docs.microsoft.com/schooldatasync/) перед развертыванием Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-115">If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="4f1a1-116">Если в вашей организации есть локальное развертывание Skype для бизнеса Server (или Lync Server), необходимо настроить Azure AD Connect для синхронизации локального каталога с Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f1a1-116">If your organization has an existing on-premises Skype for Business Server (or Lync Server) deployment, you must configure Azure AD Connect to synchronize your on-premises directory with Office 365.</span></span>  <span data-ttu-id="4f1a1-117">Дополнительные сведения можно найти в разделе [Настройка Azure AD Connect для Teams и Skype для бизнеса](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="4f1a1-117">For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect).</span></span>