---
title: Office 365 для государственных организаций — развертывание doD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Руководство для ИТ-специалистов по развертыванию Office 365 в организациях, которые обрабатывают данные, влияют на нормы doD государственных учреждений США.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd649507c0108e9a3d500f4d30cae46a3181d75d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117857"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="eae90-103">Планирование Office 365 для государственных организаций — развертывание doD</span><span class="sxs-lookup"><span data-stu-id="eae90-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="eae90-104">Это руководство подходит для ИТ-специалистов, которые являются управляющими развертыванием Office 365 в федеральных государственных учреждениях США или других субъектах, которые обрабатывают данные, на которые налагаются государственные нормы и требования, где использование Office 365 для государственных организаций — DoD соответствует этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="eae90-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="eae90-105">Если ваша организация уже выполнила требования к Office 365 для государственных организаций – DoD и применилась к программе и была приняты в программу, вы можете пропустить шаги 1 и 2 и перейти непосредственно к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="eae90-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="eae90-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="eae90-106">Step 1.</span></span> <span data-ttu-id="eae90-107">Определите, требуется ли вашей организации Office 365 для государственных организаций - DoD и соответствует требованиям к правомочности.</span><span class="sxs-lookup"><span data-stu-id="eae90-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="eae90-108">Среда Office 365 для государственных организаций - DoD обеспечивает соответствие требованиям государственных органов США к облачным службам.</span><span class="sxs-lookup"><span data-stu-id="eae90-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="eae90-109">Помимо возможностей и возможностей Office 365, в организациях есть уникальные функции, которые уникальны для Office 365 для государственных организаций – DoD:</span><span class="sxs-lookup"><span data-stu-id="eae90-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="eae90-110">Содержимое клиентов организации логически отделяется от контента клиентов в коммерческих Office 365 от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eae90-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="eae90-111">Содержимое вашей организации хранится на территории США.</span><span class="sxs-lookup"><span data-stu-id="eae90-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="eae90-112">Доступ к содержимому клиентов вашей организации ограничен для персонала Майкрософт с проверкой.</span><span class="sxs-lookup"><span data-stu-id="eae90-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="eae90-113">Office 365 для государственных организаций - DoD соответствует сертификациям и сертифицированным системам, которые требуются для клиентов с общедоступным сектором США.</span><span class="sxs-lookup"><span data-stu-id="eae90-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="eae90-114">Дополнительные сведения о предложении Office 365 для государственных организаций doD для клиентов из государственных Office 365 для государственных организаций [США,](https://products.office.com/government/compare-office-365-government-plans)включая требования [к правомочности.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="eae90-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="eae90-115">В [Office 365 правительственных](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) служб США описаны преимущества платформы, в центре которой находятся требования к соблюдению требований в СОЕДИНЕННЫх Штатах.</span><span class="sxs-lookup"><span data-stu-id="eae90-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="eae90-116">Может потребоваться перенести таблицы данных из описания службы в книгу Excel и добавить два столбца: Релевантные для моей организации **Y/N** и Соответствует потребностям моей организации **Y/N**.</span><span class="sxs-lookup"><span data-stu-id="eae90-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="eae90-117">Затем вы можете просмотреть этот список вместе с коллегами, чтобы подтвердить, что эта служба соответствует потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="eae90-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="eae90-119">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="eae90-119">Decision points</span></span>|<ul><li><span data-ttu-id="eae90-120">Решите, Office 365 для государственных организаций — DoD подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="eae90-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="eae90-121">Подтвердите, что ваша организация соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="eae90-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="eae90-122">Office 365 для государственных организаций - DoD доступна только в США.</span><span class="sxs-lookup"><span data-stu-id="eae90-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="eae90-123">Клиенты, не в том числе сша, могут выбрать один из Office 365 для государственных организаций [планов.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="eae90-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="eae90-124">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="eae90-124">Step 2.</span></span> <span data-ttu-id="eae90-125">Подача заявки Office 365 для государственных организаций - DoD</span><span class="sxs-lookup"><span data-stu-id="eae90-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="eae90-126">Решив, что эта служба подгона для вашей организации, начните подачу [заявки на получение этой службы.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="eae90-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="eae90-127">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="eae90-127">Step 3.</span></span> <span data-ttu-id="eae90-128">Понимание Office 365 для государственных организаций— стандартные параметры безопасности DoD.</span><span class="sxs-lookup"><span data-stu-id="eae90-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="eae90-129">Мы рекомендуем тщательно и тщательно проработать параметры безопасности и администратора, прежде чем вносить изменения в параметры безопасности, задав влияние на соответствие требованиям. [](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="eae90-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="eae90-131">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="eae90-131">Decision point</span></span>|<ul><li><span data-ttu-id="eae90-132">Решите, нужно ли изменить какие-либо из стандартных Office 365 для государственных организаций — параметров безопасности DoD, разрешив сначала понять, на что влияют любые изменения, которые вы можете внести.</span><span class="sxs-lookup"><span data-stu-id="eae90-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="eae90-133">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="eae90-133">Step 4.</span></span> <span data-ttu-id="eae90-134">Как понять Teams возможности Teams в настоящее время доступны в Office 365 для государственных организаций - DoD</span><span class="sxs-lookup"><span data-stu-id="eae90-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="eae90-135">С учетом требований наших облачных клиентов государственных Teams в Office 365 для государственных организаций — DoD и Teams в Enterprise планах.</span><span class="sxs-lookup"><span data-stu-id="eae90-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="eae90-136">Чтобы узнать, какие возможности доступны, см. таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="eae90-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="eae90-137">Microsoft Teams описание службы</span><span class="sxs-lookup"><span data-stu-id="eae90-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="eae90-138">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="eae90-138">Step 5.</span></span> <span data-ttu-id="eae90-139">Планирование управления</span><span class="sxs-lookup"><span data-stu-id="eae90-139">Plan for governance</span></span>

<span data-ttu-id="eae90-140">Определите свои требования к управлению и о том, как их можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="eae90-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="eae90-141">Дополнительные [сведения можно найти в](plan-teams-governance.md) Teams в области Планирование управления.</span><span class="sxs-lookup"><span data-stu-id="eae90-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="eae90-142">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="eae90-142">Decision point</span></span> |<ul><li><span data-ttu-id="eae90-143">Определите и документируйте требования к управлению, следуя инструкциям в [Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="eae90-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="eae90-144">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="eae90-144">Step 6.</span></span> <span data-ttu-id="eae90-145">Развертывание Teams для совместной работы</span><span class="sxs-lookup"><span data-stu-id="eae90-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="eae90-146">После того как вы будете переназначен в Office 365 для государственных организаций — DoD, следуйте рекомендованным путям развертывания, описанным в [Microsoft Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="eae90-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="eae90-147">Не забудьте взаимодействовать со своей командой по внедрению и управлению изменениями и Teams руководствами.</span><span class="sxs-lookup"><span data-stu-id="eae90-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="eae90-148">Вы также можете работать с [FastTrack](https://www.microsoft.com/fasttrack) или выбранным партнером, чтобы использовать службу.</span><span class="sxs-lookup"><span data-stu-id="eae90-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="eae90-149">Клиент mac Teams для сред DOD пока не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="eae90-149">The Mac Teams client for DOD environments is not yet supported.</span></span>