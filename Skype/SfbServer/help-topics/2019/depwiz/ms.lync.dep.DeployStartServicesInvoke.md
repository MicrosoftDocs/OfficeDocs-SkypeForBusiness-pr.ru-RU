---
title: Запуск служб (вызов)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: Области сводки в области выполнения команд состояние задачи, выдается для запуска служб для Скайп для сервера Business Server role, который развертывает администратор.
ms.openlocfilehash: db2e0282e15b1995aa6b83bcfdd4ecbecd922207
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887853"
---
# <a name="start-services-invoke"></a><span data-ttu-id="ed464-103">Запуск служб (вызов)</span><span class="sxs-lookup"><span data-stu-id="ed464-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="ed464-104">Области сводки в области **Выполнения команд** состояние задачи, выдается для запуска служб для Скайп для сервера Business Server role, который развертывает администратор.</span><span class="sxs-lookup"><span data-stu-id="ed464-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="ed464-105">В сводной информации в области задач не отображается запуск служб в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="ed464-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="ed464-106">Некоторые Скайп для служб Business Server может занять длительное время, чтобы начать процесс начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="ed464-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="ed464-107">В процессе выполнения задач вызывается команда запуска, но этот процесс не приостанавливается для проверки успешности запуска службы.</span><span class="sxs-lookup"><span data-stu-id="ed464-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="ed464-108">Если необходимо отслеживать запуск службы и ее состояние, следует пользоваться консолью управления (MMC) для служб Windows.</span><span class="sxs-lookup"><span data-stu-id="ed464-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="ed464-p102">Под областью задач находится раскрывающийся список, в котором отображается файл журнала **Запустить службы**. Для просмотра файла журнала нажмите кнопку **Просмотреть журнал**. Для завершения задачи нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ed464-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

