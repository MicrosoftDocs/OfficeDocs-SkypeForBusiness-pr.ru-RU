---
title: Teams для виртуальных посещений
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Настройка системы виртуальных посещений с помощью Microsoft Teams
ms.openlocfilehash: 6daa61ea44db02d48873a6fc494974c99573d0e8
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875179"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="a5a79-103">Виртуальные посещения с помощью Teams — интеграция с электронными медицинскими картами</span><span class="sxs-lookup"><span data-stu-id="a5a79-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="a5a79-104">Соединитель электронной медицинской записи (EHR) Microsoft Teams упрощает для врачей возможность виртуального посещения пациента или консультации с другим поставщиком в Teams непосредственно из системы EHR.</span><span class="sxs-lookup"><span data-stu-id="a5a79-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="a5a79-105">Microsoft Teams, созданная на базе облака Microsoft 365, обеспечивает простую и безопасную совместную работу и общение с помощью инструментов чата, видео, голоса и здравоохранения в едином центре, который поддерживает соответствие требованиям сертификации акта HIPAA, HITECH и других.</span><span class="sxs-lookup"><span data-stu-id="a5a79-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="a5a79-106">Платформа для общения и совместной работы Teams позволяет врачам легко преодолевать беспорядок несрочных фрагментированных систем, чтобы они могли уделять время оказанию наилучшего медицинского обслуживания.</span><span class="sxs-lookup"><span data-stu-id="a5a79-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="a5a79-107">Соединитель электронной медицинской записи Microsoft Teams может:</span><span class="sxs-lookup"><span data-stu-id="a5a79-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="a5a79-108">Запускайте виртуальные посещения Teams как с порталов поставщиков, так и с порталов пациентов.</span><span class="sxs-lookup"><span data-stu-id="a5a79-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="a5a79-109">Выполните обратную запись в метаданные электронной медицинской карты при подключении и отключении событий для включения автоматического аудита и сохранения записей.</span><span class="sxs-lookup"><span data-stu-id="a5a79-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="a5a79-110">Интегрируются в существующие медицинские процессы и процессы пациентов, позволяя им использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="a5a79-111">Посмотрите видео о том, как управлять виртуальными посещениями с портала электронной медицинской карты.</span><span class="sxs-lookup"><span data-stu-id="a5a79-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="a5a79-112">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="a5a79-112">Before you begin</span></span>

<span data-ttu-id="a5a79-113">Перед интеграцией соединителя электронной медицинской карты необходимо убедиться в том, что вами были соблюдены следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="a5a79-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="a5a79-114">Доступ к приложению Microsoft Teams в [магазине Epic — App Orchard](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="a5a79-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="a5a79-115">Активная подписка на Microsoft Cloud для здравоохранения или подписка на отдельное предложение соединителя электронной медицинской карты Microsoft Teams (применяется только во время производственного тестирования).</span><span class="sxs-lookup"><span data-stu-id="a5a79-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="a5a79-116">Пользователи должны иметь соответствующую лицензию на Microsoft 365 или Office 365, которая включает собрания Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="a5a79-117">Microsoft Teams следует внедрять и использовать внутри организации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="a5a79-118">Организации должны иметь версию Epic с ноября 2018 г. или более позднюю.</span><span class="sxs-lookup"><span data-stu-id="a5a79-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="a5a79-119">Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="a5a79-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="a5a79-120">Вам также потребуются сведения от следующих пользователей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="a5a79-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="a5a79-121">Администратор Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5a79-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="a5a79-122">Аналитик клиентов Epic</span><span class="sxs-lookup"><span data-stu-id="a5a79-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="a5a79-123">Просмотрите [руководство по интеграции telehealth Для Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) с вашим техническим специалистом, специалистом по Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="a5a79-124">Убедитесь, что все предварительные требования выполнены.</span><span class="sxs-lookup"><span data-stu-id="a5a79-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="a5a79-125">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="a5a79-125">Connector setup</span></span>

