## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="0a11b-101">Модели интеграции для поставщиков решений</span><span class="sxs-lookup"><span data-stu-id="0a11b-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="0a11b-102">В качестве поставщика решений Центра контактов можно выбрать три модели для интеграции подключенного решения центра контактов с Teams:</span><span class="sxs-lookup"><span data-stu-id="0a11b-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="0a11b-103">Если вы хотите использовать сертифицированные SBCs и прямую маршрутику для подключения решения центра контактов к Teams, см. модель [подключения.](?tabs=connect#steps)</span><span class="sxs-lookup"><span data-stu-id="0a11b-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="0a11b-104">Если вы хотите использовать боты Azure и API связи Microsoft Graph, чтобы поставщики решений могли создавать приложения Teams, см. модель [расширения](?tabs=extend#steps).</span><span class="sxs-lookup"><span data-stu-id="0a11b-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="0a11b-105">Если вы хотите использовать SDK, который позволяет поставщикам решений использовать собственные возможности Teams в своих приложениях, см. модель [Power.](?tabs=power#steps)</span><span class="sxs-lookup"><span data-stu-id="0a11b-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="0a11b-106">Power solutions станет доступен, когда SDK станет доступен в конце 2021 г.</span><span class="sxs-lookup"><span data-stu-id="0a11b-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="0a11b-107">**Модель подключения**</span><span class="sxs-lookup"><span data-stu-id="0a11b-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="0a11b-108">Модель Connect использует сертифицированные SBCs Майкрософт и прямую маршрутику для подключения решений центра контактов к инфраструктуре телефонной системы Teams, позволяя улучшить маршрутику, конфигурацию и аналитику системы.</span><span class="sxs-lookup"><span data-stu-id="0a11b-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="0a11b-109">Агенты могут настроить автоматические виртуальные помощники и очереди маршрутизировать на основе навыков, чтобы собирать информацию и связывать клиентов с экспертами в предметных вопросах.</span><span class="sxs-lookup"><span data-stu-id="0a11b-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="0a11b-110">**Основные моменты функций:**</span><span class="sxs-lookup"><span data-stu-id="0a11b-110">**Feature highlights:**</span></span>

<span data-ttu-id="0a11b-111">Эти функции не являются исчерпывающим списком возможностей этой модели интеграции, но в число областей, в которых она включена, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="0a11b-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="0a11b-112">Office 365 authN для агентов для подключения к клиенту Майкрософт из интегрированного клиента CCaaS</span><span class="sxs-lookup"><span data-stu-id="0a11b-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="0a11b-113">Узнайте, когда агенты доступны в Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="0a11b-114">Поддержка по переводам и групповым звонкам в Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="0a11b-115">API Teams Graph и API облачных коммуникаций для интеграции с Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="0a11b-116">Поддержка нескольких клиентов SIP в SBC поставщика решений.</span><span class="sxs-lookup"><span data-stu-id="0a11b-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="0a11b-117">Поставщики решений для использования [ <span class="underline">сертифицированного контроллера границы сеанса (SBC) Майкрософт</span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="0a11b-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="0a11b-118">**Модель "Расширить"**</span><span class="sxs-lookup"><span data-stu-id="0a11b-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="0a11b-119">Модель Extend интегрируется с клиентом Teams с помощью клиентской платформы [Teams](/microsoftteams/platform/overview), [API Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) и API облачной связи в Microsoft [Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="0a11b-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="0a11b-120">Модель "Расширить" также использует телефонную систему Teams для всех звонков в Центре контактов и управления звонками, а поставщик решений центра контактов выступает в качестве оператора телефонии вместе с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a11b-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="0a11b-121">Агенты могут использовать Teams для внутренней совместной работы и внешней связи и использовать динамические контекстные заметки для корреляции данных из нескольких систем до начала взаимодействия и предотвращения переключения контекста с помощью динамических заметок.</span><span class="sxs-lookup"><span data-stu-id="0a11b-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="0a11b-122">Организации могут проектировать рабочий процесс и расширенные конфигурации маршрутов в зависимости от конкретного пользователя и измерять качество своей системы и взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="0a11b-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="0a11b-123">**Основные моменты функций:**</span><span class="sxs-lookup"><span data-stu-id="0a11b-123">**Feature highlights:**</span></span>

<span data-ttu-id="0a11b-124">Эти функции не являются исчерпывающим списком возможностей этой модели интеграции, но в число областей, в которых она включена, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="0a11b-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="0a11b-125">API Teams Graph и API облачных коммуникаций для интеграции с Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="0a11b-126">Приложение teams для работы с агентами</span><span class="sxs-lookup"><span data-stu-id="0a11b-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="0a11b-127">Teams в качестве основной конечной точки для звонков агентов</span><span class="sxs-lookup"><span data-stu-id="0a11b-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="0a11b-128">Вызов клиента Teams для всех элементов управления звонками</span><span class="sxs-lookup"><span data-stu-id="0a11b-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="0a11b-129">Приложение "Опыт работы агента" для веб-клиента Teams и мобильного клиента</span><span class="sxs-lookup"><span data-stu-id="0a11b-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="0a11b-130">Аналитика, управление рабочего процессами, ролевая работа агентов в приложении CCaaS в Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="0a11b-131">Взаимодействие и взаимодействие, интегрированные с клиентами Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="0a11b-132">Сохранение производительности и качества работы клиентов Teams во всех приложениях</span><span class="sxs-lookup"><span data-stu-id="0a11b-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="0a11b-133">**Модель питания**</span><span class="sxs-lookup"><span data-stu-id="0a11b-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="0a11b-134">Модель Power позволяет поставщикам решений создавать голосовые приложения на базе Azure с помощью инфраструктуры звонков Teams и клиентской платформы для предоставления современных интеллектуальных решений для взаимодействия с клиентами и агентами.</span><span class="sxs-lookup"><span data-stu-id="0a11b-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="0a11b-135">Цель модели Power — предоставить одно приложение и одноэкранный центр контактов.</span><span class="sxs-lookup"><span data-stu-id="0a11b-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="0a11b-136">**Основные моменты функций:**</span><span class="sxs-lookup"><span data-stu-id="0a11b-136">**Feature highlights:**</span></span>

<span data-ttu-id="0a11b-137">Эти функции не являются исчерпывающим списком возможностей этой модели интеграции, но в число областей, в которых она включена, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="0a11b-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="0a11b-138">Формальные возможности агентов, которые включены для взаимодействия с каналом через Teams SDK</span><span class="sxs-lookup"><span data-stu-id="0a11b-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="0a11b-139">Использование служб совместной работы Teams для совместной работы агентов и взаимодействия с клиентами</span><span class="sxs-lookup"><span data-stu-id="0a11b-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="0a11b-140">Быстрая подготовка облачных служб и развертывание в любом месте</span><span class="sxs-lookup"><span data-stu-id="0a11b-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="0a11b-141">Прямое управление беседами и взаимодействие с пользователями во время бесед Teams</span><span class="sxs-lookup"><span data-stu-id="0a11b-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="0a11b-142">Модель питания будет доступна в конце 2021 г.</span><span class="sxs-lookup"><span data-stu-id="0a11b-142">The Power model will be available towards the end of 2021.</span></span>
