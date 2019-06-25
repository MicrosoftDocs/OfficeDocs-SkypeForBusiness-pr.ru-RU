---
title: Использование планировщика сети для Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
description: Узнайте, как использовать планировщик сети для определения требований к сети для Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aaf2c2c7242c594d67af131d3a15224ddf16419c
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2019
ms.locfileid: "35214825"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="3fb7a-103">Использование планировщика сети для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3fb7a-103">Use the Network Planner for Microsoft Teams</span></span>

<span data-ttu-id="3fb7a-104">Добро пожаловать в планировщик сети.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-104">Welcome to the Network Planner.</span></span> <span data-ttu-id="3fb7a-105">В некоторых случаях планировщик сети поможет вам определить и упорядочить сетевые требования для подключения пользователей Microsoft Teams в Организации.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-105">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="3fb7a-106">Когда вы предоставляете сведения о сети и использование Teams, планировщик сети вычисляет требования к сети для развертывания Teams и облачного голоса по физическим адресам Организации.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-106">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization’s physical locations.</span></span>

![Снимок экрана: планировщик сети](media/network-planner.png)

<span data-ttu-id="3fb7a-108">С помощью планировщика сети вы можете выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fb7a-108">Network Planner allows you to:</span></span>

- <span data-ttu-id="3fb7a-109">Создавайте представления своей организации с помощью сайтов и рекомендуемых Майкрософт пользователей (работников Office, удаленных работников и системы комнаты для Teams).</span><span class="sxs-lookup"><span data-stu-id="3fb7a-109">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3fb7a-110">Рекомендованные персонажи были разработаны на основе данных из рабочих групп, наиболее подходящих для использования, и типичных шаблонов использования.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-110">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="3fb7a-111">Однако вы можете создать до трех специальных персонажей в дополнение к трем рекомендованным персонажам.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-111">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="3fb7a-112">Создание отчетов и вычисление требований к пропускной способности для использования в Teams.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-112">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="3fb7a-113">Создание собственного персонажа</span><span class="sxs-lookup"><span data-stu-id="3fb7a-113">Create a custom persona</span></span>

<span data-ttu-id="3fb7a-114">Для создания собственного персонажа выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fb7a-114">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="3fb7a-115">Перейдите в планировщик сетей в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-115">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="3fb7a-116">На вкладке **персонажи** щелкните значок **+ Настраиваемый персонаж**.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-116">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="3fb7a-117">В области **Новая настройка пользователя** добавьте имя и описание нового персонажа.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-117">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="3fb7a-118">Выберите разрешения, которые пользователь может использовать в Организации.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-118">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="3fb7a-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-119">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="3fb7a-120">Создание плана</span><span class="sxs-lookup"><span data-stu-id="3fb7a-120">Build your plan</span></span>

<span data-ttu-id="3fb7a-121">Чтобы приступить к созданию плана сети, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-121">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="3fb7a-122">Перейдите в планировщик сетей в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-122">Go to the Network Planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="3fb7a-123">На вкладке **Сетевая схема** нажмите кнопку **Добавить сетевой план**.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-123">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="3fb7a-124">Введите имя и описание сетевого плана.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-124">Enter a name and description for your network plan.</span></span> <span data-ttu-id="3fb7a-125">В списке доступных планов появится план сети.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-125">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="3fb7a-126">Щелкните имя плана, чтобы выбрать новый план.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-126">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="3fb7a-127">Добавьте сайты, чтобы создать представление настройки сети вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-127">Add sites to create a representation of your organization’s network setup.</span></span>

    <span data-ttu-id="3fb7a-128">В зависимости от сети организации вы можете использовать сайты для представления здания, местоположения офиса или чего-то еще.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-128">Depending on your organization’s network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="3fb7a-129">Сайты могут быть соединены через глобальную сеть, чтобы предоставить общий доступ к Интернету и/или PSTN-подключениям.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-129">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="3fb7a-130">Для достижения наилучших результатов Создавайте сайты с локальными подключениями, прежде чем создавать сайты, которые подключаются к Интернету или КТСОП.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-130">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="3fb7a-131">Чтобы создать сайт, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-131">To create a site:</span></span>

    1. <span data-ttu-id="3fb7a-132">Добавьте имя и описание сайта.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-132">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="3fb7a-133">В разделе **Параметры сети**введите количество пользователей сети на сайте (обязательно).</span><span class="sxs-lookup"><span data-stu-id="3fb7a-133">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="3fb7a-134">Дополнительные сведения о сети: поддержка глобальных сетей, емкость глобальной сети, выход из\*\*\*\* Интернета (локальная или **Удаленная**) и коммутируемая сеть (нет, локальный или удаленный).</span><span class="sxs-lookup"><span data-stu-id="3fb7a-134">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="3fb7a-135">При создании отчета необходимо добавить номера, связанные с пропускной способностью, в глобальной сети и в Интернет-ресурсе.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-135">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="3fb7a-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-136">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="3fb7a-137">Создание отчета</span><span class="sxs-lookup"><span data-stu-id="3fb7a-137">Create a report</span></span>

<span data-ttu-id="3fb7a-138">После добавления всех сайтов вы можете создать отчет, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-138">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="3fb7a-139">На вкладке " **отчеты** " нажмите кнопку " **начать отчет**".</span><span class="sxs-lookup"><span data-stu-id="3fb7a-139">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="3fb7a-140">Для каждого сайта, который вы создаете, распределите количество пользователей по всем доступным персонажам.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-140">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="3fb7a-141">Если вы используете Microsoft рекомендованных пользователей, номер будет распространяться автоматически (80% работников Office и 20%-е исполнителя).</span><span class="sxs-lookup"><span data-stu-id="3fb7a-141">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="3fb7a-142">После того как вы завершите распространение, нажмите **создать отчет**.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-142">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="3fb7a-143">Созданный отчет будет показывать требования к пропускной способности в нескольких различных представлениях, чтобы вы могли ясно понять результат:</span><span class="sxs-lookup"><span data-stu-id="3fb7a-143">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="3fb7a-144">В таблице с отдельными вычислениями для каждой разрешенной деятельности будут отображаться требования к пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-144">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="3fb7a-145">Дополнительное представление показывает общую пропускную способность, необходимую для рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-145">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="3fb7a-146">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-146">Click **Save**.</span></span> <span data-ttu-id="3fb7a-147">Отчет будет доступен в списке "отчеты" для последующего просмотра.</span><span class="sxs-lookup"><span data-stu-id="3fb7a-147">Your report will be available on the reports list for later viewing.</span></span>
