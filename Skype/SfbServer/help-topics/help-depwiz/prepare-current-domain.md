---
title: Подготовка текущего домена
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Чтобы подготовить домен для серверов, на которые работают Skype для бизнеса Server 2015 или Skype для пользователей бизнес-сервера, необходимо выполнить шаг 5: Подготовка текущего домена, как описано в разделе Использование установки для запуска подготовки домена. Чтобы выполнить этот шаг, необходимо войти в группу администраторов домена в готовяемом домене или в качестве члена группы администраторов предприятия леса, к которой принадлежит домен. Чтобы подготовить домен:'
ms.openlocfilehash: c9c33e466b7b0fcc7c2711603c284e5f419960a1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096875"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="2bbab-105">Подготовка текущего домена</span><span class="sxs-lookup"><span data-stu-id="2bbab-105">Prepare Current Domain</span></span>

<span data-ttu-id="2bbab-106">Чтобы подготовить домен для серверов, на которые работают Skype для бизнеса Server 2015 или Skype для пользователей бизнес-сервера, необходимо выполнить шаг **5:** Подготовка текущего домена, как описано в разделе [Использование](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)установки для запуска подготовки домена .</span><span class="sxs-lookup"><span data-stu-id="2bbab-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="2bbab-107">Чтобы выполнить этот шаг, необходимо войти в группу администраторов домена в готовяемом домене или в качестве члена группы администраторов предприятия леса, к которой принадлежит домен.</span><span class="sxs-lookup"><span data-stu-id="2bbab-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="2bbab-108">Чтобы подготовить домен:</span><span class="sxs-lookup"><span data-stu-id="2bbab-108">To prepare the domain:</span></span>

1. <span data-ttu-id="2bbab-109">Чтобы запустить мастер развертывания Skype для бизнеса Server 2015, запустите Setup.exe skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2bbab-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="2bbab-110">Щелкните **Подготовить Active Directory** и дождитесь, когда определится состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="2bbab-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="2bbab-111">На странице **Шаг 5. Подготовить текущий домен** нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2bbab-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="2bbab-112">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="2bbab-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="2bbab-113">В столбце **Действие** разойдитесь по предварительной подготовке домена **и** выберите результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка домена успешно завершена, закрой журнал и нажмите **\<Success\>** кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2bbab-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="2bbab-114">Если необходимо просмотреть файлы журналов, созданные мастером развертывания Skype для бизнес-серверов, их можно найти на компьютере, на котором мастер развертывания запускался в каталоге пользователей пользователя служб домена Active Directory, который запустил этот шаг.</span><span class="sxs-lookup"><span data-stu-id="2bbab-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="2bbab-115">Например, если пользователь вошел в качестве администратора домена в домене Contoso.net, файлы журнала находятся в: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="2bbab-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>