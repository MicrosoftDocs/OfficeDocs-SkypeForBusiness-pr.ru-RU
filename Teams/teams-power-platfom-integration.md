---
title: Интеграция Teams с Microsoft Power Platform
author: lanachin
ms.author: v-lanac
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
description: Сведения о интеграции Teams с инструментами Microsoft Power Platform, включая агенты Power BI, Power, Powering и Virtual Power.
ms.openlocfilehash: 2dfcf0dffec420e70d8f90c669bb64d2e9236c3e
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204007"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="acaf8-103">Интеграция Teams с Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="acaf8-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="acaf8-104">Платформа Microsoft Power Platform помогает пользователям быстрее разрабатывать программы с помощью специальных средств для анализа данных с использованием **Power BI**, создания пользовательских приложений с помощью **приложений**для опытных пользователей, автоматизации процессов с помощью **Power**Tools и создания интеллектуальных ботов с помощью **виртуальных агентов Powering** более быстро, чем когда-либо.</span><span class="sxs-lookup"><span data-stu-id="acaf8-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="acaf8-105">Благодаря переходу между удаленными и гибридными трудозатратами Microsoft Teams позволили людям по всему миру продолжать создавать, совместно работать и общаться.</span><span class="sxs-lookup"><span data-stu-id="acaf8-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="acaf8-106">Если вы используете более 75 000 000 ежедневных активных пользователей, Teams – это то, как люди работают.</span><span class="sxs-lookup"><span data-stu-id="acaf8-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Общие сведения о графических группах и платформе Microsoft Power Platform":::

<span data-ttu-id="acaf8-108">Платформа Microsoft Power Platform предлагает множество возможностей интеграции с группами, в которых вы можете внедрить отчеты **Power BI** в рабочую область Teams, внедрить приложения, созданные с помощью **приложений Power** , как вкладку или личное приложение, активировать поток **автоматизации** из любого сообщения или использовать адаптивные карты, а также добавить Bot, созданный с помощью **виртуальных агентов** , для взаимодействия с другими участниками Организации.</span><span class="sxs-lookup"><span data-stu-id="acaf8-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="acaf8-109">Начиная с 2020 сентября, интеграция с платформой Microsoft Power Platform улучшилась, позволяя пользователям выполнять указанные ниже действия, *не покидая интерфейс Teams*.</span><span class="sxs-lookup"><span data-stu-id="acaf8-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="acaf8-110">Создавайте и делитесь информационными панелями, отчетами и приложениями с помощью **Power BI** , чтобы принимать решения, управляемые данными.</span><span class="sxs-lookup"><span data-stu-id="acaf8-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="acaf8-111">Создавайте и предоставляйте к ним доступ к самым низким и ориентированным на приложения приложениям с помощью интегрированных **приложений Power Apps** , подключаясь к бизнес-данным, хранящимся в новой базовой платформе данных (Project Oakdale), Microsoft 365 или других источниках данных с помощью соединителей.</span><span class="sxs-lookup"><span data-stu-id="acaf8-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Project Oakdale), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="acaf8-112">Создавайте автоматические рабочие процессы между приложениями и службами, чтобы синхронизировать файлы, получать уведомления, собирать данные и многое другое с помощью **Power автоматизировать**.</span><span class="sxs-lookup"><span data-stu-id="acaf8-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="acaf8-113">Создавайте ботов с помощью высокодоступных графических интерфейсов, которые не поддерживаются с помощью **виртуальных агентов** , для простого создания цифровых помощников в рамках групп и для того, чтобы они были доступны вашим коллегам для общения.</span><span class="sxs-lookup"><span data-stu-id="acaf8-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="acaf8-114">Новые возможности создания приложений, ботов и рабочих процессов создаются с помощью новой встроенной платформы данных с низким энергопотреблением для Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), которая обеспечивает хранение реляционных данных, расширенные типы данных, управление предприятием и развертывание решения одним щелчком.</span><span class="sxs-lookup"><span data-stu-id="acaf8-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="acaf8-115">Проект Oakdale строится на основе [общей службы данных](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="acaf8-115">Project Oakdale is built on top of [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="acaf8-116">С помощью Project Oakdale пользователи Teams могут находить и устанавливать пользовательские решения, готовые к использованию, из магазина App Stores, которые представляют собой распространенные сценарии для отраслей.</span><span class="sxs-lookup"><span data-stu-id="acaf8-116">With Project Oakdale, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="acaf8-117">Вы можете настроить и распространить эти пользовательские решения для адаптации к фирменной символике и требованиям Организации.</span><span class="sxs-lookup"><span data-stu-id="acaf8-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="acaf8-118">Лицензирование</span><span class="sxs-lookup"><span data-stu-id="acaf8-118">Licensing</span></span>

<span data-ttu-id="acaf8-119">Новые возможности доступны для подписок на план "Select Microsoft 365".</span><span class="sxs-lookup"><span data-stu-id="acaf8-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="acaf8-120">Дополнительные сведения о требованиях к лицензированию для приложений Power, Power, Power и Project Oakdale, можно найти в разделе [Лицензирование](https://go.microsoft.com/fwlink/?linkid=2143647).</span><span class="sxs-lookup"><span data-stu-id="acaf8-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Project Oakdale, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="acaf8-121">Более подробную информацию о требованиях к лицензированию Power BI можно найти в статьях [требования](https://go.microsoft.com/fwlink/?linkid=2143490).</span><span class="sxs-lookup"><span data-stu-id="acaf8-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="acaf8-122">Как начать работу?</span><span class="sxs-lookup"><span data-stu-id="acaf8-122">How do I get started?</span></span>

- [<span data-ttu-id="acaf8-123">Power BI и Teams</span><span class="sxs-lookup"><span data-stu-id="acaf8-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="acaf8-124">Power Apps и Teams</span><span class="sxs-lookup"><span data-stu-id="acaf8-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="acaf8-125">Автоматизация и команды в Power</span><span class="sxs-lookup"><span data-stu-id="acaf8-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="acaf8-126">Виртуальные агенты и команды Power.</span><span class="sxs-lookup"><span data-stu-id="acaf8-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
