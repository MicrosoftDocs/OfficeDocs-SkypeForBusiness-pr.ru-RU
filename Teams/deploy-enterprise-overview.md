---
title: Обзор развертывания корпоративного выпуска Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Узнайте о том, как развернуть корпоративные возможности Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b751ccebfd553f59b6144ea6b6f28db515e9c1d
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395459"
---
# <a name="teams-enterprise-deployment-overview"></a><span data-ttu-id="3bb93-103">Обзор развертывания корпоративного выпуска Teams</span><span class="sxs-lookup"><span data-stu-id="3bb93-103">Teams enterprise deployment overview</span></span>

<span data-ttu-id="3bb93-104">Если вы представитель среднего или крупного бизнеса, вам приходится заботиться о том, как запустить для пользователей новую службу, как развернуть для них клиент Microsoft Teams, как ваша сеть может затронуть качество общения в реальном времени и так далее.</span><span class="sxs-lookup"><span data-stu-id="3bb93-104">If you're a medium or large business, you need to think about how you're going to roll out the service to your users, how you're going to deploy the Microsoft Teams client to them, how your network design could impact the quality of real-time communication, and so on.</span></span> <span data-ttu-id="3bb93-105">Ознакомьтесь со следующими сегментами и прочитайте советы о том, как спланировать внедрение Teams в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3bb93-105">Check out the following sections for pointers to articles that'll help you plan for Teams in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="3bb93-106">Если вы еще не сделали этого, настоятельно рекомендуем начать развертывание Teams с пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="3bb93-106">If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot.</span></span> <span data-ttu-id="3bb93-107">Пилотный проект позволит вам и нескольким первым пользователям ознакомиться с приложением Teams и его функциями до планирования и конечного развертывания. Дополнительные сведения о запуске пилотного проекта см. в статье [Начало работы с Microsoft Teams](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="3bb93-107">A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).</span></span>

<span data-ttu-id="3bb93-108">Прочитав разделы ниже, вы будете готовы начать развертывание Teams в вашей организации. См. статью [Настройка Microsoft Teams в организации](deploy-enterprise-setup.md).</span><span class="sxs-lookup"><span data-stu-id="3bb93-108">After you've read the sections below and are ready to start deploying Teams in your organization, see [Set up Microsoft Teams in your enterprise](deploy-enterprise-setup.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="3bb93-109">Архитектура</span><span class="sxs-lookup"><span data-stu-id="3bb93-109">Architecture</span></span>

<span data-ttu-id="3bb93-110">Teams тесно интегрирован с Microsoft 365 и использует множество функций для работы чата, собраний, телефонии, потоковой передачи видео и многого другого.</span><span class="sxs-lookup"><span data-stu-id="3bb93-110">Teams is tightly integrated into Microsoft 365 and uses many features to power chat, file sharing, meetings, telephony, video streaming, and more.</span></span> <span data-ttu-id="3bb93-111">Перед развертыванием Teams ознакомьтесь с [плакатами ИТ-архитектуры и решений для телефонии Microsoft Teams](teams-architecture-solutions-posters.md), чтобы лучше узнать, как Teams взаимодействует с остальными компонентами среды Microsoft 365 и создает условия для совместной работы ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="3bb93-111">Before you roll out Teams, check out [Microsoft Teams IT architecture and telephony solutions posters](teams-architecture-solutions-posters.md) to get familiar with how Teams works with the rest of Microsoft 365 to create a complete collaboration experience for your users.</span></span>

## <a name="workloads"></a><span data-ttu-id="3bb93-112">Рабочие нагрузки</span><span class="sxs-lookup"><span data-stu-id="3bb93-112">Workloads</span></span>

<span data-ttu-id="3bb93-113">В Teams предусмотрены три рабочих нагрузки, развертываемые независимо друг от друга: **чат, команды и каналы**; **собрания и конференции**; и **телефонная система и ТСОП (телефонная сеть общего пользования)**.</span><span class="sxs-lookup"><span data-stu-id="3bb93-113">Teams has three workloads that can be deployed independently of each other: **chat, teams, and channels**; **meetings and conferencing**; and **Phone System and PSTN (public switched telephone network) connectivity**.</span></span> <span data-ttu-id="3bb93-114">Каждой рабочей нагрузке посвящен отдельный раздел документации, чтобы вам было легче найти нужную информацию,</span><span class="sxs-lookup"><span data-stu-id="3bb93-114">Each workload has its own section in our documentation to make it easier to find information about that workload.</span></span> <span data-ttu-id="3bb93-115">в том числе сведения о планировании развертывания.</span><span class="sxs-lookup"><span data-stu-id="3bb93-115">This includes deployment planning information.</span></span>

