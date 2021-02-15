---
title: Подготовка отдельного сервера Standard Edition (вызов)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: На странице "Выполнение команд" задачи установки SQL Server Express и настройки работы в качестве центрального банка управления можно просмотреть в области задач. По умолчанию создается экземпляр базы SQL Server RTC. Правила брандмауэра также создаются, чтобы разрешить серверам и клиентам входящий и исходящие доступ к базе данных и экземпляру. После завершения задачи можно выбрать файл журнала в выпадаемом списке. Файл журнала называется "Локальный компьютер Bootstrap". После выбора файла журнала нажмите кнопку "Просмотреть журнал". Просмотрите файл журнала на все ошибки и предупреждения. Когда вы будете готовы продолжить, нажмите кнопку "Готово". Теперь необходимо определить топологию с помощью построитель топологий, если это еще не сделано.
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829749"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="89230-111">Подготовка отдельного сервера Standard Edition (вызов)</span><span class="sxs-lookup"><span data-stu-id="89230-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="89230-112">На странице **"Выполнение** команд" задачи по установке SQL Server Express и настройке работы в качестве центрального банка управления можно просмотреть в области задач.</span><span class="sxs-lookup"><span data-stu-id="89230-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="89230-113">По умолчанию создается экземпляр базы SQL Server RTC.</span><span class="sxs-lookup"><span data-stu-id="89230-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="89230-114">Правила брандмауэра также создаются, чтобы разрешить серверам и клиентам входящий и исходящие доступ к базе данных и экземпляру.</span><span class="sxs-lookup"><span data-stu-id="89230-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="89230-115">После завершения задачи можно выбрать файл журнала в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="89230-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="89230-116">Файл журнала называется **локальным компьютером Bootstrap.**</span><span class="sxs-lookup"><span data-stu-id="89230-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="89230-117">После выбора файла журнала нажмите кнопку **"Просмотреть журнал".**</span><span class="sxs-lookup"><span data-stu-id="89230-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="89230-118">Просмотрите файл журнала на все ошибки и предупреждения.</span><span class="sxs-lookup"><span data-stu-id="89230-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="89230-119">Когда вы будете готовы продолжить, нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="89230-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="89230-120">Теперь необходимо определить топологию с помощью построитель топологий, если это еще не сделано.</span><span class="sxs-lookup"><span data-stu-id="89230-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="89230-121">Установка SQL Server Express может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="89230-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="89230-122">Во время установки ход выполнения не отображается на экране или панели задач.</span><span class="sxs-lookup"><span data-stu-id="89230-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="89230-123">Для отслеживания установки следует использовать диспетчер задач Windows и искать процессы MSIExec и файлы установки для SQL Server.</span><span class="sxs-lookup"><span data-stu-id="89230-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="89230-124">Таким способом вы можете посмотреть состояние установки и убедиться, что она выполняется.</span><span class="sxs-lookup"><span data-stu-id="89230-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="89230-125">В зависимости от факторов, не влияющих на данный раздел справки, установка экземпляра SQL Server может занять до 15 минут или более.</span><span class="sxs-lookup"><span data-stu-id="89230-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

