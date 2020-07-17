---
title: Использование планировщика сети для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Администратор может научиться использовать планировщик сети для определения требований к сети для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8c6a59216d1ac04c0e079015aa9de13f8cecb37
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088237"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="a26f7-103">Использование планировщика сети для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a26f7-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="a26f7-104">Планировщик сети — это новое средство, доступное в центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="a26f7-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="a26f7-105">Его можно найти, перейдя в планировщик сети **планировщика**  >  **Network planner**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-105">It can be found by going to **Planner** > **Network planner**.</span></span> <span data-ttu-id="a26f7-106">В некоторых случаях планировщик сети поможет вам определить и упорядочить сетевые требования для подключения пользователей Microsoft Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="a26f7-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="a26f7-107">Когда вы предоставляете сведения о сети и использование Teams, планировщик сети вычисляет требования к сети для развертывания Teams и облачного голоса по физическим адресам Организации.</span><span class="sxs-lookup"><span data-stu-id="a26f7-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Снимок экрана: планировщик сети](media/network-planner.png)

<span data-ttu-id="a26f7-109">С помощью планировщика сети вы можете выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a26f7-109">Network planner allows you to:</span></span>

- <span data-ttu-id="a26f7-110">Создавайте представления своей организации с помощью сайтов и рекомендуемых Майкрософт пользователей (работников Office, удаленных работников и системы комнаты для Teams).</span><span class="sxs-lookup"><span data-stu-id="a26f7-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a26f7-111">Рекомендованные персонажи были разработаны на основе данных из рабочих групп, наиболее подходящих для использования, и типичных шаблонов использования.</span><span class="sxs-lookup"><span data-stu-id="a26f7-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="a26f7-112">Однако вы можете создать до трех специальных персонажей в дополнение к трем рекомендованным персонажам.</span><span class="sxs-lookup"><span data-stu-id="a26f7-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="a26f7-113">Создание отчетов и вычисление требований к пропускной способности для использования в Teams.</span><span class="sxs-lookup"><span data-stu-id="a26f7-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="a26f7-114">Для использования планировщика сети вы должны быть глобальным администратором, администратором службы Teams или администратором для связи с Team.</span><span class="sxs-lookup"><span data-stu-id="a26f7-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="a26f7-115">Создание собственного персонажа</span><span class="sxs-lookup"><span data-stu-id="a26f7-115">Create a custom persona</span></span>

<span data-ttu-id="a26f7-116">Для создания собственного персонажа выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a26f7-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="a26f7-117">Перейдите в планировщик сетей в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a26f7-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="a26f7-118">На вкладке **персонажи** щелкните значок **+ Настраиваемый персонаж**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="a26f7-119">В области **Новая настройка пользователя** добавьте имя и описание нового персонажа.</span><span class="sxs-lookup"><span data-stu-id="a26f7-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="a26f7-120">Выберите разрешения, которые пользователь может использовать в Организации.</span><span class="sxs-lookup"><span data-stu-id="a26f7-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="a26f7-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="a26f7-122">Создание плана</span><span class="sxs-lookup"><span data-stu-id="a26f7-122">Build your plan</span></span>

<span data-ttu-id="a26f7-123">Чтобы приступить к созданию плана сети, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a26f7-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="a26f7-124">Перейдите в планировщик сетей в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a26f7-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="a26f7-125">На вкладке **Сетевая схема** нажмите кнопку **Добавить сетевой план**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="a26f7-126">Введите имя и описание сетевого плана.</span><span class="sxs-lookup"><span data-stu-id="a26f7-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="a26f7-127">В списке доступных планов появится план сети.</span><span class="sxs-lookup"><span data-stu-id="a26f7-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="a26f7-128">Щелкните имя плана, чтобы выбрать новый план.</span><span class="sxs-lookup"><span data-stu-id="a26f7-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="a26f7-129">Добавьте сайты, чтобы создать представление настройки сети вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a26f7-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="a26f7-130">В зависимости от сети организации вы можете использовать сайты для представления здания, местоположения офиса или чего-то еще.</span><span class="sxs-lookup"><span data-stu-id="a26f7-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="a26f7-131">Сайты могут быть соединены через глобальную сеть, чтобы предоставить общий доступ к Интернету и/или PSTN-подключениям.</span><span class="sxs-lookup"><span data-stu-id="a26f7-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="a26f7-132">Для достижения наилучших результатов Создавайте сайты с локальными подключениями, прежде чем создавать сайты, которые подключаются к Интернету или КТСОП.</span><span class="sxs-lookup"><span data-stu-id="a26f7-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="a26f7-133">Чтобы создать сайт, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a26f7-133">To create a site:</span></span>

    1. <span data-ttu-id="a26f7-134">Добавьте имя и описание сайта.</span><span class="sxs-lookup"><span data-stu-id="a26f7-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="a26f7-135">В разделе **Параметры сети**введите количество пользователей сети на сайте (обязательно).</span><span class="sxs-lookup"><span data-stu-id="a26f7-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="a26f7-136">Дополнительные сведения о сети: поддержка глобальных сетей, емкость глобальной сети, выход из Интернета (**Локальная** или **Удаленная**) и коммутируемая сеть (нет, локальный или удаленный).</span><span class="sxs-lookup"><span data-stu-id="a26f7-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="a26f7-137">При создании отчета необходимо добавить номера, связанные с пропускной способностью, в глобальной сети и в Интернет-ресурсе.</span><span class="sxs-lookup"><span data-stu-id="a26f7-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="a26f7-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="a26f7-139">Создание отчета</span><span class="sxs-lookup"><span data-stu-id="a26f7-139">Create a report</span></span>

<span data-ttu-id="a26f7-140">После добавления всех сайтов вы можете создать отчет, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="a26f7-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="a26f7-141">На вкладке " **отчеты** " нажмите кнопку " **начать отчет**".</span><span class="sxs-lookup"><span data-stu-id="a26f7-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="a26f7-142">Для каждого сайта, который вы создаете, распределите количество пользователей по всем доступным персонажам.</span><span class="sxs-lookup"><span data-stu-id="a26f7-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="a26f7-143">Если вы используете Microsoft рекомендованных пользователей, номер будет распространяться автоматически (80% работников Office и 20%-е исполнителя).</span><span class="sxs-lookup"><span data-stu-id="a26f7-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="a26f7-144">После того как вы завершите распространение, нажмите **создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="a26f7-145">Созданный отчет будет показывать требования к пропускной способности в нескольких различных представлениях, чтобы вы могли ясно понять результат:</span><span class="sxs-lookup"><span data-stu-id="a26f7-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="a26f7-146">В таблице с отдельными вычислениями для каждой разрешенной деятельности будут отображаться требования к пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a26f7-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="a26f7-147">Дополнительное представление показывает общую пропускную способность, необходимую для рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="a26f7-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="a26f7-148">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a26f7-148">Click **Save**.</span></span> <span data-ttu-id="a26f7-149">Отчет будет доступен в списке "отчеты" для последующего просмотра.</span><span class="sxs-lookup"><span data-stu-id="a26f7-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="a26f7-150">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="a26f7-150">Example scenario</span></span>

<span data-ttu-id="a26f7-151">Пример использования планировщика сети для настройки плана сети и создания отчета с помощью описанных ниже действий можно скачать в PowerPoint из набора [слайдов "Планировщик сети](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) " (только на английском языке).</span><span class="sxs-lookup"><span data-stu-id="a26f7-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
