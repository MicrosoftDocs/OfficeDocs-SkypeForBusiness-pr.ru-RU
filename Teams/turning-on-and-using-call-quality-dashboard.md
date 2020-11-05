---
title: Настройка панели мониторинга качества звонков (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Сведения о том, как включить и использовать панель мониторинга качества звонков и получить суммарные отчеты о качестве звонков.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918646"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="20668-103">Настройка панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="20668-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="20668-104">Откройте панель мониторинга качества звонков (CQD) на странице [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (войдите с учетными данными администратора).</span><span class="sxs-lookup"><span data-stu-id="20668-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="20668-105">Или перейдите в центр администрирования Teams и выберите **панель мониторинга качества звонков**.</span><span class="sxs-lookup"><span data-stu-id="20668-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонка в центре администрирования Teams":::

<span data-ttu-id="20668-107">На открывшейся странице нажмите **Вход** и введите глобальную учетную запись администратора или сведения об учетной записи администратора Microsoft Teams Service.</span><span class="sxs-lookup"><span data-stu-id="20668-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="20668-108">После первого входа CQD начнет сбор и обработку данных.</span><span class="sxs-lookup"><span data-stu-id="20668-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="20668-109">Имейте в виду, что для обработки достаточного количества данных для отображения значимых результатов в отчетах может потребоваться одно или несколько часов.</span><span class="sxs-lookup"><span data-stu-id="20668-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="20668-110">CQD отображает качество звонков и собраний на уровне Организации, для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="20668-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="20668-111">Для использования CQD в Skype для бизнеса Server 2019 необходимо [настроить соединитель данных звонка](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="20668-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="20668-112">Прежде чем приступить к работе, ознакомьтесь с [соединителем для связи с данными](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) .</span><span class="sxs-lookup"><span data-stu-id="20668-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="20668-113">Назначение ролей администратора для доступа к CQD</span><span class="sxs-lookup"><span data-stu-id="20668-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="20668-114">Назначение [ролей](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) для доступа к CQD людям, которым нужно пользоваться.</span><span class="sxs-lookup"><span data-stu-id="20668-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="20668-115">Если вы хотите, чтобы пользователи, не являющиеся администраторами (например, инженерами службы поддержки и агентами справочных служб) могли использовать панель мониторинга качества звонков, вы можете назначить этих пользователей одну из следующих ролей, которая предоставляет доступ к CQD.</span><span class="sxs-lookup"><span data-stu-id="20668-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="20668-116">Просмотр отчетов</span><span class="sxs-lookup"><span data-stu-id="20668-116">View reports</span></span>  |<span data-ttu-id="20668-117">Просмотр полей EUII</span><span class="sxs-lookup"><span data-stu-id="20668-117">View EUII fields</span></span>  |<span data-ttu-id="20668-118">Создание отчетов</span><span class="sxs-lookup"><span data-stu-id="20668-118">Create reports</span></span>  |<span data-ttu-id="20668-119">Отправка данных о сборке</span><span class="sxs-lookup"><span data-stu-id="20668-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="20668-120">Глобальный администратор Office 365</span><span class="sxs-lookup"><span data-stu-id="20668-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="20668-121">Да</span><span class="sxs-lookup"><span data-stu-id="20668-121">Yes</span></span>         |<span data-ttu-id="20668-122">Да</span><span class="sxs-lookup"><span data-stu-id="20668-122">Yes</span></span>         |<span data-ttu-id="20668-123">Да</span><span class="sxs-lookup"><span data-stu-id="20668-123">Yes</span></span>         |<span data-ttu-id="20668-124">Да</span><span class="sxs-lookup"><span data-stu-id="20668-124">Yes</span></span>         |
|<span data-ttu-id="20668-125">Администратор служб Teams</span><span class="sxs-lookup"><span data-stu-id="20668-125">Teams Service Administrator</span></span>     |<span data-ttu-id="20668-126">Да</span><span class="sxs-lookup"><span data-stu-id="20668-126">Yes</span></span>         |<span data-ttu-id="20668-127">Да</span><span class="sxs-lookup"><span data-stu-id="20668-127">Yes</span></span>         |<span data-ttu-id="20668-128">Да</span><span class="sxs-lookup"><span data-stu-id="20668-128">Yes</span></span>         |<span data-ttu-id="20668-129">Да</span><span class="sxs-lookup"><span data-stu-id="20668-129">Yes</span></span>         |
|<span data-ttu-id="20668-130">Администратор коммуникаций Teams</span><span class="sxs-lookup"><span data-stu-id="20668-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="20668-131">Да</span><span class="sxs-lookup"><span data-stu-id="20668-131">Yes</span></span>         |<span data-ttu-id="20668-132">Да</span><span class="sxs-lookup"><span data-stu-id="20668-132">Yes</span></span>         |<span data-ttu-id="20668-133">Да</span><span class="sxs-lookup"><span data-stu-id="20668-133">Yes</span></span>         |<span data-ttu-id="20668-134">Да</span><span class="sxs-lookup"><span data-stu-id="20668-134">Yes</span></span>         |
|<span data-ttu-id="20668-135">Инженер поддержки по коммуникациям Teams</span><span class="sxs-lookup"><span data-stu-id="20668-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="20668-136">Да</span><span class="sxs-lookup"><span data-stu-id="20668-136">Yes</span></span>         |<span data-ttu-id="20668-137">Да</span><span class="sxs-lookup"><span data-stu-id="20668-137">Yes</span></span>         |<span data-ttu-id="20668-138">Да</span><span class="sxs-lookup"><span data-stu-id="20668-138">Yes</span></span>         |<span data-ttu-id="20668-139">Нет</span><span class="sxs-lookup"><span data-stu-id="20668-139">No</span></span>         |
|<span data-ttu-id="20668-140">Специалист по поддержке взаимодействия в Teams</span><span class="sxs-lookup"><span data-stu-id="20668-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="20668-141">Да</span><span class="sxs-lookup"><span data-stu-id="20668-141">Yes</span></span>         |<span data-ttu-id="20668-142">Нет</span><span class="sxs-lookup"><span data-stu-id="20668-142">No</span></span>         |<span data-ttu-id="20668-143">Да</span><span class="sxs-lookup"><span data-stu-id="20668-143">Yes</span></span>         |<span data-ttu-id="20668-144">Нет</span><span class="sxs-lookup"><span data-stu-id="20668-144">No</span></span>         |
|<span data-ttu-id="20668-145">Администратор Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="20668-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="20668-146">Да</span><span class="sxs-lookup"><span data-stu-id="20668-146">Yes</span></span>         |<span data-ttu-id="20668-147">Да</span><span class="sxs-lookup"><span data-stu-id="20668-147">Yes</span></span>         |<span data-ttu-id="20668-148">Да</span><span class="sxs-lookup"><span data-stu-id="20668-148">Yes</span></span>         |<span data-ttu-id="20668-149">Да</span><span class="sxs-lookup"><span data-stu-id="20668-149">Yes</span></span>         |
|<span data-ttu-id="20668-150">Глобальный читатель Azure AD</span><span class="sxs-lookup"><span data-stu-id="20668-150">Azure AD Global Reader</span></span> |<span data-ttu-id="20668-151">Да</span><span class="sxs-lookup"><span data-stu-id="20668-151">Yes</span></span>         |<span data-ttu-id="20668-152">Да</span><span class="sxs-lookup"><span data-stu-id="20668-152">Yes</span></span>         |<span data-ttu-id="20668-153">Да</span><span class="sxs-lookup"><span data-stu-id="20668-153">Yes</span></span>         |<span data-ttu-id="20668-154">Нет</span><span class="sxs-lookup"><span data-stu-id="20668-154">No</span></span>         |
|<span data-ttu-id="20668-155">Office 365 сообщает читателям<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="20668-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="20668-156">Да</span><span class="sxs-lookup"><span data-stu-id="20668-156">Yes</span></span>         |<span data-ttu-id="20668-157">Нет</span><span class="sxs-lookup"><span data-stu-id="20668-157">No</span></span>         |<span data-ttu-id="20668-158">Да</span><span class="sxs-lookup"><span data-stu-id="20668-158">Yes</span></span>         |<span data-ttu-id="20668-159">Нет</span><span class="sxs-lookup"><span data-stu-id="20668-159">No</span></span>         |

<span data-ttu-id="20668-160"><sup>1</sup> в дополнение к ЧТЕНию CQDных отчетов Office 365 может просматривать все [отчеты об активности](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) в центре администрирования и любые отчеты из пакета содержимого для оценки [внедрения Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span><span class="sxs-lookup"><span data-stu-id="20668-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="20668-161">Если вы не видите [EUII (сведения для конечных пользователей)](CQD-data-and-reports.md#euii-data) и у вас есть одна из ролей, которые могут просматривать эти данные, имейте в виду, что CQD только в течение 28 дней.</span><span class="sxs-lookup"><span data-stu-id="20668-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="20668-162">Все, более 28 дней, удаляются.</span><span class="sxs-lookup"><span data-stu-id="20668-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="20668-163">Дополнительные сведения об этих ролях можно найти в разделе [о ролях администратора Office 365](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="20668-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="20668-164">После первого входа CQD начнет сбор и обработку данных.</span><span class="sxs-lookup"><span data-stu-id="20668-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="20668-165">По истечении декабря 2019 вы по-прежнему можете получать доступ к более ранней версии CQD (cqd.lync.com), несмотря на то, что на портале Legacy есть ссылка на последнюю версию CQD (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="20668-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="20668-166">В конечном итоге старая версия CQD будет списана.</span><span class="sxs-lookup"><span data-stu-id="20668-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="20668-167">По истечении 1 июля 2020 в более ранней версии CQD доступ к данным из последнего CQD.</span><span class="sxs-lookup"><span data-stu-id="20668-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="20668-168">Миграция данных и отчетов из предыдущей версии CQD</span><span class="sxs-lookup"><span data-stu-id="20668-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20668-169">Начиная с 1 июля 2020 г., вы больше не сможете переносить данные построения и отчеты из старой CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="20668-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="20668-170">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="20668-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="20668-171">Новые возможности в январе 2020: [Скачайте шаблоны запросов Power BI для CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="20668-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="20668-172">Настраиваемые шаблоны Power BI, которые можно использовать для анализа и составления отчетов о CQD данных.</span><span class="sxs-lookup"><span data-stu-id="20668-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="20668-173">Чтение с [помощью Power BI для анализа данных CQD](CQD-Power-BI-query-templates.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="20668-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="20668-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="20668-174">Related topics</span></span>

[<span data-ttu-id="20668-175">Улучшение и мониторинг качества связи для Teams</span><span class="sxs-lookup"><span data-stu-id="20668-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="20668-176">Что такое CQD?</span><span class="sxs-lookup"><span data-stu-id="20668-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="20668-177">Отправка клиента и создание данных</span><span class="sxs-lookup"><span data-stu-id="20668-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="20668-178">Данные CQD и отчеты</span><span class="sxs-lookup"><span data-stu-id="20668-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="20668-179">Использование CQD для управления качеством звонков и собраний</span><span class="sxs-lookup"><span data-stu-id="20668-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="20668-180">Измерения и меры, доступные в CQD</span><span class="sxs-lookup"><span data-stu-id="20668-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="20668-181">Классификация потоков в CQD</span><span class="sxs-lookup"><span data-stu-id="20668-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="20668-182">Анализ данных CQD с помощью Power BI</span><span class="sxs-lookup"><span data-stu-id="20668-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
