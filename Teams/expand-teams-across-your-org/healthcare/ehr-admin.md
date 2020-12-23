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
ms.openlocfilehash: 808d957cd86273852e7c2c98ec223b1988e5bd0d
ms.sourcegitcommit: cbf87fc914a19088af8ec08fb0976db9f838a45d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "49355969"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="fa70f-103">Виртуальные посещения с помощью Teams — интеграция с EHR</span><span class="sxs-lookup"><span data-stu-id="fa70f-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="fa70f-104">Соединителей электронной медицинских записей Microsoft Teams (EHR) можно легко запустить виртуальное посещение пациентов или обратиться к другому поставщику в Teams непосредственно из системы EHR.</span><span class="sxs-lookup"><span data-stu-id="fa70f-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="fa70f-105">Microsoft Teams, встроенный в облако Microsoft 365, обеспечивает простую и безопасную совместную работу и общение с чатом, видеосвязь, голосовой связью и медицинскими инструментами в едином центре, который поддерживает соответствие с сертификацией HIPAA, HITECH и другими программами.</span><span class="sxs-lookup"><span data-stu-id="fa70f-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="fa70f-106">Платформа для коммуникаций и совместной работы Teams позволяет клиникам легко перегромождать негроможденные системы и тратить время на предоставление наилучшей помощи.</span><span class="sxs-lookup"><span data-stu-id="fa70f-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="fa70f-107">Соединитер электронной записи здравоохранения Microsoft Teams (EHR) может:</span><span class="sxs-lookup"><span data-stu-id="fa70f-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="fa70f-108">Запускать виртуальные визиты Teams как с порталов поставщика услуг, так и с порталов пациентов.</span><span class="sxs-lookup"><span data-stu-id="fa70f-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="fa70f-109">Записывая запись в метаданные EHR при подключении и отключении событий, чтобы включить автоматическое ведение аудита и сохраняемую запись.</span><span class="sxs-lookup"><span data-stu-id="fa70f-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="fa70f-110">Интегрируются в существующие рабочий процессы клиники и пациентов, позволяя им использовать Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="fa70f-111">Посмотрите видео о том, как управлять виртуальными посещениями с портала EHR.</span><span class="sxs-lookup"><span data-stu-id="fa70f-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="fa70f-112">До начала работы</span><span class="sxs-lookup"><span data-stu-id="fa70f-112">Before you begin</span></span>

