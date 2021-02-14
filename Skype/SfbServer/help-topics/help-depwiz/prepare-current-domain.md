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
description: 'To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete Step 5: Prepare Current Domain, as described in the topic Using Setup to Run Domain Preparation. Для выполнения этого шага необходимо войти в систему как участник группы администраторов домена в подготавливаемом домене или как участник группы администраторов предприятия леса, к которой принадлежит домен. Чтобы подготовить домен:'
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804969"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="fe037-105">Подготовка текущего домена</span><span class="sxs-lookup"><span data-stu-id="fe037-105">Prepare Current Domain</span></span>

<span data-ttu-id="fe037-106">Чтобы подготовить домен для серверов, на которые работают пользователи Skype для бизнеса Server 2015 или Skype для бизнеса [](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)Server, необходимо выполнить шаг **5.** Подготовка текущего домена, как описано в разделе "Использование программы установки для выполнения подготовки домена".</span><span class="sxs-lookup"><span data-stu-id="fe037-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="fe037-107">Для выполнения этого шага необходимо войти в систему как участник группы администраторов домена в подготавливаемом домене или как участник группы администраторов предприятия леса, к которой принадлежит домен.</span><span class="sxs-lookup"><span data-stu-id="fe037-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="fe037-108">Чтобы подготовить домен:</span><span class="sxs-lookup"><span data-stu-id="fe037-108">To prepare the domain:</span></span>

1. <span data-ttu-id="fe037-109">В папке или на носите для установки Skype для бизнеса Server 2015 запустите Setup.exe, чтобы запустить мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fe037-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="fe037-110">Щелкните **Подготовить Active Directory** и дождитесь, когда определится состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="fe037-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="fe037-111">На странице **Шаг 5. Подготовить текущий домен** нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fe037-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="fe037-112">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="fe037-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="fe037-113">В **столбце "Действие"** разйдите "Подготовка домена" **и** найдите результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка домена успешно завершена, закроем журнал и нажмите кнопку **\<Success\>** **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="fe037-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="fe037-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span><span class="sxs-lookup"><span data-stu-id="fe037-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="fe037-115">Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="fe037-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


