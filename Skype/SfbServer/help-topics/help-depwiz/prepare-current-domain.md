---
title: Подготовка текущего домена
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Чтобы подготовить домен на серверах под управлением Скайп Business Server 2015 или Скайп для пользователей Business Server, необходимо выполнить шаг 5: Подготовка текущего домена, как описано в разделе Использование программы установки для выполнения подготовки домена. Для выполнения на шаге вы должны войти в систему как член группы администраторов домена в домен, в подготовке или как член группы "Администраторы предприятия", к которой принадлежит домену леса. Подготовка домена:'
ms.openlocfilehash: 3d32329220c59f8d51497bce5412351c412a845d
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260526"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="b5f9d-105">Подготовка текущего домена</span><span class="sxs-lookup"><span data-stu-id="b5f9d-105">Prepare Current Domain</span></span>

<span data-ttu-id="b5f9d-106">Чтобы подготовить домен на серверах под управлением Скайп Business Server 2015 или Скайп для пользователей Business Server, необходимо выполнить **Шаг 5: Подготовка текущего домена**, как описано в разделе [С помощью программы установки для выполнения подготовки домена](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span><span class="sxs-lookup"><span data-stu-id="b5f9d-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="b5f9d-107">Для выполнения на шаге вы должны войти в систему как член группы администраторов домена в домен, в подготовке или как член группы "Администраторы предприятия", к которой принадлежит домену леса.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="b5f9d-108">Подготовка домена:</span><span class="sxs-lookup"><span data-stu-id="b5f9d-108">To prepare the domain:</span></span>

1. <span data-ttu-id="b5f9d-109">Скайп для папки установки Business Server 2015 или на установочном носителе запустите Setup.exe, чтобы запустить Скайп для мастер развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="b5f9d-110">Нажмите **Подготовить Active Directory** и подождите, пока будет определено состояние развертывания.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="b5f9d-111">Когда появится окно **Шаг 5. Подготовка текущего домена**, нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="b5f9d-112">На странице **выполнения команд** подождите, пока не появится сообщение **Состояние задачи: Завершено**, а затем нажмите **Просмотреть журнал**.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="b5f9d-113">В столбце **Действие** разверните **Подготовка домена**, выполните поиск ** \<успешно\> ** результат выполнения в конце каждой задачи для проверки этого подготовки домена успешно завершена, закройте журнал и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="b5f9d-114">Если вам потребуется просмотрите файлы журнала, создаваемые с Скайп для мастер развертывания Business Server, их можно найти на компьютере, где запущен мастер развертывания в каталоге пользователи из доменных служб Active Directory пользователя, выполнившего действие.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="b5f9d-115">Например, если пользователь вошел в систему от имени администратора домена в домене Contoso.net, файлов журнала, находятся в: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="b5f9d-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