<span data-ttu-id="a5a79-126">Для настройки соединители необходимо:</span><span class="sxs-lookup"><span data-stu-id="a5a79-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="a5a79-127">Запустить портал конфигурации соединителя электронной медицинской карты</span><span class="sxs-lookup"><span data-stu-id="a5a79-127">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="a5a79-128">Сведения о конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5a79-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="a5a79-129">Утвердить или просмотреть конфигурацию</span><span class="sxs-lookup"><span data-stu-id="a5a79-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="a5a79-130">Просмотреть и завершить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="a5a79-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="a5a79-131">Запустить портал конфигурации соединителя электронной медицинской карты</span><span class="sxs-lookup"><span data-stu-id="a5a79-131">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="a5a79-132">Настройка медицинской организации для запуска виртуальных посещений с помощью Microsoft Teams начинается с запуска портала конфигурации соединителя электронной медицинской карты.</span><span class="sxs-lookup"><span data-stu-id="a5a79-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="a5a79-133">Для тестирования интеграции настраивается одна или несколько организаций.</span><span class="sxs-lookup"><span data-stu-id="a5a79-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="a5a79-134">Настройте тестовый и рабочий URL-адреса на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="a5a79-135">Прежде чем переходить к производственной среде, протестируйте интеграцию из тестовой среды Epic.</span><span class="sxs-lookup"><span data-stu-id="a5a79-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="a5a79-136">URL-адрес конфигурация соединителя электронной медицинской карты: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a5a79-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="a5a79-137">Администратор Microsoft 365 и аналитик клиентов Epic из вашей организации должны выполнить действия по интеграции и информации на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="a5a79-138">Для настройки Epic обратитесь к ресурсам технического специалиста Epic, назначенного вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="a5a79-139">Сведения о конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5a79-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="a5a79-140">Этот шаг должен быть выполнен **администратором Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="a5a79-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="a5a79-141">Администратор Microsoft 365 должен запустить портал конфигурации соединителя и войти с помощью учетных данных Майкрософт, чтобы начать процесс конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="a5a79-142">Для выполнения этого шага администратор Microsoft 365 должен получить действительный базовый URL-адрес ресурсов быстрого взаимодействия в сфере здравоохранения (FHIR) от вашего технического специалиста Epic и имя пользователя аналитика клиентов Epic, который будет утверждать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a5a79-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="a5a79-143">Администратор Microsoft 365 должен запустить страницу конфигурации соединителя и войти с помощью учетных данных Майкрософт, чтобы начать процесс конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="a5a79-144">Базовый URL-адрес FHIR — это статический адрес, соответствующий конечной точке API FHIR сервера.</span><span class="sxs-lookup"><span data-stu-id="a5a79-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="a5a79-145">Пример URL-адреса — `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span><span class="sxs-lookup"><span data-stu-id="a5a79-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="a5a79-146">Имя утверждающего конфигурации — это имя аналитика клиентов Epic, который будет отвечать за утверждение конфигурации на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="a5a79-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="a5a79-147">Аналитик клиентов Epic — это сотрудник вашей организации, который имеет доступ для входа в Epic.</span><span class="sxs-lookup"><span data-stu-id="a5a79-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![Имя утверждающего конфигурацию выбирается из списка в соединителе EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="a5a79-149">Утверждение или просмотр конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5a79-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="a5a79-150">Аналитик клиента Epic вашей медицинской организации, добавленный в качестве утверждающего, теперь должен использовать тот же URL-адрес соединителя электронной медицинской карты, что и на предыдущем шаге, для входа с использованием учетных данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5a79-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="a5a79-151">После успешной проверки утверждающему будет предложено войти в систему, используя учетные данные Epic, для проверки организации Epic.</span><span class="sxs-lookup"><span data-stu-id="a5a79-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="a5a79-152">Администратор Microsoft 365 и аналитик клиентов Epic в вашей организации могут быть одним и тем же лицом.</span><span class="sxs-lookup"><span data-stu-id="a5a79-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="a5a79-153">В этом случае добавьте собственное имя пользователя в качестве утверждающего.</span><span class="sxs-lookup"><span data-stu-id="a5a79-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="a5a79-154">Вам все равно потребуется войти в Epic, чтобы подтвердить свой доступ.</span><span class="sxs-lookup"><span data-stu-id="a5a79-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="a5a79-155">Вход Epic используется только для проверки базового URL-адреса FHIR.</span><span class="sxs-lookup"><span data-stu-id="a5a79-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="a5a79-156">Корпорация Майкрософт не будет хранить учетные данные или получать доступ к данным EHR с помощью этого входа.</span><span class="sxs-lookup"><span data-stu-id="a5a79-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Проверка и утверждение конфигурации учетных данных.](../../media/approve-view-configuration.png)

<span data-ttu-id="a5a79-158">После успешного входа в Epic аналитику клиента Epic **необходимо** утвердить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a5a79-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="a5a79-159">Если конфигурация неверна, администратор Microsoft 365 сможет изменить исходную конфигурацию, снова войдя на портал соединителя электронной медицинской карты Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5a79-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Подтвердите, что соединитель электронной медицинской карты настроен и возможность изменения конфигурации.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="a5a79-161">Просмотр и завершение конфигурации</span><span class="sxs-lookup"><span data-stu-id="a5a79-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="a5a79-162">После утверждения сведений о конфигурации администратором Epic вам будут представлены записи интеграции для запуска пациентов и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="a5a79-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="a5a79-163">Эти записи необходимы для завершения настройки виртуального посещения в Epic.</span><span class="sxs-lookup"><span data-stu-id="a5a79-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="a5a79-164">Дополнительные сведения можно найти в руководстве по интеграции Epic-Microsoft Teams Telehealth.</span><span class="sxs-lookup"><span data-stu-id="a5a79-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="a5a79-165">В любое время аналитик клиентов Microsoft 365 или Epic может войти на портал конфигурации, чтобы просмотреть записи интеграции и при необходимости изменить конфигурацию организации.</span><span class="sxs-lookup"><span data-stu-id="a5a79-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Отображаются сведения об интеграции.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="a5a79-167">Процесс утверждения должен быть завершен аналитиком клиентов Epic для каждого URL-адреса FHIR, настроенного администратором Майкрософт ранее.</span><span class="sxs-lookup"><span data-stu-id="a5a79-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Сведения о конфигурации утверждены.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="a5a79-169">Запуск виртуальных посещений Teams</span><span class="sxs-lookup"><span data-stu-id="a5a79-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="a5a79-170">После выполнения действий соединителя электронной медицинской карты и конфигурации Epic ваша организация будет готова поддерживать видео посещения с помощью Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-170">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="a5a79-171">Предварительные условия для виртуального посещения</span><span class="sxs-lookup"><span data-stu-id="a5a79-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="a5a79-172">Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="a5a79-172">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="a5a79-173">Медицинская организация должна выполнить настройку между организацией Epic и организацией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5a79-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="a5a79-174">Взаимодействие с поставщиком</span><span class="sxs-lookup"><span data-stu-id="a5a79-174">Provider experience</span></span>

<span data-ttu-id="a5a79-175">Поставщики медицинских услуг из вашей организации также могут присоединяться к виртуальным посещениям Microsoft Teams из своих приложений поставщика Epic (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="a5a79-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="a5a79-176">Кнопка **Начать виртуальное посещение** внедрена в поток поставщика.</span><span class="sxs-lookup"><span data-stu-id="a5a79-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="a5a79-177">Основные функции взаимодействия с поставщиком:</span><span class="sxs-lookup"><span data-stu-id="a5a79-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="a5a79-178">Поставщики могут присоединяться к виртуальным посещениям с помощью поддерживаемых браузеров или приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="a5a79-179">Поставщики должны один раз войти в свою учетную запись Microsoft 365 при первом виртуальном посещении.</span><span class="sxs-lookup"><span data-stu-id="a5a79-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="a5a79-180">После однократного входа поставщик будет перенаправлен сразу на виртуальную встречу в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-180">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="a5a79-181">(Поставщик должен быть авторизован в Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="a5a79-181">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="a5a79-182">Провайдер может видеть в режиме реального времени обновления участников, подключающихся и отключающихся от встречи.</span><span class="sxs-lookup"><span data-stu-id="a5a79-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="a5a79-183">Поставщик может видеть, когда пациент подключен к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="a5a79-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Взаимодействие с поставщиком во время виртуального посещения с пациентом](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="a5a79-185">Взаимодействие с пациентом</span><span class="sxs-lookup"><span data-stu-id="a5a79-185">Patient experience</span></span>

<span data-ttu-id="a5a79-186">Соединитель позволяет пациентам присоединяться к виртуальным посещениям через MyChart в Интернете и на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="a5a79-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="a5a79-187">Во время приема пациенты могут начать виртуальное посещение из MyChart с помощью кнопки **Начать виртуальное посещение**.</span><span class="sxs-lookup"><span data-stu-id="a5a79-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="a5a79-188">Основные функции взаимодействия с пациентом:</span><span class="sxs-lookup"><span data-stu-id="a5a79-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="a5a79-189">Пациенты могут присоединяться к виртуальным посещениям из современных веб-браузеров на настольных компьютерах и мобильных устройствах без установки приложения.</span><span class="sxs-lookup"><span data-stu-id="a5a79-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="a5a79-190">Пациенты могут присоединиться к виртуальным посещениям одним щелчком мыши. Другие учетные записи или выполнение входа не требуются.</span><span class="sxs-lookup"><span data-stu-id="a5a79-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="a5a79-191">Для запуска виртуального посещения пациентам не требуется создавать учетную запись Майкрософт или выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="a5a79-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="a5a79-192">Пациенты будут помещены в "зал ожидания" до тех пор, пока поставщик медицинских услуг не присоединится к встрече и не допустит их к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="a5a79-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="a5a79-193">Перед присоединением к виртуальному посещению в "зале ожидания" доступно тестирование видео и микрофона.</span><span class="sxs-lookup"><span data-stu-id="a5a79-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Взаимодействие с пациентом во время виртуального посещения](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="a5a79-195">Epic, MyChart, Haiku и Canto являются товарными знаками корпорации Epic Systems.</span><span class="sxs-lookup"><span data-stu-id="a5a79-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="a5a79-196">Конфиденциальность и расположение данных</span><span class="sxs-lookup"><span data-stu-id="a5a79-196">Privacy and location of data</span></span>

<span data-ttu-id="a5a79-197">Интеграция Teams в системы электронной медицинской карты оптимизирует объем данных, используемых и хранимых во время интеграции и потоков виртуальных посещений.</span><span class="sxs-lookup"><span data-stu-id="a5a79-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="a5a79-198">Решение соответствует общим принципам и рекомендациям по обеспечению конфиденциальности и управлению данными Teams, изложенным в разделе "Конфиденциальность Teams".</span><span class="sxs-lookup"><span data-stu-id="a5a79-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="a5a79-199">Соединитель электронной медицинской карты Microsoft Teams не хранит и не передает какие-либо идентифицирующие личные сведения или медицинские записи пациентов или поставщиков медицинских услуг из системы электронной медицинской карты.</span><span class="sxs-lookup"><span data-stu-id="a5a79-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="a5a79-200">Единственные данные, которые хранятся в соединителе электронной медицинской карты, — это уникальный идентификатор пользователя электронной медицинской карты, который используется во время настройки собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="a5a79-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="a5a79-201">Уникальный идентификатор пользователя электронной медицинской карты хранится в одном из трех географических регионов, описанных в статье [Где хранятся данные клиентов Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span><span class="sxs-lookup"><span data-stu-id="a5a79-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="a5a79-202">Все беседы, записи и другие данные, которые участники собрания ввели в Teams, хранятся в соответствии с существующими политиками хранения.</span><span class="sxs-lookup"><span data-stu-id="a5a79-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="a5a79-203">Дополнительные сведения о расположении данных в Microsoft Teams см. в статье [Расположения данных в Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a5a79-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
