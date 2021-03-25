---
title: Microsoft 365 для государственных органов — GCC High deployments
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Руководство для ИТ-специалистов по развертыванию Office 365 в сущностям, обрабатывающих данные в правительственных учреждениях США.
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
ms.openlocfilehash: c5533b6d5c2e08cb79ec8dd2052d761d86546b05
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117847"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="edb6c-103">Планирование развертывания Office 365 для государственных служб с высоким уровнем GCC</span><span class="sxs-lookup"><span data-stu-id="edb6c-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="edb6c-104">Это руководство поможет ИТ-специалистов, которые являются управляющими развертыванием Office 365 в федеральных государственных структурах США или других организациях, обрабатывающих данные, которые соответствуют правительственным требованиям и требованиям, в которых использование Office 365 для государственных учреждений (GCC High) подходит для удовлетворения этих требований.</span><span class="sxs-lookup"><span data-stu-id="edb6c-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="edb6c-105">Если ваша организация уже выполнила требования к высокому требованию к Office 365 для государственных организаций, а затем была применена к программе и приняты в нее, можно пропустить шаги 1 и 2 и перейти непосредственно к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="edb6c-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="edb6c-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="edb6c-106">Step 1.</span></span> <span data-ttu-id="edb6c-107">Определите, требуется ли вашей организации Office 365 для государственных организаций — GCC High и соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="edb6c-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="edb6c-108">Среда Office 365 Government — GCC High обеспечивает соответствие требованиям государственных органов США к облачным службам.</span><span class="sxs-lookup"><span data-stu-id="edb6c-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="edb6c-109">Помимо возможностей Office 365, в организациях есть следующие уникальные возможности Office 365 для государственных организаций — GCC High:</span><span class="sxs-lookup"><span data-stu-id="edb6c-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="edb6c-110">Содержимое вашей организации от контента клиентов логически отделяется от контента клиентов в коммерческих службах Office 365 от Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="edb6c-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="edb6c-111">Содержимое вашей организации хранится в США.</span><span class="sxs-lookup"><span data-stu-id="edb6c-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="edb6c-112">Доступ к содержимому клиентов вашей организации ограничен экранными данными сотрудников Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="edb6c-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="edb6c-113">Office 365 для государственных организаций — GCC High соответствует сертификациям и секторам, которые требуются клиентам государственного сектора США.</span><span class="sxs-lookup"><span data-stu-id="edb6c-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="edb6c-114">Дополнительные сведения о предложении Office 365 для государственных служб с высоким уровнем GCC для государственных органов США можно найти на сайте планов [Office 365](https://products.office.com/government/compare-office-365-government-plans)для государственных органов, в том числе требования к [правомочности.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="edb6c-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="edb6c-115">В [описании службы Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) для государственных органов США описаны преимущества платформы, которые в центре требований к обеспечению соответствия требованиям в США.</span><span class="sxs-lookup"><span data-stu-id="edb6c-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="edb6c-116">Может потребоваться перенести таблицы сведений из описания службы в книгу Excel и добавить два столбца: "Релевантные" для моей организации **"Y/N"** и "Соответствует потребностям моей **организации" "Y/N".**</span><span class="sxs-lookup"><span data-stu-id="edb6c-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="edb6c-117">Затем вы можете вместе с коллегами просмотреть этот список, чтобы подтвердить, что эта служба соответствует потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="edb6c-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="edb6c-119">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="edb6c-119">Decision points</span></span>|<ul><li><span data-ttu-id="edb6c-120">Определите, подходит ли office 365 для государственных организаций (GCC High) вашей организации.</span><span class="sxs-lookup"><span data-stu-id="edb6c-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="edb6c-121">Подтвердите, что ваша организация соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="edb6c-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="edb6c-122">Office 365 для государственных органов — GCC High доступен только в США.</span><span class="sxs-lookup"><span data-stu-id="edb6c-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="edb6c-123">Клиенты из других стран могут выбрать один из нескольких планов [Office 365 для государственных органов.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="edb6c-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="edb6c-124">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="edb6c-124">Step 2.</span></span> <span data-ttu-id="edb6c-125">Подача заявки на получение Office 365 для государственных органов — GCC High</span><span class="sxs-lookup"><span data-stu-id="edb6c-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="edb6c-126">Если вы решили, что эта служба под правильными для вашей организации, начните подачу [заявки на получение этой службы.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="edb6c-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="edb6c-127">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="edb6c-127">Step 3.</span></span> <span data-ttu-id="edb6c-128">Понимание параметров безопасности Office 365 для государственных учреждения.</span><span class="sxs-lookup"><span data-stu-id="edb6c-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="edb6c-129">Рекомендуем внимательно и тщательно и внести изменения в параметры безопасности и администратора и учесть влияние на соответствие требованиям, прежде чем вносить изменения в параметры безопасности по умолчанию. [](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="edb6c-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="edb6c-131">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="edb6c-131">Decision point</span></span>|<ul><li><span data-ttu-id="edb6c-132">Решите, нужно ли изменить какие-либо стандартные параметры безопасности Office 365 для государственных учреждения (GCC) и решите, как они влияют на изменения, которые вы можете внести.</span><span class="sxs-lookup"><span data-stu-id="edb6c-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="edb6c-133">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="edb6c-133">Step 4.</span></span> <span data-ttu-id="edb6c-134">Как понять, какие возможности Teams в настоящее время доступны в Office 365 для государственных органов — GCC High</span><span class="sxs-lookup"><span data-stu-id="edb6c-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="edb6c-135">В требованиях наших облачных правительственных органов существуют некоторые различия между Teams в Планах Office 365 для государственных органов : GCC High и Teams в корпоративных планах.</span><span class="sxs-lookup"><span data-stu-id="edb6c-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="edb6c-136">Чтобы узнать, какие возможности доступны, см. таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="edb6c-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="edb6c-137">Описание службы Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edb6c-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="edb6c-138">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="edb6c-138">Step 5.</span></span> <span data-ttu-id="edb6c-139">Планирование управления</span><span class="sxs-lookup"><span data-stu-id="edb6c-139">Plan for governance</span></span>

<span data-ttu-id="edb6c-140">Определите свои требования для управления и определите, как их можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="edb6c-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="edb6c-141">Дополнительные сведения [можно найти в области "Планирование управления в Teams".](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="edb6c-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="edb6c-142">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="edb6c-142">Decision point</span></span> |<ul><li><span data-ttu-id="edb6c-143">Определите и за документируйте требования к управлению, следуя инструкциям плана управления [в Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="edb6c-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="edb6c-144">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="edb6c-144">Step 6.</span></span> <span data-ttu-id="edb6c-145">Развертывание Teams для совместной работы</span><span class="sxs-lookup"><span data-stu-id="edb6c-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="edb6c-146">После того как вы будете переназначен на план Office 365 для государственных структур — GCC High, следуйте рекомендуемым путям развертывания, описанным в описании развертывания [Microsoft Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="edb6c-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="edb6c-147">Обязательно взаимодействовайте с командой по внедрению и управлению изменениями, а также с другими менеджерами Teams.</span><span class="sxs-lookup"><span data-stu-id="edb6c-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="edb6c-148">Вы также можете использовать [службу FastTrack](https://www.microsoft.com/fasttrack) или выбранного партнера.</span><span class="sxs-lookup"><span data-stu-id="edb6c-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="edb6c-149">Клиент Mac Teams для сред GCCH пока не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="edb6c-149">The Mac Teams client for GCCH environments is not yet supported.</span></span>