<span data-ttu-id="fa70f-113">Перед интеграцией соединитела EHR необходимо убедиться в том, что у вас есть следующие необходимые условия:</span><span class="sxs-lookup"><span data-stu-id="fa70f-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="fa70f-114">Активная подписка на Microsoft Cloud для здравоохранения или подписка на автономный продукт Microsoft Teams EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="fa70f-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="fa70f-115">У пользователей должна быть соответствующая лицензия Microsoft 365 или Office 365, которая включает собрания Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="fa70f-116">Microsoft Teams следует принятия и использования в организации.</span><span class="sxs-lookup"><span data-stu-id="fa70f-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="fa70f-117">У организаций должна быть версия с ноябрь 2018 г. или более поздней.</span><span class="sxs-lookup"><span data-stu-id="fa70f-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="fa70f-118">Ваши системы должны соответствовать всем требованиям [к программному обеспечению и браузеру.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="fa70f-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="fa70f-119">Вам также потребуется информация от следующих людей в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="fa70f-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="fa70f-120">Администратор Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fa70f-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="fa70f-121">Администратор</span><span class="sxs-lookup"><span data-stu-id="fa70f-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="fa70f-122">Запросите у администратора Вашей учетной Epic-Microsoft интеграции с Telehealth Teams, доступное в Marketplace.</span><span class="sxs-lookup"><span data-stu-id="fa70f-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="fa70f-123">Настройка соедините камеры</span><span class="sxs-lookup"><span data-stu-id="fa70f-123">Connector setup</span></span>

<span data-ttu-id="fa70f-124">Для настройки соединители требуется:</span><span class="sxs-lookup"><span data-stu-id="fa70f-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="fa70f-125">Запуск портала настройки соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="fa70f-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="fa70f-126">Настройка сведений о компании-поставщике</span><span class="sxs-lookup"><span data-stu-id="fa70f-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="fa70f-127">Проверка и утверждение конфигурации</span><span class="sxs-lookup"><span data-stu-id="fa70f-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="fa70f-128">Просмотр и завершить настройку</span><span class="sxs-lookup"><span data-stu-id="fa70f-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="fa70f-129">Запуск портала настройки соединителя EHR</span><span class="sxs-lookup"><span data-stu-id="fa70f-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="fa70f-130">Настройка организации здравоохранения для запуска виртуальных посещений с помощью Microsoft Teams начинается с запуска портала конфигурации EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="fa70f-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="fa70f-131">Используйте тестовый URL-адрес для настройки соединителя в тестовой среде Test Environment.</span><span class="sxs-lookup"><span data-stu-id="fa70f-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="fa70f-132">Используйте производственный URL-адрес, когда вы будете готовы включить свою среду Production.</span><span class="sxs-lookup"><span data-stu-id="fa70f-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="fa70f-133">Тестовая среда [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fa70f-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="fa70f-134">Производственная среда [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="fa70f-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="fa70f-135">Администратор Microsoft 365 и Администратор Microsoft 365 в вашей организации должны выполнить действия по настройке и сведениям на портале конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa70f-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="fa70f-136">Обратитесь к ресурсу "Переупоход", назначенного вашей организации.</span><span class="sxs-lookup"><span data-stu-id="fa70f-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="fa70f-137">Настройка сведений о компании-поставщике</span><span class="sxs-lookup"><span data-stu-id="fa70f-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="fa70f-138">Это этап должен быть выполнен администратором Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa70f-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="fa70f-139">Администратор Microsoft 365 должен запустить портал конфигурации соединителя и войти с учетными данными Майкрософт, чтобы начать настройку.</span><span class="sxs-lookup"><span data-stu-id="fa70f-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="fa70f-140">Для выполнения этого действия администратор Microsoft 365 должен получить действительный базовый URL-адрес FHIR от администратора Microsoft 365 и имя пользователя, который будет утверждать конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="fa70f-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="fa70f-141">Администратор Microsoft 365 должен запустить страницу конфигурации соединителя и войти с учетными данными Майкрософт, чтобы начать настройку.</span><span class="sxs-lookup"><span data-stu-id="fa70f-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="fa70f-142">Базовый URL-адрес FHIR — это статический адрес, соответствующий конечной точке API FHIR сервера.</span><span class="sxs-lookup"><span data-stu-id="fa70f-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="fa70f-143">Пример `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="fa70f-143">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="fa70f-144">Имя управляющего конфигурацией — это имя системного администратора ,который отвечает за утверждения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa70f-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![Имя утверждения конфигурации выбирается из списка в соединитеке EHR.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="fa70f-146">Проверка и утверждение конфигурации</span><span class="sxs-lookup"><span data-stu-id="fa70f-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="fa70f-147">Администратор Сайпа в вашей организации здравоохранения, добавленный в качестве утвержденного администратора, должен использовать для входа в службу с учетными данными Microsoft 365 тот же URL-адрес соединитора EHR, который использовался на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="fa70f-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="fa70f-148">После успешной проверки проверяемого попросят войти с учетными данными "Сергей" для проверки организации.</span><span class="sxs-lookup"><span data-stu-id="fa70f-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="fa70f-149">АдминистраторАми Microsoft 365 и Admin 365 в организациях могут быть один и тот же человек.</span><span class="sxs-lookup"><span data-stu-id="fa70f-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="fa70f-150">В этом случае на первом этапе добавьте свое имя пользователя в качестве утвержденного.</span><span class="sxs-lookup"><span data-stu-id="fa70f-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="fa70f-151">Для проверки доступа вам все равно потребуется войти в Учетную подпись.</span><span class="sxs-lookup"><span data-stu-id="fa70f-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="fa70f-152">Он используется только для проверки базового URL-адреса СЛФ.</span><span class="sxs-lookup"><span data-stu-id="fa70f-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="fa70f-153">Корпорация Майкрософт не будет хранить учетные данные или получать доступ к данным EHR при этом входе.</span><span class="sxs-lookup"><span data-stu-id="fa70f-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![Проверьте и утвердить конфигурацию учетных данных.](../../media/ehc-provider-2.png)

<span data-ttu-id="fa70f-155">После успешного входе в Агом администратор **должен** утвердить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="fa70f-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="fa70f-156">Если конфигурация неправилена, администратор Microsoft 365 сможет изменить исходные конфигурации, повторно вовшись на портал Microsoft EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="fa70f-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![Подтвердив настройку соединитела EHR и параметр для изменения конфигурации.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="fa70f-158">Просмотр и завершить настройку</span><span class="sxs-lookup"><span data-stu-id="fa70f-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="fa70f-159">Когда сведения о конфигурации будут утверждены администратором Вайла, вам будут представлены записи интеграции для запуска пациентов и поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="fa70f-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="fa70f-160">Эти записи необходимы для завершения настройки виртуального посещения в Будет.</span><span class="sxs-lookup"><span data-stu-id="fa70f-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="fa70f-161">Дополнительные сведения можно найти в Epic-Microsoft по интеграции с телетайлами Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="fa70f-162">Администратор Microsoft 365 или Microsoft 365 может в любое время войти на портал конфигурации, чтобы просмотреть записи интеграции и при необходимости изменить конфигурацию организации.</span><span class="sxs-lookup"><span data-stu-id="fa70f-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![Отобразились сведения об интеграции.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="fa70f-164">Запуск виртуальных посещений Teams</span><span class="sxs-lookup"><span data-stu-id="fa70f-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="fa70f-165">После выполнения действий по подключению eHR и настройке Учетной записи Майкрософт ваша организация готова поддерживать видеосегменты с помощью Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="fa70f-166">Предварительные условия виртуального посещения</span><span class="sxs-lookup"><span data-stu-id="fa70f-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="fa70f-167">Ваши системы должны соответствовать всем требованиям [к программному обеспечению и браузеру.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)</span><span class="sxs-lookup"><span data-stu-id="fa70f-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="fa70f-168">Организации здравоохранения должны завершить настройку между организацией "Организация Скайла" и Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa70f-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="fa70f-169">Опыт работы с поставщиком</span><span class="sxs-lookup"><span data-stu-id="fa70f-169">Provider experience</span></span>

<span data-ttu-id="fa70f-170">Поставщики здравоохранения из вашей организации также могут присоединяться к виртуальным посещениям Microsoft Teams из приложений поставщика услуг-поставщиков услуг Майкрософт (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="fa70f-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="fa70f-171">Кнопка **"Начать виртуальное** посещение" внедрена в поток поставщика услуг.</span><span class="sxs-lookup"><span data-stu-id="fa70f-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="fa70f-172">Основные функции работы поставщика:</span><span class="sxs-lookup"><span data-stu-id="fa70f-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="fa70f-173">Поставщики могут присоединяться к виртуальным посещениям с помощью поддерживаемых браузеров или приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="fa70f-174">Поставщики должны один раз войти в свою учетную запись Microsoft 365 при первом присоединении к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="fa70f-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="fa70f-175">После одновского входов поставщик будет сразу перенаправься на виртуальную встречу в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="fa70f-176">(Поставщик должен быть вписан в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="fa70f-177">Поставщик может в режиме реального времени видеть обновления участников, подключаться к назначенной встрече и отключать ее.</span><span class="sxs-lookup"><span data-stu-id="fa70f-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="fa70f-178">Поставщик может видеть, когда пациент подключен к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="fa70f-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Впечатления от виртуального визита с пациентом](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="fa70f-180">Patient experience</span><span class="sxs-lookup"><span data-stu-id="fa70f-180">Patient experience</span></span>

<span data-ttu-id="fa70f-181">Соединитестор поддерживает пациентов, которые присоединяются к виртуальным посещениям с помощью Веб-приложения MyChart и мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="fa70f-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="fa70f-182">Во время встречи пациенты могут начать виртуальный визит из myChart с помощью кнопки "Начать **виртуальный визит".**</span><span class="sxs-lookup"><span data-stu-id="fa70f-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="fa70f-183">Основные функции пациентов:</span><span class="sxs-lookup"><span data-stu-id="fa70f-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="fa70f-184">Пациенты могут присоединиться к виртуальным посещениям современных веб-браузеров на компьютере и мобильном устройстве без установки приложения.</span><span class="sxs-lookup"><span data-stu-id="fa70f-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="fa70f-185">Пациенты могут присоединиться к виртуальным посещениям одним щелчком мыши, а дополнительная учетная запись не требуется или вход не требуется.</span><span class="sxs-lookup"><span data-stu-id="fa70f-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="fa70f-186">Для запуска виртуального посещения пациенту не требуется создавать учетную запись Майкрософт или войди в нее.</span><span class="sxs-lookup"><span data-stu-id="fa70f-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="fa70f-187">Пациенты будут помещаются в "вестибюль", пока поставщик услуг здравоохранения не присоединится к встрече и не допустит их на виртуальный визит.</span><span class="sxs-lookup"><span data-stu-id="fa70f-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="fa70f-188">Тестирование видео и микрофона доступно в "вестибюле" перед присоединением к виртуальному посещению.</span><span class="sxs-lookup"><span data-stu-id="fa70f-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Patient experience of the virtual visit](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="fa70f-190">Также, MyChart, Haiku и Canto являются товарными знаками корпорации Systems.</span><span class="sxs-lookup"><span data-stu-id="fa70f-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="fa70f-191">Конфиденциальность и расположение данных</span><span class="sxs-lookup"><span data-stu-id="fa70f-191">Privacy and location of data</span></span>

<span data-ttu-id="fa70f-192">Интеграция Teams с системами EHR оптимизирует объем данных, которые используются и хранятся во время интеграции и потоков виртуального посещения.</span><span class="sxs-lookup"><span data-stu-id="fa70f-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="fa70f-193">Решение должно следовать общим принципам конфиденциальности и управления данными Teams, а также рекомендациям, описанным в этой области.</span><span class="sxs-lookup"><span data-stu-id="fa70f-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="fa70f-194">Соединиттель EHR для Microsoft Teams не хранит и не передает из системы EHR личные данные и медицинские записи пациентов и медицинских учреждений.</span><span class="sxs-lookup"><span data-stu-id="fa70f-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="fa70f-195">Единственными данными, которые хранятся соединитетелем EHR, является уникальный ИД пользователя EHR, который используется при настройке собрания Teams.</span><span class="sxs-lookup"><span data-stu-id="fa70f-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="fa70f-196">Уникальный ИД пользователя EHR хранится в одном из трех географических регионов, описанных в статье о месте хранения данных клиента [Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)</span><span class="sxs-lookup"><span data-stu-id="fa70f-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="fa70f-197">Все данные чата, записи и другие данные, вносяые участниками собрания в Teams, хранятся в соответствии с существующими политиками хранения.</span><span class="sxs-lookup"><span data-stu-id="fa70f-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="fa70f-198">Если вы хотите узнать больше о расположении данных в Microsoft Teams, посетите [веб-сайт с расположениями данных в Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)</span><span class="sxs-lookup"><span data-stu-id="fa70f-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
