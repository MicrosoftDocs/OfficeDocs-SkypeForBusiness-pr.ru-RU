---
title: Запуск служб (вызов)
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
ms.openlocfilehash: 119f7027c09d67f8c1182e20186d568007f0ca71
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026007"
---
# <a name="start-services-invoke"></a><span data-ttu-id="9b35c-103">Запуск служб (вызов)</span><span class="sxs-lookup"><span data-stu-id="9b35c-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="9b35c-104">Области сводки в области **Выполнения команд** состояние задачи, выдается для запуска служб для Скайп для сервера Business Server role, который развертывает администратор.</span><span class="sxs-lookup"><span data-stu-id="9b35c-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="9b35c-105">В сводной информации в области задач не отображается запуск служб в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="9b35c-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="9b35c-106">Некоторые Скайп для служб Business Server может занять длительное время, чтобы начать процесс начальной загрузки.</span><span class="sxs-lookup"><span data-stu-id="9b35c-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="9b35c-107">В процессе выполнения задач вызывается команда запуска, но этот процесс не приостанавливается для проверки успешности запуска службы.</span><span class="sxs-lookup"><span data-stu-id="9b35c-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="9b35c-108">Если необходимо отслеживать запуск службы и ее состояние, следует пользоваться консолью управления (MMC) для служб Windows.</span><span class="sxs-lookup"><span data-stu-id="9b35c-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="9b35c-p102">Под областью задач находится раскрывающийся список, в котором отображается файл журнала **Запустить службы**. Для просмотра файла журнала нажмите кнопку **Просмотреть журнал**. Для завершения задачи нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9b35c-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

