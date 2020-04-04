---
title: Развертывание Microsoft 365 для государственных организаций (DoD)
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Руководство для ИТ-специалистов по развертыванию Office 365 в сущностях, которые обрабатывают данные, подлежащие регулированию США по требованию.
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
ms.openlocfilehash: 33c3afcde009a6a8cedb1226dbc6383e29e76730
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137799"
---
# <a name="plan-for-microsoft-365-government---dod-deployments"></a><span data-ttu-id="98f78-103">Планирование развертывания Microsoft 365 для государственных организаций (DoD)</span><span class="sxs-lookup"><span data-stu-id="98f78-103">Plan for Microsoft 365 Government - DoD deployments</span></span>

<span data-ttu-id="98f78-104">Это руководство предназначено для ИТ-специалистов, которые управляют развертыванием Office 365 в правительственных учреждениях США и других субъектах, которые обрабатывают данные, которые распространяются на нормативные акты и требования, в которых используется компания Microsoft 365 правительством – DoD подходит для соответствия этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="98f78-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="98f78-105">Если в вашей организации уже достигнуто соответствие требованиям для государственных организаций Microsoft 365, и они были одобрены в программе, вы можете пропустить действия 1 и 2, а затем перейти прямо к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="98f78-105">If your organization has already met the Microsoft 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="98f78-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="98f78-106">Step 1.</span></span> <span data-ttu-id="98f78-107">Определите, требуется ли организациям Microsoft 365 правительством (DoD) и удовлетворяют требованиям к приемлемости.</span><span class="sxs-lookup"><span data-stu-id="98f78-107">Determine whether your organization needs Microsoft 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="98f78-108">Среда государственных учреждений Microsoft 365 (DoD) обеспечивает соответствие требованиям, предъявляемым к государственным услугам США, для облачных служб.</span><span class="sxs-lookup"><span data-stu-id="98f78-108">The Microsoft 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="98f78-109">В дополнение к преимуществам функций и возможностей Office 365, в организациях используются следующие возможности, которые являются уникальными для государственных организаций Microsoft 365 — DoD:</span><span class="sxs-lookup"><span data-stu-id="98f78-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – DoD:</span></span>

