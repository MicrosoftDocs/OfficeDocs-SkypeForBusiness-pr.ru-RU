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
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Настройка системы виртуальных посещений с помощью Microsoft Teams
ms.openlocfilehash: 4c8511939532a448d5229865618aa308494c7a42
ms.sourcegitcommit: 4bf85d91befb56566130731198518c103a53ebc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2021
ms.locfileid: "50101337"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="d4f12-103">Виртуальные посещения с помощью Teams — интеграция с EHR</span><span class="sxs-lookup"><span data-stu-id="d4f12-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="d4f12-104">Соединителей электронной записи здравоохранения Microsoft Teams (EHR) можно легко запустить виртуальное посещение пациентов или обратиться к другому поставщику в Teams непосредственно из системы EHR.</span><span class="sxs-lookup"><span data-stu-id="d4f12-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="d4f12-105">Microsoft Teams, встроенный в облако Microsoft 365, обеспечивает простую и безопасную совместную работу и общение с чатом, видеосвязь, голосовой связью и медицинскими инструментами в едином центре, который поддерживает соответствие с сертификацией HIPAA, HITECH и другими программами.</span><span class="sxs-lookup"><span data-stu-id="d4f12-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="d4f12-106">Платформа для коммуникаций и совместной работы Teams позволяет клиникам легко перегромождать негроможденные системы и тратить время на предоставление наилучшей помощи.</span><span class="sxs-lookup"><span data-stu-id="d4f12-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="d4f12-107">Соединитер электронной записи здравоохранения Microsoft Teams (EHR) может:</span><span class="sxs-lookup"><span data-stu-id="d4f12-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="d4f12-108">Запускать виртуальные визиты Teams как с порталов поставщика услуг, так и с порталов пациентов.</span><span class="sxs-lookup"><span data-stu-id="d4f12-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="d4f12-109">Записывая запись в метаданные EHR при подключении и отключении событий для автоматического аудита и сохраняемой записи.</span><span class="sxs-lookup"><span data-stu-id="d4f12-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="d4f12-110">Интегрируются в существующие рабочий процессы клиники и пациентов, позволяя им использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="d4f12-111">Посмотрите видео о том, как управлять виртуальными посещениями с портала EHR.</span><span class="sxs-lookup"><span data-stu-id="d4f12-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="d4f12-112">До начала работы</span><span class="sxs-lookup"><span data-stu-id="d4f12-112">Before you begin</span></span>

<span data-ttu-id="d4f12-113">Перед интеграцией соединитела EHR необходимо убедиться в том, что у вас есть следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="d4f12-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="d4f12-114">Access to use to use to the Microsoft Teams app in [Market's App Marketplace.](https://apporchard.epic.com/Gallery?id=6153)</span><span class="sxs-lookup"><span data-stu-id="d4f12-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="d4f12-115">Активная подписка на Microsoft Cloud для здравоохранения или подписка на автономные предложения Microsoft Teams EHR Connector (которые применяются только во время тестирования в производственной сфере).</span><span class="sxs-lookup"><span data-stu-id="d4f12-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="d4f12-116">У пользователей должна быть соответствующая лицензия Microsoft 365 или Office 365, которая включает собрания Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="d4f12-117">Microsoft Teams следует принятия и использования в организации.</span><span class="sxs-lookup"><span data-stu-id="d4f12-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="d4f12-118">У организаций должна быть версия с ноябрь 2018 г. или более поздней.</span><span class="sxs-lookup"><span data-stu-id="d4f12-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="d4f12-119">Ваши системы должны соответствовать всем требованиям [к программному обеспечению и браузеру.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="d4f12-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="d4f12-120">Вам также потребуется информация от следующих людей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="d4f12-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="d4f12-121">Администратор Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4f12-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="d4f12-122">Веха аналитика клиентов</span><span class="sxs-lookup"><span data-stu-id="d4f12-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="d4f12-123">Запросите своего технических специалиста по Epic-Microsoft интеграции с телетайлами Teams, доступное в Marketplace.</span><span class="sxs-lookup"><span data-stu-id="d4f12-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="d4f12-124">Настройка соедините камеры</span><span class="sxs-lookup"><span data-stu-id="d4f12-124">Connector setup</span></span>

