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
ms.reviewer: ansantam
description: Настройка системы виртуальных посещений с помощью Microsoft Teams
ms.openlocfilehash: 9c002a90cd91014ca4887386ca5834a4b5b41266
ms.sourcegitcommit: d73dc8505a5cc5af29635a50cbbf0f25bbb17eac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705253"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="7fd41-103">Виртуальные посещения с помощью Teams — интеграция с электронными медицинскими картами</span><span class="sxs-lookup"><span data-stu-id="7fd41-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="7fd41-104">Microsoft Teams Соединителей электронной записи здоровья (EHR) можно легко запустить виртуальный визит пациентов или консультацию к другому поставщику в Teams непосредственно из системы EHR.</span><span class="sxs-lookup"><span data-stu-id="7fd41-104">Microsoft Teams Electronic Health Record (EHR) connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="7fd41-105">Microsoft Teams, созданная на базе облака Microsoft 365, обеспечивает простую и безопасную совместную работу и общение с помощью инструментов чата, видео, голоса и здравоохранения в едином центре, который поддерживает соответствие требованиям сертификации акта HIPAA, HITECH и других.</span><span class="sxs-lookup"><span data-stu-id="7fd41-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="7fd41-106">Платформа для общения и совместной работы Teams позволяет врачам легко преодолевать беспорядок несрочных фрагментированных систем, чтобы они могли уделять время оказанию наилучшего медицинского обслуживания.</span><span class="sxs-lookup"><span data-stu-id="7fd41-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="7fd41-107">Microsoft Teams Соединитектор электронной записи здоровья (EHR) может:</span><span class="sxs-lookup"><span data-stu-id="7fd41-107">Microsoft Teams Electronic Health Record (EHR) connector can:</span></span>

- <span data-ttu-id="7fd41-108">Запускать Teams виртуальных посещений из системы EHR поставщиков с интегрированным медицинским процессом.</span><span class="sxs-lookup"><span data-stu-id="7fd41-108">Launch Teams virtual visits from the provider EHR system with an integrated clinical workflow.</span></span>
- <span data-ttu-id="7fd41-109">Позволяет пользователям присоединяться к виртуальным Teams на портале пациентов.</span><span class="sxs-lookup"><span data-stu-id="7fd41-109">Enable patients to join Teams virtual visits from within the patient portal.</span></span>
- <span data-ttu-id="7fd41-110">Пишите метаданные в систему EHR о виртуальных посещениях Teams при подключении, отключении и включении автоматического аудита и сохраняемой записи.</span><span class="sxs-lookup"><span data-stu-id="7fd41-110">Write metadata back to the EHR system regarding Teams virtual visits to record when attendees connect and disconnect and enable automatic auditing and record keeping.</span></span>

  <span data-ttu-id="7fd41-111">Посмотрите видео о том, как управлять виртуальными посещениями с портала электронной медицинской карты.</span><span class="sxs-lookup"><span data-stu-id="7fd41-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="7fd41-112">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="7fd41-112">Before you begin</span></span>

<span data-ttu-id="7fd41-113">Перед интеграцией соединителя электронной медицинской карты необходимо убедиться в том, что вами были соблюдены следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="7fd41-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="7fd41-114">Доступ к приложению Microsoft Teams в [магазине Epic — App Orchard](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="7fd41-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="7fd41-115">Активная подписка на Microsoft Cloud для здравоохранения или подписка на Microsoft Teams EHR Connector (только при тестировании в производственной системе).</span><span class="sxs-lookup"><span data-stu-id="7fd41-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="7fd41-116">Пользователи должны иметь соответствующую лицензию на Microsoft 365 или Office 365, которая включает собрания Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7fd41-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="7fd41-117">Microsoft Teams следует внедрять и использовать внутри организации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="7fd41-118">Организации должны иметь версию Epic с ноября 2018 г. или более позднюю.</span><span class="sxs-lookup"><span data-stu-id="7fd41-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="7fd41-119">Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="7fd41-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="7fd41-120">Вам также потребуются сведения от следующих пользователей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="7fd41-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="7fd41-121">Администратор Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7fd41-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="7fd41-122">Аналитик клиентов Epic</span><span class="sxs-lookup"><span data-stu-id="7fd41-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="7fd41-123">Просмотрите [руководство по интеграции телемедицины Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) со своим техническим специалистом Epic.</span><span class="sxs-lookup"><span data-stu-id="7fd41-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="7fd41-124">Выполните все необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="7fd41-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="7fd41-125">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="7fd41-125">Connector setup</span></span>

