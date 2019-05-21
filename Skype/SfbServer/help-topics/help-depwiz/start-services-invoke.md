---
title: Запуск служб (вызов)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
description: В области "Сводка" в области "выполняемые команды" отображаются сведения о состоянии задач, выданных для запуска служб для сервера ролей Skype для бизнеса Server 2015, который вы развертываете. В сводной информации в области задач не отображается запуск служб в реальном времени. Некоторые службы Skype для бизнеса Server могут занимать продолжительное время для начала начального процесса запуска. В процессе выполнения задач вызывается команда запуска, но этот процесс не приостанавливается для проверки успешности запуска службы. Если необходимо отслеживать запуск службы и ее состояние, следует пользоваться консолью управления (MMC) для служб Windows.
ms.openlocfilehash: 249ced56bd7abdc5b5142503fcffc5cb2107dde2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289563"
---
# <a name="start-services-invoke"></a><span data-ttu-id="3d6ce-107">Запуск служб (вызов)</span><span class="sxs-lookup"><span data-stu-id="3d6ce-107">Start Services (Invoke)</span></span>
 
<span data-ttu-id="3d6ce-108">В области "Сводка" в области " **выполняемые команды** " отображаются сведения о состоянии задач, выданных для запуска служб для сервера ролей Skype для бизнеса Server 2015, который вы развертываете.</span><span class="sxs-lookup"><span data-stu-id="3d6ce-108">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server 2015 role server that you are deploying.</span></span> <span data-ttu-id="3d6ce-109">В сводной информации в области задач не отображается запуск служб в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="3d6ce-109">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="3d6ce-110">Некоторые службы Skype для бизнеса Server могут занимать продолжительное время для начала начального процесса запуска.</span><span class="sxs-lookup"><span data-stu-id="3d6ce-110">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="3d6ce-111">В процессе выполнения задач вызывается команда запуска, но этот процесс не приостанавливается для проверки успешности запуска службы.</span><span class="sxs-lookup"><span data-stu-id="3d6ce-111">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="3d6ce-112">Если необходимо отслеживать запуск службы и ее состояние, следует пользоваться консолью управления (MMC) для служб Windows.</span><span class="sxs-lookup"><span data-stu-id="3d6ce-112">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="3d6ce-p103">Под областью задач находится раскрывающийся список, в котором отображается файл журнала **Запустить службы**. Для просмотра файла журнала нажмите кнопку **Просмотреть журнал**. Для завершения задачи нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="3d6ce-p103">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

