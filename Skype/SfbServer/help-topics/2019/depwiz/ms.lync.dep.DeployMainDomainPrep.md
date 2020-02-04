---
title: Подготовка текущего домена
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы подготовить домен на доступ к серверам, на которых работают пользователи Skype для бизнеса Server или Skype для бизнеса Server, необходимо выполнить шаг 5: подготовка текущего домена, как описано в разделе Использование программы установки для подготовки домена. Для выполнения этого шага необходимо войти в систему в качестве члена группы администраторов домена в подготавливается домен или входить в группу администраторов предприятия для леса, которому принадлежит домен. Чтобы подготовить домен, выполните указанные ниже действия.'
ms.openlocfilehash: 966f80fe799529ec4d208318fa417146db67ea13
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705444"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="f643a-105">Подготовка текущего домена</span><span class="sxs-lookup"><span data-stu-id="f643a-105">Prepare Current Domain</span></span>

<span data-ttu-id="f643a-106">Чтобы подготовить домен на доступ к серверам, на которых работают пользователи Skype для бизнеса Server или Skype для бизнеса Server, необходимо выполнить **Шаг 5: подготовка текущего домена**, как описано в разделе [Использование программы установки для подготовки домена](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="f643a-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="f643a-107">Для выполнения этого шага необходимо войти в систему в качестве члена группы администраторов домена в подготавливается домен или входить в группу администраторов предприятия для леса, которому принадлежит домен.</span><span class="sxs-lookup"><span data-stu-id="f643a-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="f643a-108">Чтобы подготовить домен, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f643a-108">To prepare the domain:</span></span>

1. <span data-ttu-id="f643a-109">В установочной папке или мультимедиа Skype для бизнеса Server запустите программу Setup. exe, чтобы запустить мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f643a-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="f643a-110">Нажмите **Подготовить Active Directory** и подождите, пока будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="f643a-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="f643a-111">Когда появится окно **Шаг 5. Подготовка текущего домена**, нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f643a-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="f643a-112">На странице **выполнения команд** подождите, пока не появится сообщение **Состояние задачи: Завершено**, а затем нажмите **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="f643a-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="f643a-113">В столбце **Action (действие** ) разверните **доменную версию домена**, найдите \*\* \<\> результаты выполнения в\*\* конце каждой задачи, чтобы убедиться в том, что подготовка домена успешно завершена, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f643a-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="f643a-114">Если вам нужно просмотреть файлы журнала, созданные с помощью мастера развертывания Skype для бизнеса Server, вы можете найти их на компьютере, на котором был запущен мастер развертывания, в каталоге Users доменных служб Active Directory, выполнившего шаг.</span><span class="sxs-lookup"><span data-stu-id="f643a-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="f643a-115">Например, если пользователь выполнил вход в качестве администратора домена в Contoso.net домена, файлы журнала находятся в: К:\усерс\администратор.контосо\аппдата\локал\темп.</span><span class="sxs-lookup"><span data-stu-id="f643a-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


