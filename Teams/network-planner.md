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
description: Администратор может узнать, как с помощью планировщика сети определить требования к сети для Microsoft Teams.
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
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240482"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="de47f-103">Использование планировщика сети для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de47f-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="de47f-104">Планировщик сети — это новое средство, доступное в центре Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="de47f-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="de47f-105">Его можно найти, посетив **планировщик сети**  >  **планирования**.</span><span class="sxs-lookup"><span data-stu-id="de47f-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="de47f-106">С помощью планировщика сетей можно всего за несколько шагов определить и упорядочести требования к сети для Microsoft Teams пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="de47f-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="de47f-107">Когда вы предоставляете сведения о сети и об использовании Teams, планировщик сети вычисляет требования к сети для развертывания Teams и облачных решений голосовой связи в физических расположениях вашей организации.</span><span class="sxs-lookup"><span data-stu-id="de47f-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![Снимок экрана: планировщик сети](media/network-planner.png)

<span data-ttu-id="de47f-109">Планировщик сети позволяет:</span><span class="sxs-lookup"><span data-stu-id="de47f-109">Network planner allows you to:</span></span>

- <span data-ttu-id="de47f-110">Создавайте представления своей организации с помощью сайтов и рекомендуемых Майкрософт лиц (офисных сотрудников, удаленных сотрудников и Teams комнат).</span><span class="sxs-lookup"><span data-stu-id="de47f-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="de47f-111">Рекомендуемые лица были разработаны на основе данных из Teams сценариев использования и типичных шаблонов использования.</span><span class="sxs-lookup"><span data-stu-id="de47f-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="de47f-112">Однако вы можете создать до трех пользовательских людей в дополнение к трем рекомендуемых.</span><span class="sxs-lookup"><span data-stu-id="de47f-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="de47f-113">Создание отчетов и расчет требований к пропускной способности для Teams использования.</span><span class="sxs-lookup"><span data-stu-id="de47f-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="de47f-114">Для использования планировщика сети необходимо быть глобальным администратором, администратором Teams или администратором Teams связи.</span><span class="sxs-lookup"><span data-stu-id="de47f-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="de47f-115">Создание пользовательского лица</span><span class="sxs-lookup"><span data-stu-id="de47f-115">Create a custom persona</span></span>

<span data-ttu-id="de47f-116">Чтобы создать настраиваемый пользователь, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="de47f-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="de47f-117">Перейдите в планировщик сети в центре Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="de47f-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="de47f-118">На **вкладке "Люди"** нажмите **кнопку + Пользовательская.**</span><span class="sxs-lookup"><span data-stu-id="de47f-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="de47f-119">В **области Новый пользовательский пользователь в** добавьте имя и описание нового человека.</span><span class="sxs-lookup"><span data-stu-id="de47f-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="de47f-120">Выберите разрешения, которые этот человек будет использовать в организации.</span><span class="sxs-lookup"><span data-stu-id="de47f-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="de47f-121">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="de47f-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="de47f-122">Создание плана</span><span class="sxs-lookup"><span data-stu-id="de47f-122">Build your plan</span></span>

<span data-ttu-id="de47f-123">Чтобы приступить к построению сетевого плана, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="de47f-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="de47f-124">Перейдите в планировщик сети в центре Microsoft Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="de47f-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="de47f-125">На **вкладке План** сети нажмите **кнопку Добавить план сети**.</span><span class="sxs-lookup"><span data-stu-id="de47f-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="de47f-126">Введите имя и описание сетевого плана.</span><span class="sxs-lookup"><span data-stu-id="de47f-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="de47f-127">План сети появится в списке доступных планов.</span><span class="sxs-lookup"><span data-stu-id="de47f-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="de47f-128">Щелкните название плана, чтобы выбрать новый план.</span><span class="sxs-lookup"><span data-stu-id="de47f-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="de47f-129">Добавьте сайты, чтобы создать представление сетевой настройки организации.</span><span class="sxs-lookup"><span data-stu-id="de47f-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="de47f-130">В зависимости от сети организации вы можете использовать сайты для представления здания, расположения офиса или другого объекта.</span><span class="sxs-lookup"><span data-stu-id="de47f-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="de47f-131">Сайты могут быть подключены через сетевую сеть, чтобы разрешить общий доступ к Интернету и(или) подключениям по STN.</span><span class="sxs-lookup"><span data-stu-id="de47f-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="de47f-132">Для лучших результатов создавайте сайты с локальными подключениями, прежде чем создавать сайты, которые будут удаленно подключаться к Интернету или через STN.</span><span class="sxs-lookup"><span data-stu-id="de47f-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="de47f-133">Чтобы создать сайт:</span><span class="sxs-lookup"><span data-stu-id="de47f-133">To create a site:</span></span>

    1. <span data-ttu-id="de47f-134">Добавьте имя и описание сайта.</span><span class="sxs-lookup"><span data-stu-id="de47f-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="de47f-135">В **области Параметры сети** добавьте количество пользователей сети на этом сайте (обязательно).</span><span class="sxs-lookup"><span data-stu-id="de47f-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="de47f-136">Добавьте сведения о сети: пропускная способность по сети, пропускная способность по сети WAN, доступ к Интернету **(локальный** или удаленный) и регрессия через ДНР (нет, локальный или удаленный).</span><span class="sxs-lookup"><span data-stu-id="de47f-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="de47f-137">Для получения определенных рекомендаций по пропускной способности при создание отчета необходимо добавить номера пропускной способности сети WAN и Интернета.</span><span class="sxs-lookup"><span data-stu-id="de47f-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="de47f-138">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="de47f-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="de47f-139">Создание отчета</span><span class="sxs-lookup"><span data-stu-id="de47f-139">Create a report</span></span>

<span data-ttu-id="de47f-140">После добавления всех сайтов вы можете создать отчет следующим образом:</span><span class="sxs-lookup"><span data-stu-id="de47f-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="de47f-141">На **вкладке Отчеты** нажмите **кнопку Начать отчет**.</span><span class="sxs-lookup"><span data-stu-id="de47f-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="de47f-142">Для каждого создаемого сайта распределяйте по всем доступным пользователям число пользователей.</span><span class="sxs-lookup"><span data-stu-id="de47f-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="de47f-143">Если вы используете рекомендуемые корпорацией Майкрософт люди, они будут распределяться автоматически (80 % сотрудников и 20 % удаленных сотрудников).</span><span class="sxs-lookup"><span data-stu-id="de47f-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="de47f-144">После завершения распространения нажмите кнопку **Создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="de47f-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="de47f-145">В сгенерированном отчете будут демонстрироваться требования к пропускной способности в нескольких различных представлениях, что позволит четко понять выходные данные.</span><span class="sxs-lookup"><span data-stu-id="de47f-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="de47f-146">В таблице с отдельными вычислениями будут отображаться требования к пропускной способности для каждого разрешенного действия.</span><span class="sxs-lookup"><span data-stu-id="de47f-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="de47f-147">В дополнительном представлении будут демонстрироваться общие потребности в пропускной способности с рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="de47f-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="de47f-148">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="de47f-148">Click **Save**.</span></span> <span data-ttu-id="de47f-149">Отчет будет доступен в списке отчетов для просмотра в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="de47f-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="de47f-150">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="de47f-150">Example scenario</span></span>

<span data-ttu-id="de47f-151">Чтобы получить пример использования планировщика сети для создания сетевого плана и создания отчета с помощью этих действий, скачайте набор сетевых планировщиков How-To PowerPoint [(только на английском](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) языке).</span><span class="sxs-lookup"><span data-stu-id="de47f-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
