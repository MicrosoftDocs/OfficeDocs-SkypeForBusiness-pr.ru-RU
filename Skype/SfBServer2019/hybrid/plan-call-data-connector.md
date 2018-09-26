---
title: Планирование подключения к данным звонка
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Общие сведения об использовании Скайп для бизнеса в Интернет средства телеметрии для отслеживания локальной реализации в гибридном сценарии.
ms.openlocfilehash: 2c491a217f02af77a25f362697e6f89aceb9470c
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "25030702"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="c4f96-103">Планирование подключения к данным звонка</span><span class="sxs-lookup"><span data-stu-id="c4f96-103">Plan Call Data Connector</span></span>

[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="c4f96-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="c4f96-104">Overview</span></span>
<span data-ttu-id="c4f96-105">В этом разделе описываются преимущества, рекомендации по планированию и требования к внедрению Скайп для соединителя вызова данных Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4f96-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="c4f96-106">Дополнительные сведения о настройке вызова подключения к данным содержатся в разделе [Настройка вызова подключения к данным](configure-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c4f96-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c4f96-107">В выпуске ознакомительной версии доступна только вызова Analytics панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="c4f96-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="c4f96-108">Подключения к данным вызова существенно упрощает вызов мониторинга в гибридной среде, так как больше не требуется для использования различных наборов локальной и online средства для наблюдения за всеми качество звонка пользователей.</span><span class="sxs-lookup"><span data-stu-id="c4f96-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="c4f96-109">Пользователи, размещенные локально или через Интернет, ли можно выбрать для просмотра качества звонка для всей организации в Интернете.</span><span class="sxs-lookup"><span data-stu-id="c4f96-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="c4f96-110">С помощью вызова подключения к данным с помощью одного набора инструментов можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c4f96-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="c4f96-111">Мониторинг вам группами Майкрософт, Скайп для бизнеса в Интернет и Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4f96-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="c4f96-112">Просмотр и устранение неполадок в сети.</span><span class="sxs-lookup"><span data-stu-id="c4f96-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="c4f96-113">Назначение роли администратора и служба технической поддержки для вызова анализа, позволяют сотрудникам служба технической поддержки для просмотра и устранения неполадок их области ответственности.</span><span class="sxs-lookup"><span data-stu-id="c4f96-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="c4f96-114">С помощью вызова подключения к данным Скайп для Business Server помещает данных вызовов в облачную службу таким образом, вы можете использовать возможности Скайп средства Business Online Analytics вызова (ЦС) и вызвать панель мониторинга качества (CQD), как показано на рисунке:</span><span class="sxs-lookup"><span data-stu-id="c4f96-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![Облако SfB голосовой почты](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="c4f96-116">Сервер передает качества взаимодействия (QoE) и данных регистрации вызовов соединений (CDR) Интернет-службы.</span><span class="sxs-lookup"><span data-stu-id="c4f96-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="c4f96-117">Вызвать аналитики и средств CQD позволяют контроля качества звонков и устранения ошибок с группами Майкрософт и Скайп для бизнес-служб следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4f96-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="c4f96-118">Вызов Analytics фокусируется на звучания вызовов.</span><span class="sxs-lookup"><span data-stu-id="c4f96-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="c4f96-119">Теперь показаны подробные сведения о вызовах и собрания для каждого пользователя в Скайп для учетной записи бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c4f96-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="c4f96-120">С помощью вызова анализа служба технической поддержки оператор, который затем можно отслеживать вызовы без доступа к остальной части Скайп по центру администрирования бизнес можно назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="c4f96-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="c4f96-121">Панель мониторинга качества звонков основное внимание уделяется производительности сети и проблемы в организации.</span><span class="sxs-lookup"><span data-stu-id="c4f96-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="c4f96-122">Скайп для бизнеса администраторов и инженеров сети это средство предназначено для устранения неполадок и оптимизировать производительность сети.</span><span class="sxs-lookup"><span data-stu-id="c4f96-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="c4f96-123">Дополнительные сведения можно [вызвать аналитики и панель мониторинга качества звонков](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="c4f96-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="c4f96-124">Конечно может потребоваться сохранить некоторые данные о качестве вызовов локально.</span><span class="sxs-lookup"><span data-stu-id="c4f96-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="c4f96-125">Это может быть в случае, например, при использовании решения сторонних производителей с настраиваемые отчеты и рабочие процессы.</span><span class="sxs-lookup"><span data-stu-id="c4f96-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="c4f96-126">Подключения к данным вызова позволяет настроить отправки данных на Интернет-службы, сохраняя также копирование данных на локальном сервере, как показано на рисунке:</span><span class="sxs-lookup"><span data-stu-id="c4f96-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![Облако SfB голосовой почты](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a><span data-ttu-id="c4f96-128">Требования</span><span class="sxs-lookup"><span data-stu-id="c4f96-128">Requirements</span></span>

<span data-ttu-id="c4f96-129">Следующие требования предполагается, что вы уже Скайп для Business Server, развернутые в поддерживаемых топологий.</span><span class="sxs-lookup"><span data-stu-id="c4f96-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="c4f96-130">Дополнительные сведения о развертывании Скайп Business Server и поддерживаемые топологии можно [Основы топологии](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span><span class="sxs-lookup"><span data-stu-id="c4f96-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span>

- <span data-ttu-id="c4f96-131">Гибридного подключения.</span><span class="sxs-lookup"><span data-stu-id="c4f96-131">Hybrid connectivity.</span></span> <span data-ttu-id="c4f96-132">Уже Скайп Business Server развернут, чтобы разрешить вызов подключения к данным необходимо убедиться, что имеются гибридного подключения между локальной и сетевой средах.</span><span class="sxs-lookup"><span data-stu-id="c4f96-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="c4f96-133">Это иногда называется конфигурации домена разделения.</span><span class="sxs-lookup"><span data-stu-id="c4f96-133">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="c4f96-134">Дополнительные сведения см в [планировании гибридного подключения между Скайп Business Server и Office 365](plan-hybrid-connectivity.md) и [Настройка гибридного подключения между Скайп Business Server и Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c4f96-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="c4f96-135">Для настройки вызова подключения к данным, необходимо проверить подлинность клиента Office 365 и убедитесь, что у вас есть включены следующие роли:</span><span class="sxs-lookup"><span data-stu-id="c4f96-135">To configure Call Data Connector, you must authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

   - <span data-ttu-id="c4f96-136">Скайп для администратора сервера</span><span class="sxs-lookup"><span data-stu-id="c4f96-136">Skype for Business Server Administrator</span></span> 
   - <span data-ttu-id="c4f96-137">Глобальный администратор Office 365</span><span class="sxs-lookup"><span data-stu-id="c4f96-137">Office 365 Global Administrator</span></span> 

- <span data-ttu-id="c4f96-138">Если вы еще не сделали Включение панели мониторинга качества звонков как описано в разделе [Включение и с помощью вызова панели мониторинга качества для групп Майкрософт и Скайп для бизнеса в Интернет](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="c4f96-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="c4f96-139">Сравнение локальной и online вызов качества панели мониторинга (CQD) отчетов</span><span class="sxs-lookup"><span data-stu-id="c4f96-139">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="c4f96-140">Функции отчетов</span><span class="sxs-lookup"><span data-stu-id="c4f96-140">Feature reports</span></span> | <span data-ttu-id="c4f96-141">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="c4f96-141">Skype for Business Online</span></span> | <span data-ttu-id="c4f96-142">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c4f96-142">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="c4f96-143">Показатель общего доступа приложения</span><span class="sxs-lookup"><span data-stu-id="c4f96-143">Application sharing metric</span></span> |<span data-ttu-id="c4f96-144">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-144">Yes</span></span> | <span data-ttu-id="c4f96-145">Ограниченные</span><span class="sxs-lookup"><span data-stu-id="c4f96-145">Limited</span></span> |
| <span data-ttu-id="c4f96-146">Стандартные сведения о клиенте</span><span class="sxs-lookup"><span data-stu-id="c4f96-146">Customer building information</span></span>| <span data-ttu-id="c4f96-147">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-147">Yes</span></span> | <span data-ttu-id="c4f96-148">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-148">Yes</span></span> |
| <span data-ttu-id="c4f96-149">Аналитика перехода</span><span class="sxs-lookup"><span data-stu-id="c4f96-149">Drill-down analytics</span></span> | <span data-ttu-id="c4f96-150">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-150">Yes</span></span> | <span data-ttu-id="c4f96-151">Нет</span><span class="sxs-lookup"><span data-stu-id="c4f96-151">No</span></span> |
| <span data-ttu-id="c4f96-152">Показателей надежности</span><span class="sxs-lookup"><span data-stu-id="c4f96-152">Media reliability metrics</span></span> | <span data-ttu-id="c4f96-153">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-153">Yes</span></span> | <span data-ttu-id="c4f96-154">Ограниченные</span><span class="sxs-lookup"><span data-stu-id="c4f96-154">Limited</span></span> |
| <span data-ttu-id="c4f96-155">Отчеты о ожидания введите</span><span class="sxs-lookup"><span data-stu-id="c4f96-155">Out-of-the-box reports</span></span> | <span data-ttu-id="c4f96-156">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-156">Yes</span></span> | <span data-ttu-id="c4f96-157">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-157">Yes</span></span> |
| <span data-ttu-id="c4f96-158">Обзор отчетов</span><span class="sxs-lookup"><span data-stu-id="c4f96-158">Overview reports</span></span> | <span data-ttu-id="c4f96-159">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-159">Yes</span></span> | <span data-ttu-id="c4f96-160">Нет</span><span class="sxs-lookup"><span data-stu-id="c4f96-160">No</span></span> |
| <span data-ttu-id="c4f96-161">На пользовательские отчеты</span><span class="sxs-lookup"><span data-stu-id="c4f96-161">Per user reports</span></span> | <span data-ttu-id="c4f96-162">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-162">Yes</span></span> | <span data-ttu-id="c4f96-163">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-163">Yes</span></span> |
| <span data-ttu-id="c4f96-164">Настройка отчетов</span><span class="sxs-lookup"><span data-stu-id="c4f96-164">Report set customization</span></span> <br> <span data-ttu-id="c4f96-165">(Добавление, удаление и изменение отчетов)</span><span class="sxs-lookup"><span data-stu-id="c4f96-165">(add, delete, modify reports)</span></span> | <span data-ttu-id="c4f96-166">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-166">Yes</span></span> | <span data-ttu-id="c4f96-167">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-167">Yes</span></span> |
| <span data-ttu-id="c4f96-168">На основе видео экрана показатели общего доступа</span><span class="sxs-lookup"><span data-stu-id="c4f96-168">Video-based screen sharing metrics</span></span> | <span data-ttu-id="c4f96-169">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-169">Yes</span></span> | <span data-ttu-id="c4f96-170">Нет</span><span class="sxs-lookup"><span data-stu-id="c4f96-170">No</span></span> |
| <span data-ttu-id="c4f96-171">Данные API-интерфейсы для программного доступа</span><span class="sxs-lookup"><span data-stu-id="c4f96-171">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="c4f96-172">Чтобы CQD</span><span class="sxs-lookup"><span data-stu-id="c4f96-172">to CQD</span></span> | <span data-ttu-id="c4f96-173">Нет</span><span class="sxs-lookup"><span data-stu-id="c4f96-173">No</span></span> | <span data-ttu-id="c4f96-174">Да</span><span class="sxs-lookup"><span data-stu-id="c4f96-174">Yes</span></span> |



