<span data-ttu-id="7fd41-126">Для настройки соединители необходимо:</span><span class="sxs-lookup"><span data-stu-id="7fd41-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="7fd41-127">Запуск портала настройки соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="7fd41-127">Launch the EHR connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="7fd41-128">Сведения о конфигурации</span><span class="sxs-lookup"><span data-stu-id="7fd41-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="7fd41-129">Утвердить или просмотреть конфигурацию</span><span class="sxs-lookup"><span data-stu-id="7fd41-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="7fd41-130">Просмотреть и завершить конфигурацию</span><span class="sxs-lookup"><span data-stu-id="7fd41-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="7fd41-131">Запуск портала настройки соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="7fd41-131">Launch the EHR connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="7fd41-132">Настройка организации здравоохранения для запуска виртуальных посещений с Microsoft Teams начинается с запуска портала конфигурации соединителя EHR.</span><span class="sxs-lookup"><span data-stu-id="7fd41-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR connector configuration portal.</span></span> <span data-ttu-id="7fd41-133">Для тестирования интеграции настраивается одна или несколько организаций.</span><span class="sxs-lookup"><span data-stu-id="7fd41-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="7fd41-134">Настройте тестовый и рабочий URL-адреса на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="7fd41-135">Прежде чем переходить к производственной среде, протестируйте интеграцию из тестовой среды Epic.</span><span class="sxs-lookup"><span data-stu-id="7fd41-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="7fd41-136">URL-адрес конфигурация соединителя электронной медицинской карты: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="7fd41-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="7fd41-137">Администратор Microsoft 365 и аналитик клиентов Epic из вашей организации должны выполнить действия по интеграции и информации на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="7fd41-138">Для настройки Epic обратитесь к ресурсам технического специалиста Epic, назначенного вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="7fd41-139">Сведения о конфигурации</span><span class="sxs-lookup"><span data-stu-id="7fd41-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="7fd41-140">Этот шаг должен быть выполнен **администратором Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="7fd41-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="7fd41-141">Администратор Microsoft 365 должен запустить портал конфигурации соединителя и войти с помощью учетных данных Майкрософт, чтобы начать процесс конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="7fd41-142">Для выполнения этого шага администратор Microsoft 365 должен получить действительный базовый URL-адрес ресурсов быстрого взаимодействия в сфере здравоохранения (FHIR) от вашего технического специалиста Epic и имя пользователя аналитика клиентов Epic, который будет утверждать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7fd41-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="7fd41-143">Администратор Microsoft 365 должен запустить страницу конфигурации соединителя и войти с помощью учетных данных Майкрософт, чтобы начать процесс конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="7fd41-144">Базовый URL-адрес FHIR — это статический адрес, соответствующий конечной точке API FHIR сервера.</span><span class="sxs-lookup"><span data-stu-id="7fd41-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="7fd41-145">Пример URL-адреса — `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span><span class="sxs-lookup"><span data-stu-id="7fd41-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="7fd41-146">Имя утверждающего конфигурации — это имя аналитика клиентов Epic, который будет отвечать за утверждение конфигурации на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="7fd41-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="7fd41-147">Аналитик клиентов Epic — это сотрудник вашей организации, который имеет доступ для входа в Epic.</span><span class="sxs-lookup"><span data-stu-id="7fd41-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![Имя утверждающего конфигурацию выбирается из списка в соединителе EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="7fd41-149">Утверждение или просмотр конфигурации</span><span class="sxs-lookup"><span data-stu-id="7fd41-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="7fd41-150">Клиентский аналитик вашей медицинской организации, добавленный в качестве утвержденного, теперь должен использовать тот же URL-адрес соединителя EHR, что и на предыдущем шаге, для входа с Microsoft 365 учетными данными.</span><span class="sxs-lookup"><span data-stu-id="7fd41-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="7fd41-151">После успешной проверки утверждающему будет предложено войти в систему, используя учетные данные Epic, для проверки организации Epic.</span><span class="sxs-lookup"><span data-stu-id="7fd41-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="7fd41-152">Администратор Microsoft 365 и аналитик клиентов Epic в вашей организации могут быть одним и тем же лицом.</span><span class="sxs-lookup"><span data-stu-id="7fd41-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="7fd41-153">В этом случае добавьте собственное имя пользователя в качестве утверждающего.</span><span class="sxs-lookup"><span data-stu-id="7fd41-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="7fd41-154">Вам все равно потребуется войти в Epic, чтобы подтвердить свой доступ.</span><span class="sxs-lookup"><span data-stu-id="7fd41-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="7fd41-155">Вход Epic используется только для проверки базового URL-адреса FHIR.</span><span class="sxs-lookup"><span data-stu-id="7fd41-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="7fd41-156">Корпорация Майкрософт не будет хранить учетные данные или получать доступ к данным EHR с помощью этого входа.</span><span class="sxs-lookup"><span data-stu-id="7fd41-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Проверка и утверждение конфигурации учетных данных.](../../media/approve-view-configuration.png)

