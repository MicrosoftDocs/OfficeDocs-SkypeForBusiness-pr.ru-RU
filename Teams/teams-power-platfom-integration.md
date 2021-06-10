---
title: Teams интеграции с Microsoft Power Platform
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
description: Узнайте, Teams интеграцию с инструментами Microsoft Power Platform, включая Power BI, power apps, Power Automate и Power Virtual Agents.
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111045"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="f1048-103">Teams интеграции с Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="f1048-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="f1048-104">Платформа Microsoft Power Platform помогает пользователям ускорить разработку с помощью средств с низким кодом для анализа данных с помощью **Power BI,** создания пользовательских приложений с помощью **Power Apps,** автоматизации процессов с помощью **Power Automate** и создания интеллектуальных ботов с помощью **Power Virtual Agents** быстрее, чем когда-либо.</span><span class="sxs-lookup"><span data-stu-id="f1048-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="f1048-105">Переход к удаленной и гибридной работе Microsoft Teams позволяет людям по всему миру создавать, совместно работать и общаться.</span><span class="sxs-lookup"><span data-stu-id="f1048-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="f1048-106">Более 75 миллионов активных пользователей в день Teams, как они работают.</span><span class="sxs-lookup"><span data-stu-id="f1048-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Изображение, на Teams и Microsoft Power Platform":::

<span data-ttu-id="f1048-108">Microsoft Power Platform предоставляет множество возможностей интеграции с Teams, где можно вставлять отчеты **Power BI** в рабочей области Teams, вставлять приложения, созданные с помощью **Power Apps** в качестве вкладки или личного приложения, запускать поток **Power Automate** сообщений или использовать адаптивные карточки, а также добавлять боты, созданные с помощью **Power Virtual Agents,** в Teams для взаимодействия с другими сотрудниками организации.</span><span class="sxs-lookup"><span data-stu-id="f1048-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="f1048-109">С сентября 2020 г. улучшена интеграция с Microsoft Power Platform, благодаря которой пользователи могут делать следующее, не выходя из *Teams интерфейса:*</span><span class="sxs-lookup"><span data-stu-id="f1048-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="f1048-110">Создавайте панели мониторинга, отчеты и приложения и делитесь ими с помощью Power BI **принимать** решения на основе данных.</span><span class="sxs-lookup"><span data-stu-id="f1048-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="f1048-111">Создавайте и делитесь приложениями с низким кодом, встроенными с помощью встроенной студии **Power Apps,** подключаясь к бизнес-данным, которые хранятся в новой платформе данных (Microsoft Dataverse для Teams), Microsoft 365 или в других источниках данных через соединители.</span><span class="sxs-lookup"><span data-stu-id="f1048-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="f1048-112">Создавайте автоматизированные рабочие процессы между приложениями и службами для синхронизации файлов, получения уведомлений, сбора данных и многого **Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="f1048-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="f1048-113">Создавайте боты с помощью графического интерфейса без кода с помощью **Power Virtual Agents,** чтобы легко создавать цифровых помощников в Teams и сделать их доступными для общения с коллегами.</span><span class="sxs-lookup"><span data-stu-id="f1048-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="f1048-114">Новые возможности для создания приложений, ботов и рабочих процессов обеспечиваются новой встроенной платформой данных с низким кодом для Teams Dataverse для [Teams,](/powerapps/teams/overview-data-platform)которая обеспечивает хранение реляционных данных, типы данных с насыщенными данными, управление корпоративным классом и развертывание решений одним щелчком мыши.</span><span class="sxs-lookup"><span data-stu-id="f1048-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="f1048-115">Надстройка Dataverse для Teams, созданная на основе [microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="f1048-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="f1048-116">С помощью функции Dataverse для Teams пользователи Teams могут находить и устанавливать пользовательские готовые решения из Teams приложений, демонстрирующих распространенные сценарии в различных отраслях.</span><span class="sxs-lookup"><span data-stu-id="f1048-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="f1048-117">Вы можете настроить и расширить эти пользовательские решения в зависимости от фирменой маркы и требований вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f1048-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="f1048-118">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="f1048-118">Licensing</span></span>

<span data-ttu-id="f1048-119">Новые возможности доступны для выбранных Microsoft 365 подписки.</span><span class="sxs-lookup"><span data-stu-id="f1048-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="f1048-120">Дополнительные сведения о лицензионных требованиях для Power Apps, Power Automate, Power Virtual Agents и Dataverse для Teams см. в [лицензировании.](/power-platform/admin/about-teams-environment)</span><span class="sxs-lookup"><span data-stu-id="f1048-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="f1048-121">Дополнительные сведения о лицензионных требованиях для Power BI см. в [требованиях.](/power-bi/collaborate-share/service-collaborate-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="f1048-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="f1048-122">Как начать работу?</span><span class="sxs-lookup"><span data-stu-id="f1048-122">How do I get started?</span></span>

- [<span data-ttu-id="f1048-123">Power BI и Teams</span><span class="sxs-lookup"><span data-stu-id="f1048-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="f1048-124">Power Apps и Teams</span><span class="sxs-lookup"><span data-stu-id="f1048-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="f1048-125">Power Automate и Teams</span><span class="sxs-lookup"><span data-stu-id="f1048-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="f1048-126">Power Virtual Agents и Teams</span><span class="sxs-lookup"><span data-stu-id="f1048-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)