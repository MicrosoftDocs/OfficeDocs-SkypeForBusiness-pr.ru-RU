---
title: Команды для виртуальных посетителей
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Настройка системы виртуальных посещений с помощью Microsoft Teams
ms.openlocfilehash: dcf852486d6a7fbace23bea5fb8610c62bdc7e4f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766722"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="a3c93-103">Виртуальные посещения с помощью Teams – интеграция с EHR</span><span class="sxs-lookup"><span data-stu-id="a3c93-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="a3c93-104">Соединительная запись о работоспособности Microsoft Teams (EHR) позволяет clinicians запускать виртуальные пациента и консультации с другими поставщиками в Teams прямо из системы EHR.</span><span class="sxs-lookup"><span data-stu-id="a3c93-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="a3c93-105">Приложение Microsoft Teams, разработанное в облаке Microsoft 365, обеспечивает простую и безопасную совместную работу с помощью чатов, видео, голоса и средств для сферы здравоохранения на одном концентраторе, который поддерживает соответствие требованиям закона HIPAA, HITECH Certification и т. д.</span><span class="sxs-lookup"><span data-stu-id="a3c93-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="a3c93-106">Платформа для взаимодействия и совместной работы в Teams позволяет clinicians сократить количество фрагментированных систем, чтобы они могли тратить время на предоставление лучшей важности.</span><span class="sxs-lookup"><span data-stu-id="a3c93-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="a3c93-107">Соединитель электронной записи о работоспособности Microsoft Teams (EHR) может:</span><span class="sxs-lookup"><span data-stu-id="a3c93-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="a3c93-108">Запускайте виртуальные визиты Teams из поставщиков и порталов пациента.</span><span class="sxs-lookup"><span data-stu-id="a3c93-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="a3c93-109">Чтобы включить автоматическую аудит и сохранение записи, снова напишите метаданные EHR в событиях Connect и Disconnect.</span><span class="sxs-lookup"><span data-stu-id="a3c93-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="a3c93-110">Интегрируйтесь с существующими рабочими процессами Clinician и пациента, разрешая им использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a3c93-111">До начала работы</span><span class="sxs-lookup"><span data-stu-id="a3c93-111">Before you begin</span></span>

<span data-ttu-id="a3c93-112">Прежде чем приступить к интеграции соединителя EHR, необходимо убедиться, что у вас есть следующие предварительные требования:</span><span class="sxs-lookup"><span data-stu-id="a3c93-112">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="a3c93-113">Подписка на подписку Microsoft Cloud на здравоохранение или подписку на Microsoft Teams EHR Connector для автономного предложения.</span><span class="sxs-lookup"><span data-stu-id="a3c93-113">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="a3c93-114">У пользователей должна быть соответствующая лицензия Microsoft 365 или Office 365, включающая собрания Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-114">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="a3c93-115">Корпорация Microsoft Teams должна быть принята и использоваться в рамках Организации.</span><span class="sxs-lookup"><span data-stu-id="a3c93-115">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="a3c93-116">Организации должны иметь версию "История" 2018 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="a3c93-116">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="a3c93-117">Ваши системы должны соответствовать всем требованиям к [программному обеспечению и браузеру](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="a3c93-117">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="a3c93-118">Вам также понадобятся сведения о следующих сотрудниках вашей организации:</span><span class="sxs-lookup"><span data-stu-id="a3c93-118">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="a3c93-119">Администратор Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3c93-119">Microsoft 365 administrator</span></span>

- <span data-ttu-id="a3c93-120">Администратор "История"</span><span class="sxs-lookup"><span data-stu-id="a3c93-120">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="a3c93-121">Попросите администратора вашей ситуации предоставить вам руководство по интеграции Epic-Microsoft Teaming для группы, доступное на рынке.</span><span class="sxs-lookup"><span data-stu-id="a3c93-121">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="a3c93-122">Настройка соединителя</span><span class="sxs-lookup"><span data-stu-id="a3c93-122">Connector setup</span></span>

<span data-ttu-id="a3c93-123">Для установки соединителя необходимо:</span><span class="sxs-lookup"><span data-stu-id="a3c93-123">The connector setup requires that you:</span></span>

