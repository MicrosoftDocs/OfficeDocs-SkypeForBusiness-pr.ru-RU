---
title: Microsoft 365 Государственные — GCC высокий уровень развертывания
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Руководство для ИТ-специалистов по развертыванию Office 365 в организациях, которые обрабатывают данные, подавлимые на правительственный регламент США.
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
ms.openlocfilehash: 9e5f8df087ca7ad999a9756467925be68c60e96f
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718060"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="388f0-103">Планирование Office 365 для государственных организаций — GCC высокий уровень развертывания</span><span class="sxs-lookup"><span data-stu-id="388f0-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="388f0-104">Это руководство подходит для ИТ-специалистов, которые являются управляющими развертыванием Office 365 в государственных учреждениях США или других субъектах, которые обрабатывают данные, на которые налагаются государственные нормы и требования, где использование Office 365 для государственных организаций – GCC Высокая соответствует этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="388f0-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="388f0-105">Если ваша организация уже выполнила Office 365 для государственных организаций – GCC Требования к высоким требованиям к требованиям, которые были применены и приняты в программу, можно пропустить шаги 1 и 2 и перейти непосредственно к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="388f0-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="388f0-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="388f0-106">Step 1.</span></span> <span data-ttu-id="388f0-107">Определите, требуется ли вашей Office 365 для государственных организаций — GCC высокая и соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="388f0-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="388f0-108">Среда Office 365 для государственных организаций - GCC Высокая обеспечивает соответствие требованиям государственных органов США к облачным службам.</span><span class="sxs-lookup"><span data-stu-id="388f0-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="388f0-109">Помимо возможностей и возможностей Office 365, в организациях есть уникальные возможности, которые уникальны для Office 365 для государственных организаций – GCC Высокая:</span><span class="sxs-lookup"><span data-stu-id="388f0-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="388f0-110">Содержимое клиентов организации логически отделяется от контента клиентов в коммерческих Office 365 от Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="388f0-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="388f0-111">Содержимое вашей организации для клиентов хранится на территории США.</span><span class="sxs-lookup"><span data-stu-id="388f0-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="388f0-112">Доступ к содержимому клиентов вашей организации ограничен для персонала Майкрософт с проверкой.</span><span class="sxs-lookup"><span data-stu-id="388f0-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="388f0-113">Office 365 для государственных организаций – GCC высокая соответствует сертификациям и заказчикам, которые требуются для клиентов из государственного сектора США.</span><span class="sxs-lookup"><span data-stu-id="388f0-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="388f0-114">Дополнительные сведения о предложении Office 365 для государственных организаций – GCC для клиентов из государственных [](https://products.office.com/government/compare-office-365-government-plans)Office 365 для государственных организаций США можно найти на сайте Office 365 для государственных организаций, включая [требования к правомочности.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="388f0-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="388f0-115">В [Office 365 правительственных](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) служб США описаны преимущества платформы, в центре которой находятся требования к соблюдению требований в СОЕДИНЕННЫх Штатах.</span><span class="sxs-lookup"><span data-stu-id="388f0-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="388f0-116">Может потребоваться перенести таблицы данных из описания службы в книгу Excel и добавить два столбца: Релевантные для моей организации **Y/N** и Соответствует потребностям моей организации **Y/N**.</span><span class="sxs-lookup"><span data-stu-id="388f0-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="388f0-117">Затем вы можете просмотреть этот список вместе с коллегами, чтобы подтвердить, что эта служба соответствует потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="388f0-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="388f0-119">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="388f0-119">Decision points</span></span>|<ul><li><span data-ttu-id="388f0-120">Решите, подходит ли Office 365 для государственных организаций – GCC высокая для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="388f0-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="388f0-121">Подтвердите, что ваша организация соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="388f0-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="388f0-122">Office 365 для государственных организаций - GCC Высокая доступна только в США.</span><span class="sxs-lookup"><span data-stu-id="388f0-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="388f0-123">Клиенты, не в том числе сша, могут выбрать один из Office 365 для государственных организаций [планов.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="388f0-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="388f0-124">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="388f0-124">Step 2.</span></span> <span data-ttu-id="388f0-125">Применить для Office 365 для государственных организаций — GCC высокая</span><span class="sxs-lookup"><span data-stu-id="388f0-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="388f0-126">Решив, что эта служба подгона для вашей организации, начните подачу [заявки на получение этой службы.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="388f0-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="388f0-127">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="388f0-127">Step 3.</span></span> <span data-ttu-id="388f0-128">Понимание Office 365 для государственных организаций — GCC параметры безопасности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="388f0-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="388f0-129">Прежде чем вносить изменения в параметры безопасности по умолчанию, внимательно продумайте параметры администратора и безопасности, а также продумайте, как это влияет на соответствие требованиям. [](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="388f0-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="388f0-131">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="388f0-131">Decision point</span></span>|<ul><li><span data-ttu-id="388f0-132">Решите, нужно ли изменить какой-либо из стандартных Office 365 для государственных организаций — GCC высокий уровень безопасности, разрешив сначала понять, на что влияют все изменения, которые вы можете внести.</span><span class="sxs-lookup"><span data-stu-id="388f0-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="388f0-133">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="388f0-133">Step 4.</span></span> <span data-ttu-id="388f0-134">Как понять Teams возможности, доступные в настоящее время в Office 365 для государственных организаций — GCC Высокая</span><span class="sxs-lookup"><span data-stu-id="388f0-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="388f0-135">С учетом требований наших облачных клиентов государственных Teams в Office 365 для государственных организаций — GCC высокая и Teams в Enterprise планах.</span><span class="sxs-lookup"><span data-stu-id="388f0-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="388f0-136">Чтобы узнать, какие возможности доступны, см. таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="388f0-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="388f0-137">Microsoft Teams описание службы</span><span class="sxs-lookup"><span data-stu-id="388f0-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="388f0-138">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="388f0-138">Step 5.</span></span> <span data-ttu-id="388f0-139">Планирование управления</span><span class="sxs-lookup"><span data-stu-id="388f0-139">Plan for governance</span></span>

<span data-ttu-id="388f0-140">Определите свои требования к управлению и о том, как их можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="388f0-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="388f0-141">Дополнительные [сведения можно найти в](plan-teams-governance.md) Teams в области Планирование управления.</span><span class="sxs-lookup"><span data-stu-id="388f0-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="388f0-142">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="388f0-142">Decision point</span></span> |<ul><li><span data-ttu-id="388f0-143">Определите и документируйте требования к управлению, следуя инструкциям в [Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="388f0-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="388f0-144">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="388f0-144">Step 6.</span></span> <span data-ttu-id="388f0-145">Развертывание Teams для совместной работы</span><span class="sxs-lookup"><span data-stu-id="388f0-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="388f0-146">После того как вы оказалось в Office 365 для государственных организаций – GCC Высокая, следуйте рекомендованным путям развертывания, описанным в описании в Microsoft Teams [.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="388f0-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="388f0-147">Не забудьте взаимодействовать со своей командой по внедрению и управлению изменениями и Teams руководствами.</span><span class="sxs-lookup"><span data-stu-id="388f0-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="388f0-148">Вы также можете работать с [FastTrack](https://www.microsoft.com/fasttrack) или выбранным партнером, чтобы использовать службу.</span><span class="sxs-lookup"><span data-stu-id="388f0-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
