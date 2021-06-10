---
title: Настройка панели мониторинга качества звонка (CQD)
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
description: Узнайте, как включить и использовать панель мониторинга качества звонков и получить сводные отчеты о качестве звонков.
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254539"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="e6535-103">Настройка панели мониторинга качества звонка (CQD)</span><span class="sxs-lookup"><span data-stu-id="e6535-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="e6535-104">Откройте панель мониторинга качества звонка (CQD) Майкрософт по ссылке [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (войди с учетными данными администратора).</span><span class="sxs-lookup"><span data-stu-id="e6535-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="e6535-105">Или перейдите в Центр администрирования Teams и выберите **Панель мониторинга качества звонка**.</span><span class="sxs-lookup"><span data-stu-id="e6535-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Снимок экрана: кнопка панели мониторинга качества звонка в Teams администрирования":::

<span data-ttu-id="e6535-107">На открываемой странице нажмите кнопку **Войти** и введите учетную запись глобального администратора или Microsoft Teams учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="e6535-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Administrator account information.</span></span> <span data-ttu-id="e6535-108">После первого войти в CQD начнет сбор и обработку данных.</span><span class="sxs-lookup"><span data-stu-id="e6535-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="e6535-109">Имейте в виду, что обработка достаточного количества данных для отображения осмысленной информации в отчетах может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="e6535-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="e6535-110">В CQD показаны качество звонка и собрания на уровне организации для Microsoft Teams, Skype для бизнеса Online и Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e6535-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e6535-111">Чтобы использовать CQD в Skype для бизнеса Server 2019, необходимо настроить соединители данных [звонка.](/skypeforbusiness/hybrid/configure-call-data-connector)</span><span class="sxs-lookup"><span data-stu-id="e6535-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="e6535-112">Перед [началом работы см. планирование соединитела](/skypeforbusiness/hybrid/plan-call-data-connector) данных зова.</span><span class="sxs-lookup"><span data-stu-id="e6535-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="e6535-113">Назначение ролей администратора для доступа к CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="e6535-114">[Назначать](/microsoft-365/admin/add-users/about-admin-roles) роли для доступа к CQD людям, которые должны его использовать.</span><span class="sxs-lookup"><span data-stu-id="e6535-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="e6535-115">Если вы хотите, чтобы пользователи без администрирования (например, инженеры службы поддержки и агенты службы технической поддержки) могли использовать панель мониторинга качества звонка, вы можете назначить им одну из следующих ролей, которая обеспечивает доступ к CQD.</span><span class="sxs-lookup"><span data-stu-id="e6535-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="e6535-116">Просмотр отчетов</span><span class="sxs-lookup"><span data-stu-id="e6535-116">View reports</span></span>  |<span data-ttu-id="e6535-117">Просмотр полей EUII</span><span class="sxs-lookup"><span data-stu-id="e6535-117">View EUII fields</span></span>  |<span data-ttu-id="e6535-118">Создание отчетов</span><span class="sxs-lookup"><span data-stu-id="e6535-118">Create reports</span></span>  |<span data-ttu-id="e6535-119">Upload данных о здании</span><span class="sxs-lookup"><span data-stu-id="e6535-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="e6535-120">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="e6535-120">Global Administrator</span></span>     |<span data-ttu-id="e6535-121">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-121">Yes</span></span>         |<span data-ttu-id="e6535-122">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-122">Yes</span></span>         |<span data-ttu-id="e6535-123">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-123">Yes</span></span>         |<span data-ttu-id="e6535-124">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-124">Yes</span></span>         |
|<span data-ttu-id="e6535-125">Администратор Teams</span><span class="sxs-lookup"><span data-stu-id="e6535-125">Teams Administrator</span></span>     |<span data-ttu-id="e6535-126">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-126">Yes</span></span>         |<span data-ttu-id="e6535-127">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-127">Yes</span></span>         |<span data-ttu-id="e6535-128">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-128">Yes</span></span>         |<span data-ttu-id="e6535-129">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-129">Yes</span></span>         |
|<span data-ttu-id="e6535-130">Администратор коммуникаций Teams</span><span class="sxs-lookup"><span data-stu-id="e6535-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="e6535-131">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-131">Yes</span></span>         |<span data-ttu-id="e6535-132">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-132">Yes</span></span>         |<span data-ttu-id="e6535-133">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-133">Yes</span></span>         |<span data-ttu-id="e6535-134">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-134">Yes</span></span>         |
|<span data-ttu-id="e6535-135">Инженер поддержки по коммуникациям Teams</span><span class="sxs-lookup"><span data-stu-id="e6535-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="e6535-136">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-136">Yes</span></span>         |<span data-ttu-id="e6535-137">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-137">Yes</span></span>         |<span data-ttu-id="e6535-138">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-138">Yes</span></span>         |<span data-ttu-id="e6535-139">Нет</span><span class="sxs-lookup"><span data-stu-id="e6535-139">No</span></span>         |
|<span data-ttu-id="e6535-140">Teams Специалист службы поддержки связи</span><span class="sxs-lookup"><span data-stu-id="e6535-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="e6535-141">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-141">Yes</span></span>         |<span data-ttu-id="e6535-142">Нет</span><span class="sxs-lookup"><span data-stu-id="e6535-142">No</span></span>         |<span data-ttu-id="e6535-143">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-143">Yes</span></span>         |<span data-ttu-id="e6535-144">Нет</span><span class="sxs-lookup"><span data-stu-id="e6535-144">No</span></span>         |
|<span data-ttu-id="e6535-145">Skype для бизнеса Администратора</span><span class="sxs-lookup"><span data-stu-id="e6535-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="e6535-146">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-146">Yes</span></span>         |<span data-ttu-id="e6535-147">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-147">Yes</span></span>         |<span data-ttu-id="e6535-148">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-148">Yes</span></span>         |<span data-ttu-id="e6535-149">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-149">Yes</span></span>         |
|<span data-ttu-id="e6535-150">Global Reader</span><span class="sxs-lookup"><span data-stu-id="e6535-150">Global Reader</span></span> |<span data-ttu-id="e6535-151">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-151">Yes</span></span>         |<span data-ttu-id="e6535-152">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-152">Yes</span></span>         |<span data-ttu-id="e6535-153">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-153">Yes</span></span>         |<span data-ttu-id="e6535-154">Нет</span><span class="sxs-lookup"><span data-stu-id="e6535-154">No</span></span>         |
|<span data-ttu-id="e6535-155">Reports Reader<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e6535-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="e6535-156">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-156">Yes</span></span>         |<span data-ttu-id="e6535-157">Нет</span><span class="sxs-lookup"><span data-stu-id="e6535-157">No</span></span>         |<span data-ttu-id="e6535-158">Да</span><span class="sxs-lookup"><span data-stu-id="e6535-158">Yes</span></span>         |<span data-ttu-id="e6535-159">Нет</span><span class="sxs-lookup"><span data-stu-id="e6535-159">No</span></span>         |

<span data-ttu-id="e6535-160"><sup>1</sup> Помимо чтения отчетов CQD, читатель отчетов [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) может просматривать все отчеты об активности в Центре администрирования и отчеты из пакета содержимого для Microsoft 365 [внедрения.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)</span><span class="sxs-lookup"><span data-stu-id="e6535-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="e6535-161">Если вы не видите euII (зависимые сведения для конечного [пользователя)](CQD-data-and-reports.md#euii-data) и у вас есть одна из ролей, которая может видеть эти сведения, имейте в виду, что CQD хранится только в течение 28 дней.</span><span class="sxs-lookup"><span data-stu-id="e6535-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="e6535-162">Удаляются все данные старше 28 дней.</span><span class="sxs-lookup"><span data-stu-id="e6535-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="e6535-163">Дополнительные сведения об этих ролях см. в Office 365 [роли администраторов.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="e6535-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="e6535-164">После первого войти в CQD начнет сбор и обработку данных.</span><span class="sxs-lookup"><span data-stu-id="e6535-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="e6535-165">С декабря 2019 г. вы по-прежнему сможете получить доступ к старой версии CQD (cqd.lync.com), хотя на устаревшем портале вы можете получить ссылку на последнюю версию CQD (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e6535-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="e6535-166">Со временем более старая версия CQD будет списальна.</span><span class="sxs-lookup"><span data-stu-id="e6535-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="e6535-167">С 1 июля 2020 г. более старая версия CQD будет получать доступ к данным из последней версии CQD.</span><span class="sxs-lookup"><span data-stu-id="e6535-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="e6535-168">Перенос данных здания и отчетов из предыдущей версии CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6535-169">С 1 июля 2020 г. вы больше не сможете перенести данные о здании и отчеты из старого CQD https://CQD.lync.com) (.</span><span class="sxs-lookup"><span data-stu-id="e6535-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="e6535-170">Использование Power BI для анализа данных CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="e6535-171">Новое в январе 2020 г.: [скачивание шаблонов Power BI запросов для CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e6535-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="e6535-172">Настраиваемые Power BI шаблоны, которые можно использовать для анализа данных CQD и отчета о них.</span><span class="sxs-lookup"><span data-stu-id="e6535-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="e6535-173">Дополнительные сведения Power BI статью Использование Power BI для анализа данных [CQD.](CQD-Power-BI-query-templates.md)</span><span class="sxs-lookup"><span data-stu-id="e6535-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e6535-174">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e6535-174">Related topics</span></span>

[<span data-ttu-id="e6535-175">Улучшение и отслеживание качества звонка для Teams</span><span class="sxs-lookup"><span data-stu-id="e6535-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="e6535-176">Что такое CQD?</span><span class="sxs-lookup"><span data-stu-id="e6535-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="e6535-177">Upload данных о клиенте и здании</span><span class="sxs-lookup"><span data-stu-id="e6535-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="e6535-178">Данные и отчеты CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="e6535-179">Управление качеством звонка и собрания с помощью CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="e6535-180">Измерения и меры, доступные в CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="e6535-181">Классификация потоков в CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="e6535-182">Использование Power BI для анализа данных CQD</span><span class="sxs-lookup"><span data-stu-id="e6535-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)