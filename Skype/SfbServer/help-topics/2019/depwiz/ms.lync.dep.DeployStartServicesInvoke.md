---
title: Запуск служб (вызов)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: В области сводки на области "Выполнение команд" отображается состояние задач, выданных для запуска служб для развертываемого сервера ролей Skype для бизнеса Server.
ms.openlocfilehash: 34e128fd5c879c80e3e3eb242cd654b19c5f6dd3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808779"
---
# <a name="start-services-invoke"></a><span data-ttu-id="b95db-103">Запуск служб (вызов)</span><span class="sxs-lookup"><span data-stu-id="b95db-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="b95db-104">В области сводки  на области "Выполнение команд" отображается состояние задач, выданных для запуска служб для развертываемого сервера ролей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b95db-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="b95db-105">В представленной сводке отсутствует индикация запуска служб в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="b95db-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="b95db-106">На начало начального запуска некоторых служб Skype для бизнеса Server может потребоваться много времени.</span><span class="sxs-lookup"><span data-stu-id="b95db-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="b95db-107">Задачи дают команду на запуск, но не ожидают результата, чтобы определить, успешно ли запустилась служба.</span><span class="sxs-lookup"><span data-stu-id="b95db-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="b95db-108">Если вам необходимо отслеживать запуск службы и ее состояние, используйте консоль управления (MMC) для служб Windows.</span><span class="sxs-lookup"><span data-stu-id="b95db-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="b95db-p102">Под панелью задач находится раскрывающийся список, в котором отображается файл журнала **Запустить службы**. Для просмотра файла журнала нажмите кнопку **Просмотреть журнал**. Чтобы завершить задачу, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b95db-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

