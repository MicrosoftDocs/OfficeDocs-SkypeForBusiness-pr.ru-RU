---
title: Использование планировщика сети для Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Администратор может узнать, как использовать Планировщик сети для определения сетевых требований для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611803"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="9a024-103">Использование планировщика сети для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a024-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="9a024-104">Планировщик сетей — это новый инструмент, доступный в Центре администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="9a024-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="9a024-105">Его можно найти в **планировщике сети**  >  **планирования.**</span><span class="sxs-lookup"><span data-stu-id="9a024-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="9a024-106">С помощью Планировщика сетей можно всего несколькими шагами определить и упорядочеть требования к сети для подключения пользователей Microsoft Teams в организации.</span><span class="sxs-lookup"><span data-stu-id="9a024-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="9a024-107">При предоставлении сведений о сети и использовании Teams планировщик сети рассчитывает требования к сети для развертывания Teams и облачного голосового связи в физических расположениях организации.</span><span class="sxs-lookup"><span data-stu-id="9a024-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Снимок экрана: планировщик сети](media/network-planner.png)

<span data-ttu-id="9a024-109">Планировщик сети позволяет:</span><span class="sxs-lookup"><span data-stu-id="9a024-109">Network planner allows you to:</span></span>

- <span data-ttu-id="9a024-110">Создавайте представления своей организации с помощью сайтов и рекомендуемых Майкрософт людей (офисных сотрудников, удаленных сотрудников и системы комнат Teams).</span><span class="sxs-lookup"><span data-stu-id="9a024-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a024-111">Рекомендуемые типовые группы были разработаны на основе данных из сценариев использования Teams и типичных шаблонов использования.</span><span class="sxs-lookup"><span data-stu-id="9a024-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="9a024-112">Однако вы можете создать до трех пользовательских людей в дополнение к трем рекомендуемых.</span><span class="sxs-lookup"><span data-stu-id="9a024-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="9a024-113">Создание отчетов и расчет требований к пропускной способности для использования Teams.</span><span class="sxs-lookup"><span data-stu-id="9a024-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="9a024-114">Для использования планировщика сети необходимо быть глобальным администратором, администратором служб Teams или администратором связи Teams.</span><span class="sxs-lookup"><span data-stu-id="9a024-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="9a024-115">Создание пользовательского лица</span><span class="sxs-lookup"><span data-stu-id="9a024-115">Create a custom persona</span></span>

<span data-ttu-id="9a024-116">Чтобы создать пользовательское лицо, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="9a024-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="9a024-117">Перейдите в планировщик сетей в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a024-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="9a024-118">На **вкладке "Люди"** нажмите кнопку **+Пользовательский пользователь.**</span><span class="sxs-lookup"><span data-stu-id="9a024-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="9a024-119">В области **"Новый пользователь"** добавьте имя и описание нового человека.</span><span class="sxs-lookup"><span data-stu-id="9a024-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="9a024-120">Выберите разрешения, которые этот человек будет использовать в организации.</span><span class="sxs-lookup"><span data-stu-id="9a024-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="9a024-121">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a024-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="9a024-122">Создание плана</span><span class="sxs-lookup"><span data-stu-id="9a024-122">Build your plan</span></span>

<span data-ttu-id="9a024-123">Чтобы приступить к построению сетевого плана, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="9a024-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="9a024-124">Перейдите в планировщик сетей в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a024-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="9a024-125">На **вкладке "План сети"** нажмите кнопку **"Добавить план сети".**</span><span class="sxs-lookup"><span data-stu-id="9a024-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="9a024-126">Введите имя и описание сетевого плана.</span><span class="sxs-lookup"><span data-stu-id="9a024-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="9a024-127">План сети появится в списке доступных планов.</span><span class="sxs-lookup"><span data-stu-id="9a024-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="9a024-128">Щелкните имя плана, чтобы выбрать новый план.</span><span class="sxs-lookup"><span data-stu-id="9a024-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="9a024-129">Добавьте сайты, чтобы создать представление настройки сети организации.</span><span class="sxs-lookup"><span data-stu-id="9a024-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="9a024-130">В зависимости от сети организации вы можете использовать сайты для представления здания, расположения офиса или другого объекта.</span><span class="sxs-lookup"><span data-stu-id="9a024-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="9a024-131">Сайты могут быть подключены по сети WAN, чтобы разрешить совместный доступ к Интернету и (или) подключениям по STN.</span><span class="sxs-lookup"><span data-stu-id="9a024-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="9a024-132">Для лучших результатов создайте сайты с локальными подключениями, прежде чем создавать сайты, которые будут удаленно подключаться к Интернету или STN.</span><span class="sxs-lookup"><span data-stu-id="9a024-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="9a024-133">Чтобы создать сайт:</span><span class="sxs-lookup"><span data-stu-id="9a024-133">To create a site:</span></span>

    1. <span data-ttu-id="9a024-134">Добавьте имя и описание сайта.</span><span class="sxs-lookup"><span data-stu-id="9a024-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="9a024-135">В **параметрах сети** добавьте количество пользователей сети на этом сайте (обязательно).</span><span class="sxs-lookup"><span data-stu-id="9a024-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="9a024-136">Добавьте сведения о сети: пропускную способность для WAN, пропускную способность по интернету **(локальный** или удаленный) и ДНР (отсутствует, локальный или удаленный).</span><span class="sxs-lookup"><span data-stu-id="9a024-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="9a024-137">Для получения определенных рекомендаций по пропускной способности при созданием отчета необходимо добавить номера пропускной способности WAN и Интернета.</span><span class="sxs-lookup"><span data-stu-id="9a024-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="9a024-138">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a024-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="9a024-139">Создание отчета</span><span class="sxs-lookup"><span data-stu-id="9a024-139">Create a report</span></span>

<span data-ttu-id="9a024-140">После добавления всех сайтов можно создать отчет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a024-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="9a024-141">На **вкладке "Отчеты"** нажмите кнопку **"Начать отчет".**</span><span class="sxs-lookup"><span data-stu-id="9a024-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="9a024-142">Для каждого создаемого сайта распределяйте по всем доступным пользователям количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="9a024-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="9a024-143">Если вы используете рекомендуемые корпорацией Майкрософт номера сотрудников, они будут распределяться автоматически (80 % сотрудников офисных служб и 20 % удаленных сотрудников).</span><span class="sxs-lookup"><span data-stu-id="9a024-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="9a024-144">После завершения распространения нажмите кнопку **"Создать отчет".**</span><span class="sxs-lookup"><span data-stu-id="9a024-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="9a024-145">В сгенерированном отчете будут демонстрироваться требования к пропускной способности в нескольких различных представлениях, что позволит понять выходные данные.</span><span class="sxs-lookup"><span data-stu-id="9a024-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="9a024-146">В таблице с индивидуальными вычислениями будут отображаться требования к пропускной способности для каждого разрешенного действия.</span><span class="sxs-lookup"><span data-stu-id="9a024-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="9a024-147">В дополнительном представлении будут демонстрироваться общие потребности в пропускной способности с рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="9a024-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="9a024-148">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9a024-148">Click **Save**.</span></span> <span data-ttu-id="9a024-149">Отчет будет доступен в списке отчетов для просмотра в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="9a024-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="9a024-150">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="9a024-150">Example scenario</span></span>

<span data-ttu-id="9a024-151">Пример использования планировщика сети для создания сетевого плана и создания отчета с помощью этих действий см. в презентации PowerPoint How-To "Сетевой планировщик" [(только](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) на английском языке).</span><span class="sxs-lookup"><span data-stu-id="9a024-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
