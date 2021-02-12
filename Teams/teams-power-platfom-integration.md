---
title: Интеграция Teams с Microsoft Power Platform
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Узнайте об интеграции Teams со средствами платформы Microsoft Power Platform, включая Power BI, приложения Power Apps, Power Automate и виртуальные агенты Power.
ms.openlocfilehash: 0fb05596fb5fa87ab4e209325cc35b7a3eae56d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804569"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="07468-103">Интеграция Teams с Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="07468-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="07468-104">Платформа Microsoft Power Platform помогает пользователям ускорить разработку с помощью средств с низким кодом для анализа данных с помощью **Power BI,** создания пользовательских приложений с помощью **Power Apps,** автоматизации процессов с помощью **Power Automate** и создания интеллектуальных ботов с помощью виртуальных агентов **Power,** как никогда.</span><span class="sxs-lookup"><span data-stu-id="07468-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="07468-105">Благодаря переходу на удаленную и гибридную работу Microsoft Teams позволяет людям по всему миру создавать, совместно работать и общаться.</span><span class="sxs-lookup"><span data-stu-id="07468-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="07468-106">С более чем 75 миллионами ежедневно активных пользователей Teams — это работа пользователей.</span><span class="sxs-lookup"><span data-stu-id="07468-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Image summarizing Teams and Microsoft Power Platform":::

<span data-ttu-id="07468-108">Платформа Microsoft Power Platform предоставляет множество возможностей интеграции с Teams, где можно вставлять отчеты Power BI в рабочее пространство **Teams,** внедрение приложений, созданных с помощью **Power Apps** в качестве вкладки или личного приложения, запускать power **Automate** из любого сообщения или использовать адаптивные карточки, а также добавлять бот, созданный с помощью виртуальных агентов **Power,** в Teams для других участников организации для взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="07468-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="07468-109">Начиная с сентября 2020 г. улучшена интеграция с Microsoft Power Platform, благодаря которой пользователи могут:</span><span class="sxs-lookup"><span data-stu-id="07468-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="07468-110">Создание панелей мониторинга, отчетов и приложений с помощью **Power BI** и их совместное использование для принятия решений на основе данных.</span><span class="sxs-lookup"><span data-stu-id="07468-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="07468-111">Создавайте приложения с низким кодом и делитесь ими с помощью встроенной студии **Power Apps,** подключаясь к бизнес-данным, которые хранятся в новой платформе данных (Microsoft Dataverse для Teams), Microsoft 365 или в других источниках данных через соединители.</span><span class="sxs-lookup"><span data-stu-id="07468-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="07468-112">Создавайте автоматизированные рабочие процессы между приложениями и службами, чтобы синхронизировать файлы, получать уведомления, собирать данные и делать много другое с помощью **Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="07468-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="07468-113">Создавайте боты с помощью наглядного графического интерфейса без кода с помощью виртуальных агентов **Power,** чтобы легко создавать цифровых помощников в Teams и делать их доступными для общения с коллегами.</span><span class="sxs-lookup"><span data-stu-id="07468-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="07468-114">Новые возможности для создания приложений, ботов и рабочих процессов обеспечиваются благодаря новой встроенной платформе данных с низким кодом для Teams, [dataverse для Teams,](https://go.microsoft.com/fwlink/?linkid=2143541)которая обеспечивает реляционное хранение данных, насыщенные типы данных, управление корпоративным классом и развертывание решений одним щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="07468-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="07468-115">Dataverse for Teams is built on top of [Microsoft Dataverse.](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="07468-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="07468-116">С помощью dataverse для Teams пользователи Teams могут находить и устанавливать пользовательские готовые к использованию решения из магазина приложений Teams, демонстрируемые распространенные сценарии в различных отраслях.</span><span class="sxs-lookup"><span data-stu-id="07468-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="07468-117">Вы можете настраивать и расширять эти пользовательские решения в зависимости от фирменой маркы и требований вашей организации.</span><span class="sxs-lookup"><span data-stu-id="07468-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="07468-118">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="07468-118">Licensing</span></span>

<span data-ttu-id="07468-119">Новые возможности доступны для выбранных подписок Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07468-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="07468-120">Дополнительные сведения о требованиях к лицензированию для Power Apps, Power Automate, виртуальных агентов Power и Dataverse для Teams см. в [лицензиях.](https://go.microsoft.com/fwlink/?linkid=2143647)</span><span class="sxs-lookup"><span data-stu-id="07468-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="07468-121">Дополнительные сведения о требованиях к лицензированию Для Power BI см. [в требованиях.](https://go.microsoft.com/fwlink/?linkid=2143490)</span><span class="sxs-lookup"><span data-stu-id="07468-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="07468-122">Как начать работу?</span><span class="sxs-lookup"><span data-stu-id="07468-122">How do I get started?</span></span>

- [<span data-ttu-id="07468-123">Power BI и Teams</span><span class="sxs-lookup"><span data-stu-id="07468-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="07468-124">Power Apps и Teams</span><span class="sxs-lookup"><span data-stu-id="07468-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="07468-125">Power Automate и Teams</span><span class="sxs-lookup"><span data-stu-id="07468-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="07468-126">Виртуальные агенты и Команды Power</span><span class="sxs-lookup"><span data-stu-id="07468-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
