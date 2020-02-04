---
title: Подготовка отдельного сервера Standard Edition (вызов)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: На странице Выполнение команд задачи по установке SQL Server Express и настройке для работы в качестве хранилища центрального управления можно просмотреть в области задач. По умолчанию создается экземпляр базы данных на основе SQL Server с именем RTC. Кроме того, создаются правила брандмауэра, разрешающие входящему и исходящий доступ к базам данных и экземпляру серверов и клиентов. После завершения задачи вы можете выбрать файл журнала из раскрывающегося списка. Файл журнала называется "локальный компьютер для начальной загрузки". Выбрав файл журнала, нажмите кнопку Просмотреть журнал. Проверьте файл журнала на наличие ошибок и предупреждений. Когда вы будете готовы продолжить, нажмите кнопку Готово. Теперь вы можете определить топологию с помощью построителя топологии, если это еще не сделано.
ms.openlocfilehash: 729bdacffff09876272e45a34377ced950e88ebf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700814"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="970a8-111">Подготовка отдельного сервера Standard Edition (вызов)</span><span class="sxs-lookup"><span data-stu-id="970a8-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="970a8-112">На странице **выполнение команд** задачи по установке SQL Server Express и настройке для работы в качестве хранилища центрального управления можно просмотреть в области задач.</span><span class="sxs-lookup"><span data-stu-id="970a8-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="970a8-113">По умолчанию создается экземпляр базы данных на основе SQL Server с именем RTC.</span><span class="sxs-lookup"><span data-stu-id="970a8-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="970a8-114">Кроме того, создаются правила брандмауэра, разрешающие входящему и исходящий доступ к базам данных и экземпляру серверов и клиентов.</span><span class="sxs-lookup"><span data-stu-id="970a8-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="970a8-115">После завершения задачи вы можете выбрать файл журнала из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="970a8-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="970a8-116">Файл журнала называется " **локальный компьютер для начальной загрузки**".</span><span class="sxs-lookup"><span data-stu-id="970a8-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="970a8-117">Выбрав файл журнала, нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="970a8-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="970a8-118">Проверьте файл журнала на наличие ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="970a8-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="970a8-119">Когда вы будете готовы продолжить, нажмите кнопку **Готово.**</span><span class="sxs-lookup"><span data-stu-id="970a8-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="970a8-120">Теперь вы можете определить топологию с помощью построителя топологии, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="970a8-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="970a8-121">Для завершения установки SQL Server Express может потребоваться некоторое время.</span><span class="sxs-lookup"><span data-stu-id="970a8-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="970a8-122">Во время установки не отображается индикатор выполнения на экране или в области задач.</span><span class="sxs-lookup"><span data-stu-id="970a8-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="970a8-123">Для наблюдения за установкой следует использовать диспетчер задач Windows и искать процессы MSIExec и файлы установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="970a8-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="970a8-124">Таким образом, вы можете просмотреть состояние установки и убедиться, что установка продолжается.</span><span class="sxs-lookup"><span data-stu-id="970a8-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="970a8-125">В зависимости от факторов, описанных в этом разделе справки, для завершения установки экземпляра SQL Server может потребоваться до 15 минут или более.</span><span class="sxs-lookup"><span data-stu-id="970a8-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

