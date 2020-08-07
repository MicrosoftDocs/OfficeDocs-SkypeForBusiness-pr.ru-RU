---
title: Office 365 для государственных организаций — развертывание GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Руководство для ИТ-специалистов по развертыванию Office 365 в сущностях, которые обрабатывают данные, подлежащие регулированию за правительство США
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
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581250"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="a8d76-103">Планирование Office 365 для государственных организаций — развертывание GCC</span><span class="sxs-lookup"><span data-stu-id="a8d76-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="a8d76-104">Это руководство предназначено для ИТ-специалистов, которые управляют развертыванием Office 365 в компаниях, использующих федеральные и территориальные компании США, а также в тех или иных компаниях, которые обрабатывают данные, которые распространяются на нормативные акты и требования, где использование Office 365 правительством – GCC подходит для соответствия этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="a8d76-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="a8d76-105">Новая версия 26 марта 2020 г. не пропустите [для вас краткое руководство по началу](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)работы с GCC.</span><span class="sxs-lookup"><span data-stu-id="a8d76-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8d76-106">В Microsoft Teams существует значительная Копилка в онлайновых звонках, голосовых и видеоконференциях в связи с Coronavirus (COVID-19) Pandemic.</span><span class="sxs-lookup"><span data-stu-id="a8d76-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="a8d76-107">В ответ на безприоритетные звонки, а также для обеспечения бесперебойности и доступности Корпорация Майкрософт предоставляет пользователям Microsoft Teams GCC аудио-и видеосерверы, которые могут использовать обработку мощностей в наших коммерческих центрах обработки данных и в наших правительственных центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="a8d76-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="a8d76-108">Эти аудио-и видеосерверы находятся на серверах граничного сервера Microsoft Azure FedRAMP High Accreditation в Соединенных Штатах и не хранят контент клиентов.</span><span class="sxs-lookup"><span data-stu-id="a8d76-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="a8d76-109">Тем не менее, эти серверы обрабатывают звук и видео для звонков и конференций и работают в рамках нашего коммерческого персонала в течение этого временного периода.</span><span class="sxs-lookup"><span data-stu-id="a8d76-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="a8d76-110">Квалифицированные работники с монитором отслеживают эти серверы для потенциального доступа к данным клиентов, просматривая любые интерактивные журналы на этих серверах.</span><span class="sxs-lookup"><span data-stu-id="a8d76-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="a8d76-111">Квалифицированный персонал соответствует требованиям GCC для доступа к контенту клиента.</span><span class="sxs-lookup"><span data-stu-id="a8d76-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="a8d76-112">Дополнительные сведения о требованиях к блокировке можно найти в [описании службы GCC](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span><span class="sxs-lookup"><span data-stu-id="a8d76-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="a8d76-113">Благодарим вас за помощь, так как мы делаем шаги по обеспечению доступности и надежности наших услуг в чрезвычайных случаях.</span><span class="sxs-lookup"><span data-stu-id="a8d76-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="a8d76-114">Если в вашей организации уже достигнуто соответствие требованиям Office 365 для государственных организаций, и они были одобрены в программе, вы можете пропустить действия 1 и 2, а затем перейти прямо к шагу 3.</span><span class="sxs-lookup"><span data-stu-id="a8d76-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="a8d76-115">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="a8d76-115">Step 1.</span></span> <span data-ttu-id="a8d76-116">Определите, требуется ли Организация требованиям Office 365 для государственных учреждений — GCC и соответствует требованиям к приемлемости.</span><span class="sxs-lookup"><span data-stu-id="a8d76-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="a8d76-117">Среда Office 365 государственных учреждений – GCC обеспечивает соответствие требованиям для государственных служб США, включая FedRAMP, и требования к уголовной и федеральной информационной системе (типы данных CJI и FTI).</span><span class="sxs-lookup"><span data-stu-id="a8d76-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="a8d76-118">Помимо функций и возможностей Office 365, в организациях используются следующие возможности, которые являются уникальными для Office 365 для государственных организаций — GCC:</span><span class="sxs-lookup"><span data-stu-id="a8d76-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="a8d76-119">Данные клиента организации логически выделяться из содержимого клиента в коммерческих службах Office 365 от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8d76-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="a8d76-120">Сведения о клиентах вашей организации хранятся в Соединенных Штатах.</span><span class="sxs-lookup"><span data-stu-id="a8d76-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="a8d76-121">Доступ к контенту клиента организации ограничен сотрудниками Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8d76-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="a8d76-122">Office 365 государственных учреждений – GCC соответствует сертификациям и accreditations, которые необходимы для пользователей, использующих общедоступный сектор США.</span><span class="sxs-lookup"><span data-stu-id="a8d76-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="a8d76-123">Вы можете найти дополнительные сведения о правительственных учреждениях Office 365 для пользователей правительства США на [планах office 365 для государственных организаций](https://products.office.com/government/compare-office-365-government-plans), включая [требования к приемлемости](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="a8d76-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="a8d76-124">[Описание службы Office 365 США](https://technet.microsoft.com/library/mt774581.aspx) описывает преимущества платформы, которые выравниваются по всем требованиям, предъявляемым к требованиям, в Соединенных Штатах.</span><span class="sxs-lookup"><span data-stu-id="a8d76-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="a8d76-125">Вы можете перенести таблицы данных из описания службы в книгу Excel и добавить два столбца: **соответствующие моей организации y и n** и соответствующие **требованиям моей организации y/n**.</span><span class="sxs-lookup"><span data-stu-id="a8d76-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="a8d76-126">Затем вы можете просмотреть этот список с коллегами, чтобы убедиться, что эта услуга отвечает потребностям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a8d76-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точки принятия решений](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a8d76-128">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="a8d76-128">Decision points</span></span>|<ul><li><span data-ttu-id="a8d76-129">Решите, подходит ли Office 365 для государственных учреждений — GCC для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a8d76-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="a8d76-130">Убедитесь, что ваша организация соответствует требованиям к приемлемости.</span><span class="sxs-lookup"><span data-stu-id="a8d76-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="a8d76-131">Office 365 правительственные учреждения — GCC можно загрузить только в США.</span><span class="sxs-lookup"><span data-stu-id="a8d76-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="a8d76-132">Пользователи, не связанные с правительством США, могут выбрать один из нескольких [планов Office 365 для государственных учреждений](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="a8d76-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="a8d76-133">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="a8d76-133">Step 2.</span></span> <span data-ttu-id="a8d76-134">Установка Office 365 для государственных организаций — GCC</span><span class="sxs-lookup"><span data-stu-id="a8d76-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="a8d76-135">Если вы решили, что эта услуга является нужной для вашей организации, начните процесс [применения этой услуги здесь](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="a8d76-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="a8d76-136">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="a8d76-136">Step 3.</span></span> <span data-ttu-id="a8d76-137">Общие сведения о параметрах безопасности по умолчанию для Office 365 для государственных организаций.</span><span class="sxs-lookup"><span data-stu-id="a8d76-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="a8d76-138">Прежде чем вносить изменения в параметры безопасности по умолчанию, рекомендуется внимательно просмотреть [Параметры администратора и безопасности](enable-features-office-365.md) перед их изменением и оценить соответствие требованиям.</span><span class="sxs-lookup"><span data-stu-id="a8d76-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a8d76-140">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="a8d76-140">Decision point</span></span>|<ul><li><span data-ttu-id="a8d76-141">Решите, нужно ли вам изменить настройки безопасности Office 365 для государственных организаций (по умолчанию), чтобы понять, как можно вносить любые изменения.</span><span class="sxs-lookup"><span data-stu-id="a8d76-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="a8d76-142">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="a8d76-142">Step 4.</span></span> <span data-ttu-id="a8d76-143">Общие сведения о функциях, которые в настоящее время недоступны или отключены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a8d76-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="a8d76-144">В соответствии с требованиями наших облачных облаков в Office 365 правительство — GCC и планы предприятий.</span><span class="sxs-lookup"><span data-stu-id="a8d76-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="a8d76-145">Ознакомьтесь со следующей таблицей, в которой можно узнать, какие функции доступны.</span><span class="sxs-lookup"><span data-stu-id="a8d76-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="a8d76-146">Описание службы Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8d76-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="a8d76-147">После того как другие рабочие нагрузки будут полностью доступны в облаке GCC, они станут доступны в Teams, когда завершится вся дополнительная интеграция.</span><span class="sxs-lookup"><span data-stu-id="a8d76-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a8d76-149">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="a8d76-149">Decision point</span></span>|<ul><li><span data-ttu-id="a8d76-150">Решите, соответствует ли компонент Teams заданным требованиям Организации.</span><span class="sxs-lookup"><span data-stu-id="a8d76-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="a8d76-151">Шаг 5.</span><span class="sxs-lookup"><span data-stu-id="a8d76-151">Step 5.</span></span> <span data-ttu-id="a8d76-152">Планирование руководства</span><span class="sxs-lookup"><span data-stu-id="a8d76-152">Plan for governance</span></span>

<span data-ttu-id="a8d76-153">Определите требования к управлению и их возможности.</span><span class="sxs-lookup"><span data-stu-id="a8d76-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="a8d76-154">Для получения дополнительных сведений перейдите к разделу [планирование для руководства в Teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="a8d76-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Значок, изображающий точку принятия решения](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a8d76-156">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="a8d76-156">Decision point</span></span>|<ul><li><span data-ttu-id="a8d76-157">Определите и Задокументируйте требования к управлению, следуя рекомендациям, изложенным в разделе [планирование руководства для Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="a8d76-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="a8d76-158">Шаг 6.</span><span class="sxs-lookup"><span data-stu-id="a8d76-158">Step 6.</span></span> <span data-ttu-id="a8d76-159">Развертывание команд для совместной работы</span><span class="sxs-lookup"><span data-stu-id="a8d76-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="a8d76-160">После перехода на Office 365 правительство — GCC следуйте рекомендациям, описанным в разделе Развертывание [Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a8d76-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="a8d76-161">Не забудьте принять участие в команде внедрения и управления изменениями и Teams лидерами.</span><span class="sxs-lookup"><span data-stu-id="a8d76-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="a8d76-162">Вы также можете работать с [FastTrack](https://www.microsoft.com/fasttrack) или выбранным партнером, чтобы присвоить ему услуги.</span><span class="sxs-lookup"><span data-stu-id="a8d76-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="a8d76-163">Шаг 7.</span><span class="sxs-lookup"><span data-stu-id="a8d76-163">Step 7.</span></span> <span data-ttu-id="a8d76-164">Развертывание команд для собраний и голосовых сообщений</span><span class="sxs-lookup"><span data-stu-id="a8d76-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="a8d76-165">Это также очень выгодно для использования Teams с более широкой группой заинтересованных лиц, чтобы начать планирование собраний и [функций голосовой связи в облаке](cloud-voice-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="a8d76-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

