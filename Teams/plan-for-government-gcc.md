---
title: 'Microsoft 365 для государственных органов : развертывание GCC'
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Руководство для ИТ-специалистов по развертыванию Microsoft 365 в сущностям, обрабатывающих данные в правительственных учреждениях США
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117837"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="58f10-103">Планирование развертывания Microsoft 365 для государственных органов — GCC</span><span class="sxs-lookup"><span data-stu-id="58f10-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="58f10-104">Это руководство подходит для ИТ-специалистов, которые являются управляющими развертыванием Microsoft 365 в федеральных, региональных, локальных, сущно-правовых единицах или в разуных организациях государственных организаций, которые обрабатывают данные, в отношении которых регламентирование и требования государственных организаций, в которых использование Microsoft 365 для государственных организаций (GCC) подходит для обеспечения этих требований.</span><span class="sxs-lookup"><span data-stu-id="58f10-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="58f10-105">26 марта 2020 г. Не пропустите наше краткое руководство по началу загрузки для [GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)</span><span class="sxs-lookup"><span data-stu-id="58f10-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58f10-106">В Microsoft Teams огромное количество звонков в Интернете и аудио- и видеоконференций происходит из-за того, что существует возможность coVID-19.</span><span class="sxs-lookup"><span data-stu-id="58f10-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="58f10-107">В ответ на рост звонков в связи с увеличением масштаба и обеспечением непрерывности и доступности корпорация Майкрософт разрешает аудио- и видеособраниям Microsoft Teams GCC использовать вычислительную мощность в наших коммерческих центрах обработки данных, а также в центрах обработки данных государственных организаций.</span><span class="sxs-lookup"><span data-stu-id="58f10-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="58f10-108">Эти аудио- и видеофайлы находятся на границах пограничного сервера Microsoft Azure FedRAMP в США и не хранят контент клиента.</span><span class="sxs-lookup"><span data-stu-id="58f10-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="58f10-109">Однако эти серверы обрабатывают звук и видео для звонков и конференций и работают в рамках наших коммерческих сотрудников в течение этого промежуточного периода.</span><span class="sxs-lookup"><span data-stu-id="58f10-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="58f10-110">Квалифицированные и экранные сотрудники отслеживают на этих серверах потенциальный доступ к данным клиентов, просматривая интерактивные входы на эти серверы.</span><span class="sxs-lookup"><span data-stu-id="58f10-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="58f10-111">Квалифицированные сотрудники отвечают требованиям GCC для доступа к контенту клиента.</span><span class="sxs-lookup"><span data-stu-id="58f10-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="58f10-112">Подробные сведения о требованиях к камере см. в описании [службы GCC.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="58f10-112">For details about screening requirements, see the [GCC service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="58f10-113">Благодарим вас за поддержку, так как мы берем за нее все необходимые меры для обеспечения надежности и надежности служб в указанные периоды.</span><span class="sxs-lookup"><span data-stu-id="58f10-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="58f10-114">Если ваша организация уже выполнила требования к правомочности на Microsoft 365 для государственных организаций, а затем применяется к программе и принимается в нее, можно пропустить шаги 1 и 2 и перейти непосредственно к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="58f10-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="58f10-115">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="58f10-115">Step 1.</span></span> <span data-ttu-id="58f10-116">Определите, требуется ли вашей организации Microsoft 365 для государственных организаций — GCC и соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="58f10-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="58f10-117">Среда Microsoft 365 Government — GCC обеспечивает соответствие требованиям государственных органов США к облачным службам, включая FedRAMP Moderate, а также требования для преступную и федеральной системы сведений о налогах (CJI и FTI).</span><span class="sxs-lookup"><span data-stu-id="58f10-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="58f10-118">В дополнение к функциям и возможностям Microsoft 365 организации получают следующие уникальные возможности Microsoft 365 для государственных организаций (GCC).</span><span class="sxs-lookup"><span data-stu-id="58f10-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="58f10-119">Содержимое вашей организации от контента клиентов логически отделяется от контента клиентов в коммерческих службах Microsoft 365 от Корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="58f10-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="58f10-120">Содержимое вашей организации хранится в США.</span><span class="sxs-lookup"><span data-stu-id="58f10-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="58f10-121">Доступ к содержимому клиентов вашей организации ограничен экранными данными сотрудников Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="58f10-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="58f10-122">Microsoft 365 для государственных организаций: GCC соответствует сертификациям и секторам, которые требуются клиентам государственного сектора США.</span><span class="sxs-lookup"><span data-stu-id="58f10-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="58f10-123">Дополнительные сведения о предложении Microsoft 365 government — GCC для государственных органов США можно найти на веб-сайте планов [Microsoft 365](https://products.office.com/government/compare-office-365-government-plans)для государственных органов, включая требования к [приемлемости.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="58f10-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="58f10-124">В [описании службы Microsoft 365 US Government](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) описаны преимущества платформы, в центре которых находятся требования к обеспечению соответствия требованиям в США.</span><span class="sxs-lookup"><span data-stu-id="58f10-124">The [Microsoft 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="58f10-125">Может потребоваться перенести таблицы сведений из описания службы в книгу Excel и добавить два столбца: "Релевантные" для моей организации **"Y/N"** и "Соответствует потребностям моей **организации" "Y/N".**</span><span class="sxs-lookup"><span data-stu-id="58f10-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="58f10-126">Затем вы можете вместе с коллегами просмотреть этот список, чтобы подтвердить, что эта служба соответствует потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58f10-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="58f10-128">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="58f10-128">Decision points</span></span>|<ul><li><span data-ttu-id="58f10-129">Определите, подходит ли microsoft 365 government — GCC для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58f10-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="58f10-130">Подтвердите, что ваша организация соответствует требованиям.</span><span class="sxs-lookup"><span data-stu-id="58f10-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="58f10-131">Microsoft 365 для государственных органов . GCC доступна только в США.</span><span class="sxs-lookup"><span data-stu-id="58f10-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="58f10-132">Клиенты из других стран могут выбрать один из нескольких планов [Microsoft 365 для государственных органов.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="58f10-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="58f10-133">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="58f10-133">Step 2.</span></span> <span data-ttu-id="58f10-134">Подача заявки на microsoft 365 для государственных ( GCC)</span><span class="sxs-lookup"><span data-stu-id="58f10-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="58f10-135">Если вы решили, что эта служба под вашей организацией, начните подачу заявки на получение этой [службы здесь.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="58f10-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="58f10-136">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="58f10-136">Step 3.</span></span> <span data-ttu-id="58f10-137">Понимание параметров безопасности Microsoft 365 для государственных учреждения и GCC по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58f10-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="58f10-138">Рекомендуем внимательно и тщательно и внести изменения в параметры безопасности и администратора, а также учесть влияние на соблюдение требований, прежде чем вносить изменения в параметры безопасности по умолчанию. [](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="58f10-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="58f10-140">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="58f10-140">Decision point</span></span>|<ul><li><span data-ttu-id="58f10-141">Решите, нужно ли изменить какие-либо стандартные параметры безопасности Microsoft 365 для государственных органов ( GCC), чтобы сначала понять, как влияют на них изменения.</span><span class="sxs-lookup"><span data-stu-id="58f10-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="58f10-142">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="58f10-142">Step 4.</span></span> <span data-ttu-id="58f10-143">Просмотр возможностей, которые недоступны или отключены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58f10-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="58f10-144">В требованиях наших облачных правительственных органов существуют некоторые различия между планами Microsoft 365 для государственных органов — GCC и Корпоративный.</span><span class="sxs-lookup"><span data-stu-id="58f10-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="58f10-145">Чтобы узнать, какие возможности доступны, см. таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="58f10-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="58f10-146">Описание службы Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58f10-146">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="58f10-147">Когда другие рабочие нагрузки станут полностью доступны в облаке GCC, они станут доступны в Teams после завершения всех дополнительных работ по интеграции.</span><span class="sxs-lookup"><span data-stu-id="58f10-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="58f10-149">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="58f10-149">Decision point</span></span>|<ul><li><span data-ttu-id="58f10-150">Определите, соответствует ли набор функций Teams потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58f10-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="58f10-151">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="58f10-151">Step 5.</span></span> <span data-ttu-id="58f10-152">Планирование управления</span><span class="sxs-lookup"><span data-stu-id="58f10-152">Plan for governance</span></span>

<span data-ttu-id="58f10-153">Определите свои требования для управления и определите, как их можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="58f10-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="58f10-154">Дополнительные сведения [можно найти в области "Планирование управления в Teams".](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="58f10-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="58f10-156">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="58f10-156">Decision point</span></span>|<ul><li><span data-ttu-id="58f10-157">Определите и за документируйте требования к управлению, следуя инструкциям плана управления [в Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="58f10-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="58f10-158">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="58f10-158">Step 6.</span></span> <span data-ttu-id="58f10-159">Развертывание Teams для совместной работы</span><span class="sxs-lookup"><span data-stu-id="58f10-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="58f10-160">После того как вы войду в Microsoft 365 для государственных структур — GCC, следуйте рекомендуемым путям развертывания, описанным в описании развертывания [Microsoft Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="58f10-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="58f10-161">Обязательно взаимодействовайте с командой по внедрению и управлению изменениями, а также с командами для управления изменениями и командами Teams.</span><span class="sxs-lookup"><span data-stu-id="58f10-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="58f10-162">Вы также можете использовать [службу FastTrack](https://www.microsoft.com/fasttrack) или выбранного партнера.</span><span class="sxs-lookup"><span data-stu-id="58f10-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="58f10-163">Шаг 7.</span><span class="sxs-lookup"><span data-stu-id="58f10-163">Step 7.</span></span> <span data-ttu-id="58f10-164">Развертывание Teams для собраний и голосовых команд</span><span class="sxs-lookup"><span data-stu-id="58f10-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="58f10-165">Это также отличное время, чтобы использовать Teams вместе с более широкой группой заинтересованных лиц, чтобы приступить к планированию развертывание собраний и функций облачного [голосового связи.](./cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="58f10-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](./cloud-voice-landing-page.md).</span></span>