- <span data-ttu-id="98f78-110">Данные клиента организации логически выделяться из содержимого клиента в коммерческих службах Office 365 от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="98f78-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="98f78-111">Сведения о клиентах вашей организации хранятся в Соединенных Штатах.</span><span class="sxs-lookup"><span data-stu-id="98f78-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="98f78-112">Доступ к контенту клиента организации ограничен сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="98f78-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="98f78-113">Microsoft 365, правительство – DoD соответствует сертификациям и accreditations, которые необходимы для пользователей с общественным сектором США.</span><span class="sxs-lookup"><span data-stu-id="98f78-113">Microsoft 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="98f78-114">Вы можете найти дополнительные сведения о правительственных учреждениях Microsoft 365 (для государственных организаций, использующих правительство США, в [планах Office 365](https://products.office.com/government/compare-office-365-government-plans), включая [требования к приемлемости](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="98f78-114">You can find more information about the Microsoft 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="98f78-115">[Описание службы Office 365 США](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) описывает преимущества платформы, которые выравниваются по центру в соответствии с требованиями к требованиям к собранию в Соединенных Штатах.</span><span class="sxs-lookup"><span data-stu-id="98f78-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="98f78-116">Вы можете перенести таблицы данных из описания службы в книгу Excel и добавить два столбца: **соответствующие моей организации y и n** и соответствующие **требованиям моей организации y/n**.</span><span class="sxs-lookup"><span data-stu-id="98f78-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="98f78-117">Затем вы можете просмотреть этот список с коллегами, чтобы убедиться, что эта услуга отвечает потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="98f78-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="98f78-119">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="98f78-119">Decision points</span></span>|<ul><li><span data-ttu-id="98f78-120">Решите, подходит ли компания Microsoft 365 для государственных организаций по требованию для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="98f78-120">Decide whether Microsoft 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="98f78-121">Убедитесь, что ваша организация соответствует требованиям к приемлемости.</span><span class="sxs-lookup"><span data-stu-id="98f78-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="98f78-122">Microsoft 365, правительство — DoD – это только в США.</span><span class="sxs-lookup"><span data-stu-id="98f78-122">Microsoft 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="98f78-123">Пользователи, не связанные с правительством США, могут выбрать один из нескольких [планов Office 365 для государственных учреждений](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="98f78-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---dod"></a><span data-ttu-id="98f78-124">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="98f78-124">Step 2.</span></span> <span data-ttu-id="98f78-125">Применимо для государственных учреждений Microsoft 365 (DoD)</span><span class="sxs-lookup"><span data-stu-id="98f78-125">Apply for Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="98f78-126">Если вы решили, что эта услуга является нужной для вашей организации, начните процесс [применения для этой услуги](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="98f78-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---dod-default-security-settings"></a><span data-ttu-id="98f78-127">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="98f78-127">Step 3.</span></span> <span data-ttu-id="98f78-128">Общие сведения о параметрах безопасности по умолчанию для государственных учреждений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98f78-128">Understand Microsoft 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="98f78-129">Прежде чем вносить изменения в параметры безопасности по умолчанию, рекомендуется внимательно просмотреть [Параметры администратора и безопасности](enable-features-office-365.md) перед их изменением и оценить соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="98f78-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="98f78-131">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="98f78-131">Decision point</span></span>|<ul><li><span data-ttu-id="98f78-132">Решите, нужно ли вам изменить какие-либо настройки безопасности Microsoft 365 для государственных учреждений по умолчанию, а также решить, как это повлияет на любые изменения, которые могут быть внесены.</span><span class="sxs-lookup"><span data-stu-id="98f78-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---dod"></a><span data-ttu-id="98f78-133">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="98f78-133">Step 4.</span></span> <span data-ttu-id="98f78-134">Общие сведения о возможностях групп, которые в настоящее время поддерживаются в Microsoft 365 государственных учреждений (DoD)</span><span class="sxs-lookup"><span data-stu-id="98f78-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - DoD</span></span>

<span data-ttu-id="98f78-135">В соответствии с требованиями наших облачных облаков в Microsoft 365 правительством (DoD) и Teams в корпоративных планах есть различия между Teams.</span><span class="sxs-lookup"><span data-stu-id="98f78-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="98f78-136">Ознакомьтесь со следующей таблицей, в которой можно узнать, какие функции доступны.</span><span class="sxs-lookup"><span data-stu-id="98f78-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="98f78-137">Описание службы Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98f78-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="98f78-138">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="98f78-138">Step 5.</span></span> <span data-ttu-id="98f78-139">Планирование руководства</span><span class="sxs-lookup"><span data-stu-id="98f78-139">Plan for governance</span></span>

<span data-ttu-id="98f78-140">Определите требования к управлению и их возможности.</span><span class="sxs-lookup"><span data-stu-id="98f78-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="98f78-141">Для получения дополнительных сведений перейдите к разделу [планирование для руководства в Teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="98f78-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="98f78-142">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="98f78-142">Decision point</span></span> |<ul><li><span data-ttu-id="98f78-143">Определите и Задокументируйте требования к управлению, следуя рекомендациям, изложенным в разделе [планирование руководства для Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="98f78-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="98f78-144">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="98f78-144">Step 6.</span></span> <span data-ttu-id="98f78-145">Развертывание команд для совместной работы</span><span class="sxs-lookup"><span data-stu-id="98f78-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="98f78-146">После того как вы перейдете на веб-контроллер Microsoft 365 правительством (DoD), следуйте рекомендациям, описанным в разделе Развертывание [Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="98f78-146">After you've been onboarded to Microsoft 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="98f78-147">Не забудьте принять участие в команде внедрения и управления изменениями и Teams лидерами.</span><span class="sxs-lookup"><span data-stu-id="98f78-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="98f78-148">Вы также можете работать с [FastTrack](https://www.microsoft.com/fasttrack) или выбранным партнером, чтобы присвоить ему услуги.</span><span class="sxs-lookup"><span data-stu-id="98f78-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