<span data-ttu-id="7fd41-158">После успешного входа в Epic аналитику клиента Epic **необходимо** утвердить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7fd41-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="7fd41-159">Если конфигурация неверна, администратор Microsoft 365 сможет изменить исходную конфигурацию, снова войдя на портал соединителя электронной медицинской карты Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7fd41-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Подтвердите, что соединитель электронной медицинской карты настроен и возможность изменения конфигурации.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="7fd41-161">Просмотр и завершение конфигурации</span><span class="sxs-lookup"><span data-stu-id="7fd41-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="7fd41-162">После утверждения сведений о конфигурации администратором Epic вам будут представлены записи интеграции для запуска пациентов и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="7fd41-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="7fd41-163">Эти записи необходимы для завершения настройки виртуального посещения в Epic.</span><span class="sxs-lookup"><span data-stu-id="7fd41-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="7fd41-164">Дополнительные сведения можно найти в руководстве по интеграции Epic-Microsoft Teams Telehealth.</span><span class="sxs-lookup"><span data-stu-id="7fd41-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="7fd41-165">В любое время аналитик клиентов Microsoft 365 или Epic может войти на портал конфигурации, чтобы просмотреть записи интеграции и при необходимости изменить конфигурацию организации.</span><span class="sxs-lookup"><span data-stu-id="7fd41-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Отображаются сведения об интеграции.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="7fd41-167">Процесс утверждения должен быть завершен аналитиком клиентов Epic для каждого URL-адреса FHIR, настроенного администратором Майкрософт ранее.</span><span class="sxs-lookup"><span data-stu-id="7fd41-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![Сведения о конфигурации утверждены.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="7fd41-169">Запуск виртуальных посещений Teams</span><span class="sxs-lookup"><span data-stu-id="7fd41-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="7fd41-170">После выполнения действий по подключению eHR и настройки Службы EHR ваша организация готова поддерживать видео посещения с помощью Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7fd41-170">After completing the EHR connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="7fd41-171">Предварительные условия для виртуального посещения</span><span class="sxs-lookup"><span data-stu-id="7fd41-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="7fd41-172">Ваши системы должны соответствовать всем [требованиям к программному обеспечению и браузеру](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="7fd41-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="7fd41-173">Медицинская организация должна выполнить настройку между организацией Epic и организацией Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fd41-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="7fd41-174">Взаимодействие с поставщиком</span><span class="sxs-lookup"><span data-stu-id="7fd41-174">Provider experience</span></span>

<span data-ttu-id="7fd41-175">Поставщики медицинских услуг из вашей организации также могут присоединяться к виртуальным посещениям Microsoft Teams из своих приложений поставщика Epic (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="7fd41-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="7fd41-176">Кнопка **Начать виртуальное посещение** внедрена в поток поставщика.</span><span class="sxs-lookup"><span data-stu-id="7fd41-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="7fd41-177">Основные функции взаимодействия с поставщиком:</span><span class="sxs-lookup"><span data-stu-id="7fd41-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="7fd41-178">Поставщики могут присоединяться к виртуальным посещениям с помощью поддерживаемых браузеров или приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7fd41-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="7fd41-179">Поставщики должны один раз войти в свою учетную запись Microsoft 365 при первом виртуальном посещении.</span><span class="sxs-lookup"><span data-stu-id="7fd41-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="7fd41-p114">После однократного входа поставщик будет перенаправлен сразу на виртуальную встречу в Microsoft Teams. (Поставщик должен быть авторизован в Microsoft Teams.)</span><span class="sxs-lookup"><span data-stu-id="7fd41-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="7fd41-182">Провайдер может видеть в режиме реального времени обновления участников, подключающихся и отключающихся от встречи.</span><span class="sxs-lookup"><span data-stu-id="7fd41-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="7fd41-183">Поставщик может видеть, когда пациент подключен к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="7fd41-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Взаимодействие с поставщиком во время виртуального посещения с пациентом](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="7fd41-185">Взаимодействие с пациентом</span><span class="sxs-lookup"><span data-stu-id="7fd41-185">Patient experience</span></span>

<span data-ttu-id="7fd41-186">Соединитель позволяет пациентам присоединяться к виртуальным посещениям через MyChart в Интернете и на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="7fd41-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="7fd41-187">Во время приема пациенты могут начать виртуальное посещение из MyChart с помощью кнопки **Начать виртуальное посещение**.</span><span class="sxs-lookup"><span data-stu-id="7fd41-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="7fd41-188">Основные функции взаимодействия с пациентом:</span><span class="sxs-lookup"><span data-stu-id="7fd41-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="7fd41-189">Пациенты могут присоединяться к виртуальным посещениям из современных веб-браузеров на настольных компьютерах и мобильных устройствах без установки приложения.</span><span class="sxs-lookup"><span data-stu-id="7fd41-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="7fd41-190">Пациенты могут присоединиться к виртуальным посещениям одним щелчком мыши. Другие учетные записи или выполнение входа не требуются.</span><span class="sxs-lookup"><span data-stu-id="7fd41-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="7fd41-191">Для запуска виртуального посещения пациентам не требуется создавать учетную запись Майкрософт или выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="7fd41-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="7fd41-192">Пациенты будут помещены в "зал ожидания" до тех пор, пока поставщик медицинских услуг не присоединится к встрече и не допустит их к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="7fd41-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="7fd41-193">Перед присоединением к виртуальному посещению в "зале ожидания" доступно тестирование видео и микрофона.</span><span class="sxs-lookup"><span data-stu-id="7fd41-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Взаимодействие с пациентом во время виртуального посещения](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="7fd41-195">Epic, MyChart, Haiku и Canto являются товарными знаками корпорации Epic Systems.</span><span class="sxs-lookup"><span data-stu-id="7fd41-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="7fd41-196">Конфиденциальность и расположение данных</span><span class="sxs-lookup"><span data-stu-id="7fd41-196">Privacy and location of data</span></span>

<span data-ttu-id="7fd41-197">Интеграция Teams в системы электронной медицинской карты оптимизирует объем данных, используемых и хранимых во время интеграции и потоков виртуальных посещений.</span><span class="sxs-lookup"><span data-stu-id="7fd41-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="7fd41-198">Решение соответствует общим принципам и рекомендациям по обеспечению конфиденциальности и управлению данными Teams, изложенным в разделе "Конфиденциальность Teams".</span><span class="sxs-lookup"><span data-stu-id="7fd41-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="7fd41-199">Соединитель электронной медицинской карты Microsoft Teams не хранит и не передает какие-либо идентифицирующие личные сведения или медицинские записи пациентов или поставщиков медицинских услуг из системы электронной медицинской карты.</span><span class="sxs-lookup"><span data-stu-id="7fd41-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="7fd41-200">Единственные данные, которые хранятся в соединителе электронной медицинской карты, — это уникальный идентификатор пользователя электронной медицинской карты, который используется во время настройки собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="7fd41-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="7fd41-201">Уникальный идентификатор пользователя электронной медицинской карты хранится в одном из трех географических регионов, описанных в статье [Где хранятся данные клиентов Microsoft 365](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="7fd41-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="7fd41-202">Все беседы, записи и другие данные, которые участники собрания ввели в Teams, хранятся в соответствии с существующими политиками хранения.</span><span class="sxs-lookup"><span data-stu-id="7fd41-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="7fd41-203">Дополнительные сведения о расположении данных в Microsoft Teams см. в статье [Расположения данных в Teams](../../location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7fd41-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7fd41-204">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7fd41-204">Related topics</span></span>

[<span data-ttu-id="7fd41-205">Teams виртуальных посещений</span><span class="sxs-lookup"><span data-stu-id="7fd41-205">Teams virtual visits</span></span>](ehr-admin-reports.md)