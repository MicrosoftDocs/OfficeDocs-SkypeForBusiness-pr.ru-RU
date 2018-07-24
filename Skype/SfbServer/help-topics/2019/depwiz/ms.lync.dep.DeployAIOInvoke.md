---
title: Подготовка отдельного сервера Standard Edition (вызов)
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: На странице выполнение команд можно просмотреть задачи установки SQL Server Express и настройки в качестве центрального хранилища управления в области задач. По умолчанию создать экземпляр базы данных на основе SQL Server с именем RTC. Чтобы разрешить входящий и исходящий доступ для серверов и клиентов для взаимодействия с базой данных и экземпляр также создаются правила брандмауэра. После выполнения задачи, можно выбрать файл журнала из раскрывающегося списка. Файл журнала называется начальной загрузки локального компьютера. После выбора файла журнала, нажмите кнопку Просмотреть журнал. Просмотрите файл журнала все ошибки и предупреждения. Когда вы будете готовы продолжить, нажмите кнопку Готово. Теперь следует определить топологию с помощью построителя топологий, если это еще не сделано.
ms.openlocfilehash: 44fae0f1349b9252f207248fa99b714b0a8550ce
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987513"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="1f8c8-111">Подготовка отдельного сервера Standard Edition (вызов)</span><span class="sxs-lookup"><span data-stu-id="1f8c8-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="1f8c8-112">На странице **выполнение команд** можно просмотреть задачи установки SQL Server Express и настройки в качестве центрального хранилища управления в области задач.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="1f8c8-113">По умолчанию создать экземпляр базы данных на основе SQL Server с именем RTC.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="1f8c8-114">Чтобы разрешить входящий и исходящий доступ для серверов и клиентов для взаимодействия с базой данных и экземпляр также создаются правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="1f8c8-115">После выполнения задачи, можно выбрать файл журнала из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="1f8c8-116">Файл журнала называется **начальной загрузки локального компьютера**.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="1f8c8-117">После выбора файла журнала, нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="1f8c8-118">Просмотрите файл журнала все ошибки и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="1f8c8-119">Когда вы будете готовы продолжить, нажмите кнопку **Готово.**</span><span class="sxs-lookup"><span data-stu-id="1f8c8-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="1f8c8-120">Теперь следует определить топологию с помощью построителя топологий, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1f8c8-121">Установка SQL Server Express может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="1f8c8-122">Во время установки нет не хода выполнения отображается на экране или в области задач.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="1f8c8-123">Для процедуры установки, необходимо использовать диспетчер задач Windows и найдите для процессов MSIExec и файлы установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="1f8c8-124">Таким образом можно просматривать состояние установки и убедитесь, что установка будет продолжена.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="1f8c8-125">В зависимости от факторов выходит за рамки этого раздела справки может потребоваться до 15 минут или более экземпляра для установки SQL Server для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1f8c8-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