<span data-ttu-id="3bb93-116">Чтобы узнать больше о планировании развертывания для интересующей вас рабочей нагрузки, см. статьи:</span><span class="sxs-lookup"><span data-stu-id="3bb93-116">To see deployment planning information for the workload you want to deploy, see the following articles:</span></span>

- [<span data-ttu-id="3bb93-117">Чат, команды и каналы</span><span class="sxs-lookup"><span data-stu-id="3bb93-117">Chat, teams, and channels</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [<span data-ttu-id="3bb93-118">Собрания и конференции</span><span class="sxs-lookup"><span data-stu-id="3bb93-118">Meetings and conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="3bb93-119">Телефонная система и связь с ТСОП</span><span class="sxs-lookup"><span data-stu-id="3bb93-119">Phone System and PSTN connectivity</span></span>](cloud-voice-landing-page.md)

## <a name="network-planner"></a><span data-ttu-id="3bb93-120">Планировщик сети</span><span class="sxs-lookup"><span data-stu-id="3bb93-120">Network planner</span></span>

<span data-ttu-id="3bb93-121">Планировщик сети для Teams — это чрезвычайно важный компонент, если у вас много пользователей, комплексные сети или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="3bb93-121">Network planning for Teams is extremely important when you have large numbers of users, complex networks, or both.</span></span> <span data-ttu-id="3bb93-122">Teams поддерживает голосовую связь и видеоконференции. Для оптимальной работы обе функции полагаются на общение в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="3bb93-122">Teams supports voice calling and video conferencing, both of which rely on real-time communications to provide the best experience possible for users.</span></span> <span data-ttu-id="3bb93-123">Сеть должна обладать следующими качествами:</span><span class="sxs-lookup"><span data-stu-id="3bb93-123">Networks must:</span></span>

- <span data-ttu-id="3bb93-124">Достаточная пропускная способность, чтобы обеспечить работу множества одновременных голосовых вызовов, видеоконференций, собраний, демонстраций экранов и так далее.</span><span class="sxs-lookup"><span data-stu-id="3bb93-124">Have sufficient bandwidth capacity to accommodate the number of concurrent voice calls, video conferences, meetings, screen sharing, and so on.</span></span>
- <span data-ttu-id="3bb93-125">Сетевое оборудование с поддержкой протоколов связи в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="3bb93-125">Have network hardware that supports real-time communication protocols.</span></span>
- <span data-ttu-id="3bb93-126">Возможность подключения нужных сетевых портов к устройствам в сети, службам Microsoft 365 и внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="3bb93-126">Allow the required network ports between devices on your networks, Microsoft 365 services, and external users.</span></span>

<span data-ttu-id="3bb93-127">Чтобы лучше понять требования Teams к сети, см. следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="3bb93-127">See the following articles to help you understand Teams network requirements:</span></span>

- [<span data-ttu-id="3bb93-128">Подготовка сети организации к использованию Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3bb93-128">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)
- [<span data-ttu-id="3bb93-129">Прокси-серверы для Teams или Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3bb93-129">Proxy servers for Teams or Skype for Business Online</span></span>](proxy-servers-for-skype-for-business-online.md)

<span data-ttu-id="3bb93-130">Чтобы помочь вам с планированием, Teams содержит планировщик сети.</span><span class="sxs-lookup"><span data-stu-id="3bb93-130">To help you with your planning, Teams includes the Network planner.</span></span> <span data-ttu-id="3bb93-131">Планировщик сети задает вопросы о количестве и типах ваших пользователей, числе сайтов организации, пропускной способности сети и прочих данных.</span><span class="sxs-lookup"><span data-stu-id="3bb93-131">The Network planner asks you questions about the number and types of users you have, how many sites your organization has, the bandwidth capacity of your network links, and more.</span></span> <span data-ttu-id="3bb93-132">На основании этих сведений планировщик сети создает отчет, содержащий требования и рекомендации к пропускной способности по каждому действию.</span><span class="sxs-lookup"><span data-stu-id="3bb93-132">Using this information, the Network planner creates a report that shows the bandwidth requirements for each activity, along with the recommendations.</span></span>

 > [!div class="nextstepaction"]
> [<span data-ttu-id="3bb93-133">Перейти к планировщику сети</span><span class="sxs-lookup"><span data-stu-id="3bb93-133">Go to Network planner</span></span>](https://admin.teams.microsoft.com/networkplanner/organization)

<span data-ttu-id="3bb93-134">(Чтобы открыть планировщик сети, вы должны быть [глобальным администратором Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles).)</span><span class="sxs-lookup"><span data-stu-id="3bb93-134">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Network planner.)</span></span>

<span data-ttu-id="3bb93-135">Чтобы узнать больше о работе планировщика сети, см. статью [Использование планировщика сети для Microsoft Teams](network-planner.md).</span><span class="sxs-lookup"><span data-stu-id="3bb93-135">For details about how the Network planner works, see [Use the Network planner for Microsoft Teams](network-planner.md).</span></span>

<span data-ttu-id="3bb93-136">Чтобы ознакомиться с примером работы планировщика сети, см. [Использование планировщика сети — пример сценария](tutorial-network-planner-example.yml).</span><span class="sxs-lookup"><span data-stu-id="3bb93-136">To see an example of how Network planner can plan your network, see [Using Network Planner - example scenario](tutorial-network-planner-example.yml).</span></span>

## <a name="teams-advisor"></a><span data-ttu-id="3bb93-137">Помощник для Teams</span><span class="sxs-lookup"><span data-stu-id="3bb93-137">Teams advisor</span></span>

<span data-ttu-id="3bb93-138">Помощник для Teams — это решение Teams, которое помогает объединить команды, каналы, общий доступ к файлам и планировщик для создания проекта развертывания в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3bb93-138">The Teams advisor is a solution within Teams that brings together teams, channels, file sharing, and Planner, to create a deployment project for your organization.</span></span> <span data-ttu-id="3bb93-139">Помощник для Teams создает план проекта для выбранной рабочей нагрузки (например, чат, команды и каналы), содержащий рекомендуемые задачи, которые необходимо выполнить во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="3bb93-139">Teams advisor creates project plan, specific to the workload you select (such as chat, teams, and channels), that includes the recommended tasks you should perform during your deployment.</span></span> <span data-ttu-id="3bb93-140">В каждой задаче предусмотрен набор инструкций, предложений и ссылок на соответствующие статьи, чтобы помочь вам в ходе развертывания.</span><span class="sxs-lookup"><span data-stu-id="3bb93-140">Each task contains instructions, suggestions, and links to relevant articles, to guide you through the process.</span></span> <span data-ttu-id="3bb93-141">Задачи можно назначить другим лицам с указанием сроков начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="3bb93-141">You can easily assign tasks to one or more individuals, and specify start and end dates for each task.</span></span>

> [!TIP]
> <span data-ttu-id="3bb93-142">Узнайте, как воспользоваться помощником для Teams и спланировать развертывание Teams, завершив модуль [Развертывание с помощником для Teams](https://docs.microsoft.com/learn/modules/m365-teams-rollout-using-advisor/) в Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="3bb93-142">See how you can use Teams advisor to help you plan your Teams deployment by completing the [Roll out using the Teams advisor](https://docs.microsoft.com/learn/modules/m365-teams-rollout-using-advisor/) module on Microsoft Learn.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3bb93-143">Перейти к помощнику для Teams</span><span class="sxs-lookup"><span data-stu-id="3bb93-143">Go to Teams advisor</span></span>](https://admin.teams.microsoft.com/teams-deployment)

<span data-ttu-id="3bb93-144">(Чтобы открыть помощник для Teams, вы должны быть [глобальным администратором Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles).)</span><span class="sxs-lookup"><span data-stu-id="3bb93-144">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Teams advisor.)</span></span>

<span data-ttu-id="3bb93-145">Подробные сведения о работе помощника для Teams см. в статье [Использование помощника для Teams для развертывания Microsoft Teams](use-advisor-teams-roll-out.md).</span><span class="sxs-lookup"><span data-stu-id="3bb93-145">For details about how the Teams advisor works, see [Use Advisor for Teams to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>

## <a name="lifecycle-and-governance-planning"></a><span data-ttu-id="3bb93-146">Планирование жизненного цикла и управления</span><span class="sxs-lookup"><span data-stu-id="3bb93-146">Lifecycle and governance planning</span></span>

<span data-ttu-id="3bb93-147">При планировании развертывания Teams необходимо учитывать жизненный цикл команд, каналов, файлов и прочего в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3bb93-147">As you plan your Teams deployment, you need to consider the lifecycle of teams, channels, files, and so on, in your organization.</span></span> <span data-ttu-id="3bb93-148">Также следует помнить о том, какие типы информации будут в них храниться.</span><span class="sxs-lookup"><span data-stu-id="3bb93-148">You should also think about what types of information will be stored in them.</span></span> <span data-ttu-id="3bb93-149">Команды можно создавать для отдельных проектов, подразделения или в качестве центрального ресурса для всей организации.</span><span class="sxs-lookup"><span data-stu-id="3bb93-149">Teams may be created for a specific project, for a department, or they might be used as a central resource for the entire organization.</span></span> <span data-ttu-id="3bb93-150">У каждого варианта использования есть свои требования, поэтому вам необходимо ответить на несколько вопросов:</span><span class="sxs-lookup"><span data-stu-id="3bb93-150">Each of these uses have different requirements, which drive questions like the following:</span></span>

- <span data-ttu-id="3bb93-151">Как долго команды будут оставаться активными?</span><span class="sxs-lookup"><span data-stu-id="3bb93-151">How long will the teams remain active?</span></span>
- <span data-ttu-id="3bb93-152">Кто должен руководить командами и распоряжаться их каналами?</span><span class="sxs-lookup"><span data-stu-id="3bb93-152">Who should own and manage the teams and their channels?</span></span>
- <span data-ttu-id="3bb93-153">Следует ли вводить особые требования для отдельных команд?</span><span class="sxs-lookup"><span data-stu-id="3bb93-153">Should certain compliance requirements apply to some teams, but not others?</span></span>
- <span data-ttu-id="3bb93-154">Нужно ли внедрять правила в отношении имен, чтобы пользователям было легче отыскать нужную команду?</span><span class="sxs-lookup"><span data-stu-id="3bb93-154">Should there be a naming policy to help users identify the right team?</span></span>

<span data-ttu-id="3bb93-155">Создание правил и руководств на начальном этапе развертывания поможет удостовериться, что пользователи смогут найти нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="3bb93-155">Creating policies and guidelines as part of your initial deployment will help ensure that your users can find the information they need.</span></span> <span data-ttu-id="3bb93-156">Не менее важно и то, что соответствующие политики помогут вашей организации предотвратить утечки информации, обеспечить соответствие нормативным требованиям и сохранять информацию в архивных целях.</span><span class="sxs-lookup"><span data-stu-id="3bb93-156">Just as importantly, however, appropriate policies will help protect your organization from information leakage, help you conform to regulatory requirements, and help you retain information as needed for archival purposes.</span></span>

<span data-ttu-id="3bb93-157">Чтобы узнать больше об управлении жизненным циклом и руководстве в Teams, см. статьи:</span><span class="sxs-lookup"><span data-stu-id="3bb93-157">To learn more about lifecycle management and governance in Teams, see the following:</span></span>

- [<span data-ttu-id="3bb93-158">Планирование управления жизненным циклом в Teams</span><span class="sxs-lookup"><span data-stu-id="3bb93-158">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
- [<span data-ttu-id="3bb93-159">Планирование управления в Teams</span><span class="sxs-lookup"><span data-stu-id="3bb93-159">Plan for governance in Teams</span></span>](plan-teams-governance.md)

## <a name="adoption"></a><span data-ttu-id="3bb93-160">Внедрение</span><span class="sxs-lookup"><span data-stu-id="3bb93-160">Adoption</span></span>

<span data-ttu-id="3bb93-161">Чтобы ваша организация и пользователи смогли получить от Teams наибольшую пользу, вам понадобится программа внедрения.</span><span class="sxs-lookup"><span data-stu-id="3bb93-161">To ensure that your organization and your users get the most out of Teams, you need an adoption program.</span></span> <span data-ttu-id="3bb93-162">Эффективная программа внедрения поможет привлечь первых пользователей, которые смогут:</span><span class="sxs-lookup"><span data-stu-id="3bb93-162">An effective adoption program can mobilize early adopters who can:</span></span>

- <span data-ttu-id="3bb93-163">Рассказать о преимуществах Teams коллегам и руководителям групп и компании.</span><span class="sxs-lookup"><span data-stu-id="3bb93-163">Articulate the benefits of Teams to their colleagues and to business or group leaders.</span></span>
- <span data-ttu-id="3bb93-164">Поделиться радостью от использования Teams для совместной работы и удобного общения.</span><span class="sxs-lookup"><span data-stu-id="3bb93-164">Spark excitement in others who see how Teams improves collaboration and makes it easier to connect with each other.</span></span>
- <span data-ttu-id="3bb93-165">Оценить имеющиеся деловые процессы и дать рекомендации о том, как лучше всего внедрить в них Teams.</span><span class="sxs-lookup"><span data-stu-id="3bb93-165">Help evaluate existing business processes and make recommendations for how Teams can be integrated into them.</span></span>
- <span data-ttu-id="3bb93-166">Сообщать команде разработки об успехах и трудностях в работе и ускорить внедрение.</span><span class="sxs-lookup"><span data-stu-id="3bb93-166">Report back to the deployment team both successes and difficulties to help improve the adoption process.</span></span>

<span data-ttu-id="3bb93-167">Чтобы узнать больше о программе внедрения, см. [Внедрение Microsoft Teams](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="3bb93-167">For details about setting up an adoption program, see [Adopt Microsoft Teams](adopt-microsoft-teams-landing-page.md).</span></span>