- [<span data-ttu-id="a3c93-124">Запуск портала конфигурации соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="a3c93-124">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="a3c93-125">Настройка сведений об организации поставщика</span><span class="sxs-lookup"><span data-stu-id="a3c93-125">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="a3c93-126">Проверка и утверждение конфигурации</span><span class="sxs-lookup"><span data-stu-id="a3c93-126">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="a3c93-127">Проверка и завершение настройки</span><span class="sxs-lookup"><span data-stu-id="a3c93-127">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="a3c93-128">Запуск портала конфигурации соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="a3c93-128">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="a3c93-129">Настройка организации здравоохранения для запуска виртуальных визитов в Microsoft Teams начинается с запуска портала конфигурации соединителя EHR.</span><span class="sxs-lookup"><span data-stu-id="a3c93-129">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="a3c93-130">С помощью тестового URL-адреса Настройте соединительную линию для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="a3c93-130">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="a3c93-131">Используйте URL-адрес производства, когда вы будете готовы включить производственную среду для создания истории.</span><span class="sxs-lookup"><span data-stu-id="a3c93-131">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="a3c93-132">Тестовая среда [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a3c93-132">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="a3c93-133">Производственную среду [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a3c93-133">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="a3c93-134">Администратор администраторов Microsoft 365 и история ее организации должны заполнить данные и этапы интеграции на портале настройки.</span><span class="sxs-lookup"><span data-stu-id="a3c93-134">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="a3c93-135">Для этапов настройки обобщения свяжитесь с ресурсом, назначенным вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a3c93-135">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="a3c93-136">Настройка сведений об организации поставщика</span><span class="sxs-lookup"><span data-stu-id="a3c93-136">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="a3c93-137">Это действие завершается администратором Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3c93-137">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="a3c93-138">Чтобы начать процесс настройки, администратор Microsoft 365 должен запустить портал конфигурации соединителя и войти с помощью учетных данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3c93-138">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="a3c93-139">Чтобы выполнить это действие, администратор Microsoft 365 должен получить действительный базовый URL-адрес для ресурсов с быстрой совместимостью (FHIR) от администратора Microsoft 365 и имя пользователя администратора, который будет утверждать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a3c93-139">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="a3c93-140">Чтобы начать процесс настройки, администратор Microsoft 365 должен запустить страницу конфигурации соединителя и войти с помощью учетных данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3c93-140">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="a3c93-141">Базовый URL-адрес FHIR является статическим адресом, соответствующим конечной точке сервера FHIR API.</span><span class="sxs-lookup"><span data-stu-id="a3c93-141">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="a3c93-142">Пример URL-адреса [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) .</span><span class="sxs-lookup"><span data-stu-id="a3c93-142">An example URL is [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST).</span></span>

- <span data-ttu-id="a3c93-143">Имя утверждающего конфигурации — это имя системного администратора, который будет ответственен за утверждение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a3c93-143">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![Имя утверждающего конфигурации выделено из списка в соединителе EHR.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="a3c93-145">Проверка и утверждение конфигурации</span><span class="sxs-lookup"><span data-stu-id="a3c93-145">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="a3c93-146">Для входа в систему с помощью учетных данных Microsoft 365 администратором вашей организации здравоохранения, который добавился в качестве утверждающего, необходимо использовать тот же URL-адрес соединителя EHR, что и на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="a3c93-146">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="a3c93-147">После успешной проверки утверждающему лицу будет предложено выполнить вход, используя свои учетные данные для проверки Организации, в которой выполняется история.</span><span class="sxs-lookup"><span data-stu-id="a3c93-147">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="a3c93-148">Администраторы Microsoft 365 и пользователи с обделами в вашей организации могут быть одного и того же человека.</span><span class="sxs-lookup"><span data-stu-id="a3c93-148">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="a3c93-149">В этом случае добавьте свое имя пользователя в качестве утверждающего на первом этапе.</span><span class="sxs-lookup"><span data-stu-id="a3c93-149">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="a3c93-150">Для проверки прав доступа вам по-прежнему понадобится войти в службу "История".</span><span class="sxs-lookup"><span data-stu-id="a3c93-150">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="a3c93-151">Вход в эту учетную запись используется только для проверки базового URL-адреса FHIR.</span><span class="sxs-lookup"><span data-stu-id="a3c93-151">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="a3c93-152">Корпорация Майкрософт не сохраняет учетные данные и не получает доступ к данным EHR с помощью этого входа.</span><span class="sxs-lookup"><span data-stu-id="a3c93-152">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![Проверьте и утвердите конфигурацию учетных данных.](../../media/ehc-provider-2.png)

<span data-ttu-id="a3c93-154">После успешного входа в свою учетную запись Администратор **может** утвердить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="a3c93-154">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="a3c93-155">Если конфигурация не верна, администратор Microsoft 365 может изменить исходные настройки, войдя на портал Microsoft EHR Connector еще раз.</span><span class="sxs-lookup"><span data-stu-id="a3c93-155">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![Убедитесь в том, что соединитель EHR настроен, и измените параметры.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="a3c93-157">Проверка и завершение настройки</span><span class="sxs-lookup"><span data-stu-id="a3c93-157">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="a3c93-158">Если сведения о конфигурации утверждены администратором, вы будете получать записи интеграции для пациента и поставщиков.</span><span class="sxs-lookup"><span data-stu-id="a3c93-158">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="a3c93-159">Эти записи необходимы для завершения конфигурации виртуального посещения в ситуации.</span><span class="sxs-lookup"><span data-stu-id="a3c93-159">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="a3c93-160">Дополнительные сведения можно найти в руководстве по интеграции Epic-Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-160">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="a3c93-161">В любое время Администратор Microsoft 365 или история может войти на портал конфигурации, чтобы просмотреть записи интеграции и при необходимости изменить конфигурацию Организации.</span><span class="sxs-lookup"><span data-stu-id="a3c93-161">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Откроется информация о интеграции.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="a3c93-163">Запуск виртуальных визитных групп</span><span class="sxs-lookup"><span data-stu-id="a3c93-163">Launch Teams virtual visits</span></span>

<span data-ttu-id="a3c93-164">После завершения действий соединителя EHR и настройки ситуации ваша организация готова поддерживать посещения видео в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-164">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="a3c93-165">Виртуальные посещения, необходимые для виртуальных посетителей</span><span class="sxs-lookup"><span data-stu-id="a3c93-165">Virtual visit prerequisites</span></span>

- <span data-ttu-id="a3c93-166">Ваши системы должны соответствовать всем требованиям к [программному обеспечению и браузеру](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="a3c93-166">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="a3c93-167">Организация здравоохранения должна завершить настройку между Организацией "История" и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a3c93-167">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="a3c93-168">Взаимодействие с поставщиком</span><span class="sxs-lookup"><span data-stu-id="a3c93-168">Provider experience</span></span>

<span data-ttu-id="a3c93-169">Поставщики для здравоохранения из вашей организации также могут присоединиться к виртуальным посещениям Microsoft Teams из своих приложений провайдера (гиперпространства, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="a3c93-169">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="a3c93-170">Кнопка " **начать виртуальный визит** " внедрена в поток управления поставщиками.</span><span class="sxs-lookup"><span data-stu-id="a3c93-170">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="a3c93-171">Основные возможности поставщика:</span><span class="sxs-lookup"><span data-stu-id="a3c93-171">Key features of the provider experience:</span></span>

- <span data-ttu-id="a3c93-172">Поставщики могут присоединяться к виртуальным посещениям с помощью поддерживаемых браузеров или приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-172">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="a3c93-173">Поставщики должны выполнить вход с помощью учетной записи Microsoft 365 в первый раз, когда вы присоединитесь к виртуальному посещаете.</span><span class="sxs-lookup"><span data-stu-id="a3c93-173">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="a3c93-174">После того как один раз войти в Skype, поставщик будет передаваться непосредственно в виртуальную встречу в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-174">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="a3c93-175">(Поставщик должен войти в Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="a3c93-175">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="a3c93-176">Поставщик может видеть обновления участников, которые подключаются и отключаются в реальном времени для указанной встречи.</span><span class="sxs-lookup"><span data-stu-id="a3c93-176">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="a3c93-177">Поставщик может видеть, когда пациент подключается к виртуальному визиту.</span><span class="sxs-lookup"><span data-stu-id="a3c93-177">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Работа провайдера виртуального посещения с пациентом](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="a3c93-179">Качество пациента</span><span class="sxs-lookup"><span data-stu-id="a3c93-179">Patient experience</span></span>

<span data-ttu-id="a3c93-180">Соединительная линия поддерживает пациентов присоединения виртуальных посетителей через MyChart веб-и мобильные телефоны.</span><span class="sxs-lookup"><span data-stu-id="a3c93-180">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="a3c93-181">Во время встречи пациентов может начать виртуальный визит из MyChart с помощью кнопки " **начать виртуальный центр посещения** ".</span><span class="sxs-lookup"><span data-stu-id="a3c93-181">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="a3c93-182">Основные характеристики качества пациента:</span><span class="sxs-lookup"><span data-stu-id="a3c93-182">Key features of the patient experience:</span></span>

- <span data-ttu-id="a3c93-183">Пациентов может присоединиться к виртуальным посещениям современных браузеров на настольном компьютере и мобильном устройстве без установки приложений.</span><span class="sxs-lookup"><span data-stu-id="a3c93-183">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="a3c93-184">Пациентов может присоединиться к виртуальным посещениям одним щелчком, а дополнительные учетные записи или выполнить вход не требуется.</span><span class="sxs-lookup"><span data-stu-id="a3c93-184">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="a3c93-185">Пациентов не обязаны создавать учетную запись Майкрософт или входить в службу для запуска виртуального посещения.</span><span class="sxs-lookup"><span data-stu-id="a3c93-185">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="a3c93-186">Пациентов будет помещен в зал до тех пор, пока поставщик здравоохранения не присоединится к встрече и не отправит ее виртуальному визиту.</span><span class="sxs-lookup"><span data-stu-id="a3c93-186">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="a3c93-187">Тестирование видео и микрофона доступно в зале ожидания, прежде чем присоединиться к виртуальному веб –.</span><span class="sxs-lookup"><span data-stu-id="a3c93-187">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Качество обслуживания виртуального визита в пациентах](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="a3c93-189">История, MyChart, Haiku и Canto являются товарными знаками корпорации Systems.</span><span class="sxs-lookup"><span data-stu-id="a3c93-189">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="a3c93-190">Конфиденциальность и местонахождение данных</span><span class="sxs-lookup"><span data-stu-id="a3c93-190">Privacy and location of data</span></span>

<span data-ttu-id="a3c93-191">Интеграция Teams в EHR Systems оптимизирует объем используемых данных и их хранение во время интеграции и виртуальных потоков посещения.</span><span class="sxs-lookup"><span data-stu-id="a3c93-191">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="a3c93-192">Решение соответствует общим принципам конфиденциальности и управления данными, а также рекомендациям, изложенным в разделе Конфиденциальность в Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-192">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="a3c93-193">Соединитель Microsoft Teams EHR не хранит и не переносит какие бы то ни вы личные данные или какие – либо записи о работоспособности пациентов или сотрудников здравоохранения из системы EHR.</span><span class="sxs-lookup"><span data-stu-id="a3c93-193">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="a3c93-194">Только те данные, которые хранятся в соединителе EHR, — это уникальный идентификатор пользователя EHR, который используется во время настройки собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="a3c93-194">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="a3c93-195">Уникальный идентификатор пользователя EHR хранится в одном из трех географических регионов, описанных в том [месте, где хранятся данные о клиентах Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) .</span><span class="sxs-lookup"><span data-stu-id="a3c93-195">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="a3c93-196">Все чат, записи и другие данные, вводимые участниками собрания в Teams, хранятся в соответствии с существующими политиками хранения.</span><span class="sxs-lookup"><span data-stu-id="a3c93-196">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="a3c93-197">Если вы хотите получить дополнительные сведения о расположении данных в Microsoft Teams, перейдите [в раздел Расположение данных в Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a3c93-197">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