<span data-ttu-id="d4f12-125">Для настройки соединители требуется:</span><span class="sxs-lookup"><span data-stu-id="d4f12-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="d4f12-126">Запуск портала настройки соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="d4f12-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="d4f12-127">Сведения о конфигурации</span><span class="sxs-lookup"><span data-stu-id="d4f12-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="d4f12-128">Утверждение или просмотр конфигурации</span><span class="sxs-lookup"><span data-stu-id="d4f12-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="d4f12-129">Просмотр и завершить настройку</span><span class="sxs-lookup"><span data-stu-id="d4f12-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="d4f12-130">Запуск портала настройки соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="d4f12-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="d4f12-131">Настройка организации здравоохранения для запуска виртуальных посещений с помощью Microsoft Teams начинается с запуска портала конфигурации EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="d4f12-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="d4f12-132">Для тестирования интеграции необходимо настроить одну или несколько организаций.</span><span class="sxs-lookup"><span data-stu-id="d4f12-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="d4f12-133">Настройте тестовый и производственный URL-адрес на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d4f12-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="d4f12-134">Протестировать интеграцию из тестовой среды Сергея перед переходом на производственную среду.</span><span class="sxs-lookup"><span data-stu-id="d4f12-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="d4f12-135">URL-адрес конфигурации соединителя EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d4f12-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="d4f12-136">Администратор Microsoft 365 и клиентский аналитик Из вашей организации должны выполнить действия по настройке и сведениям на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d4f12-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="d4f12-137">Обратитесь к ресурсу технических специалистов, назначенного вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d4f12-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="d4f12-138">Сведения о конфигурации</span><span class="sxs-lookup"><span data-stu-id="d4f12-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="d4f12-139">Это этап должен быть выполнен **администратором Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="d4f12-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="d4f12-140">Администратор Microsoft 365 должен запустить портал конфигурации соединителя и войти с учетными данными Майкрософт, чтобы начать настройку.</span><span class="sxs-lookup"><span data-stu-id="d4f12-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="d4f12-141">Для выполнения этого действия администратор Microsoft 365 должен получить действительный базовый URL-адрес FHIR от вашего специалиста по технической подготовке Реге и имя пользователя клиентского аналитика, который будет утверждать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d4f12-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="d4f12-142">Администратор Microsoft 365 должен запустить страницу конфигурации соединителя и войти с учетными данными Майкрософт, чтобы начать настройку.</span><span class="sxs-lookup"><span data-stu-id="d4f12-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="d4f12-143">Базовый URL-адрес FHIR — это статический адрес, соответствующий конечной точке API FHIR сервера.</span><span class="sxs-lookup"><span data-stu-id="d4f12-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="d4f12-144">Пример `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="d4f12-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="d4f12-145">Имя оголившего конфигурации — это имя клиентского аналитика Висячего, который будет отвечать за утверждения конфигурации на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="d4f12-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="d4f12-146">Клиентский аналитик Висяка — это человек в вашей организации, который имеет доступ для регистрации к Этим данным.</span><span class="sxs-lookup"><span data-stu-id="d4f12-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![Имя утверждения конфигурации выбирается из списка в соединитеке EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="d4f12-148">Утверждение или просмотр конфигурации</span><span class="sxs-lookup"><span data-stu-id="d4f12-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="d4f12-149">Клиентский аналитик вашей организации, добавленный в качестве утверждения, должен использовать тот же URL-адрес соединитора EHR, что и при предыдущем шаге, для входа с учетными данными Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f12-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="d4f12-150">После успешной проверки проверяемого попросят войти в организацию с учетными данными "Сергей".</span><span class="sxs-lookup"><span data-stu-id="d4f12-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="d4f12-151">Администратор Microsoft 365 и клиентский аналитик в вашей организации Может быть один и тот же человек.</span><span class="sxs-lookup"><span data-stu-id="d4f12-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="d4f12-152">В этом случае добавьте свое имя пользователя в качестве утвержденного.</span><span class="sxs-lookup"><span data-stu-id="d4f12-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="d4f12-153">Для проверки доступа все равно потребуется войти в Ахет.</span><span class="sxs-lookup"><span data-stu-id="d4f12-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="d4f12-154">Он используется только для проверки базового URL-адреса СЛФ.</span><span class="sxs-lookup"><span data-stu-id="d4f12-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="d4f12-155">Корпорация Майкрософт не будет хранить учетные данные или получать доступ к данным EHR с помощью этого входа.</span><span class="sxs-lookup"><span data-stu-id="d4f12-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Проверьте и утвердить конфигурацию учетных данных.](../../media/approve-view-configuration.png)

<span data-ttu-id="d4f12-157">После успешного войти в Процесс аналитик Клиента Должен **утвердить** конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d4f12-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="d4f12-158">Если конфигурация неправилена, администратор Microsoft 365 сможет изменить исходные конфигурации, повторно вовшись на портал соединители microsoft EHR.</span><span class="sxs-lookup"><span data-stu-id="d4f12-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Подтвердим, что соединитер EHR настроен и может изменить конфигурацию.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="d4f12-160">Просмотр и завершить настройку</span><span class="sxs-lookup"><span data-stu-id="d4f12-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="d4f12-161">Когда сведения о конфигурации будут утверждены администратором Вайла, вам будут представлены записи интеграции для запуска пациентов и поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="d4f12-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="d4f12-162">Эти записи необходимы для завершения настройки виртуального посещения в Будет.</span><span class="sxs-lookup"><span data-stu-id="d4f12-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="d4f12-163">Дополнительные сведения можно найти в Epic-Microsoft по интеграции с телетайлами Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="d4f12-164">Клиентский аналитик Microsoft 365 или Portal может в любое время войти на портал конфигурации, чтобы просмотреть записи интеграции и при необходимости изменить конфигурацию организации.</span><span class="sxs-lookup"><span data-stu-id="d4f12-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Отобразились сведения об интеграции.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="d4f12-166">Процесс утверждения должен завершиться клиентом-аналитиком Висячим клиентом для каждого URL-адреса FHIR, настроенного администратором Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d4f12-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Сведения конфигурации утверждены.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="d4f12-168">Запуск виртуальных посещений Teams</span><span class="sxs-lookup"><span data-stu-id="d4f12-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="d4f12-169">После выполнения действий по подключению eHR и настройке Учетной записи Майкрософт ваша организация готова к видеосегментам в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="d4f12-170">Предварительные условия виртуального посещения</span><span class="sxs-lookup"><span data-stu-id="d4f12-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="d4f12-171">Ваши системы должны соответствовать всем требованиям [к программному обеспечению и браузеру.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="d4f12-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="d4f12-172">Организации здравоохранения должны завершить настройку между организацией "Организация Скайла" и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4f12-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="d4f12-173">Опыт работы с поставщиком</span><span class="sxs-lookup"><span data-stu-id="d4f12-173">Provider experience</span></span>

<span data-ttu-id="d4f12-174">Поставщики здравоохранения из вашей организации также могут присоединяться к виртуальным посещениям Microsoft Teams из приложений поставщика услуг-поставщиков услуг Майкрософт (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="d4f12-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="d4f12-175">Кнопка **"Начать виртуальное** посещение" внедрена в поток поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="d4f12-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="d4f12-176">Основные функции работы поставщика:</span><span class="sxs-lookup"><span data-stu-id="d4f12-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="d4f12-177">Поставщики могут присоединяться к виртуальным посещениям с помощью поддерживаемых браузеров или приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="d4f12-178">Поставщики должны войти в свою учетную запись Microsoft 365 один раз при первом присоединении к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="d4f12-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="d4f12-179">После одно входов поставщик будет сразу перенаправься на виртуальную встречу в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="d4f12-180">(Поставщик должен быть вписан в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="d4f12-181">Поставщик может в режиме реального времени видеть обновления участников, подключаться к назначенной встрече и отключать ее.</span><span class="sxs-lookup"><span data-stu-id="d4f12-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="d4f12-182">Поставщик может видеть, когда пациент подключен к виртуальному визиту.</span><span class="sxs-lookup"><span data-stu-id="d4f12-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Впечатления от виртуального визита с пациентом](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="d4f12-184">Patient experience</span><span class="sxs-lookup"><span data-stu-id="d4f12-184">Patient experience</span></span>

<span data-ttu-id="d4f12-185">Соединитестор поддерживает пациентов, которые присоединяются к виртуальным посещениям через MyChart Web и мобильные устройства.</span><span class="sxs-lookup"><span data-stu-id="d4f12-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="d4f12-186">Во время встречи пациенты могут начать виртуальный визит из myChart с помощью кнопки "Начать **виртуальный визит".**</span><span class="sxs-lookup"><span data-stu-id="d4f12-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="d4f12-187">Основные функции пациентов:</span><span class="sxs-lookup"><span data-stu-id="d4f12-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="d4f12-188">Пациенты могут присоединиться к виртуальным посещениям современных веб-браузеров на компьютере и мобильном устройстве без установки приложения.</span><span class="sxs-lookup"><span data-stu-id="d4f12-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="d4f12-189">Пациенты могут присоединиться к виртуальным посещениям одним щелчком мыши, для этого не требуется другая учетная запись или вход в учетную запись.</span><span class="sxs-lookup"><span data-stu-id="d4f12-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="d4f12-190">Для запуска виртуального посещения пациенту не требуется создавать учетную запись Майкрософт или войди в нее.</span><span class="sxs-lookup"><span data-stu-id="d4f12-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="d4f12-191">Пациенты будут помещаются в "вестибюль", пока поставщик услуг здравоохранения не присоединится к встрече и не допустит их в виртуальный визит.</span><span class="sxs-lookup"><span data-stu-id="d4f12-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="d4f12-192">Тестирование видео и микрофона доступно в "вестибюле" перед присоединением к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="d4f12-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Patient experience of the virtual visit](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="d4f12-194">Также, MyChart, Haiku и Canto являются товарными знаками корпорации Systems.</span><span class="sxs-lookup"><span data-stu-id="d4f12-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="d4f12-195">Конфиденциальность и расположение данных</span><span class="sxs-lookup"><span data-stu-id="d4f12-195">Privacy and location of data</span></span>

<span data-ttu-id="d4f12-196">Интеграция Teams с системами EHR оптимизирует объем данных, которые используются и хранятся во время интеграции и потоков виртуального посещения.</span><span class="sxs-lookup"><span data-stu-id="d4f12-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="d4f12-197">Решение должно следовать общим принципам конфиденциальности и управления данными Teams, а также правилам, описанным в этой области.</span><span class="sxs-lookup"><span data-stu-id="d4f12-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="d4f12-198">Соединиттель EHR для Microsoft Teams не хранит и не передает из системы EHR личные данные и медицинские записи пациентов и медицинских учреждений.</span><span class="sxs-lookup"><span data-stu-id="d4f12-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="d4f12-199">Единственными данными, которые хранятся соединитетелем EHR, является уникальный ИД пользователя EHR, который используется при настройке собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="d4f12-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="d4f12-200">Уникальный ИД пользователя EHR хранится в одном из трех географических регионов, описанных в месте хранения данных клиента [Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)</span><span class="sxs-lookup"><span data-stu-id="d4f12-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="d4f12-201">Все данные чата, записи и другие данные, вносяые участниками собрания в Teams, хранятся в соответствии с существующими политиками хранения.</span><span class="sxs-lookup"><span data-stu-id="d4f12-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="d4f12-202">Если вы хотите узнать больше о расположении данных в Microsoft Teams, посетите [веб-сайт с расположениями данных в Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)</span><span class="sxs-lookup"><span data-stu-id="d4f12-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
