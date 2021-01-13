---
title: Подготовка текущего леса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Для подготовки леса доменных служб Active Directory необходимо успешно расширить схему, как описано в разделе "Подготовка схемы" и убедиться, что схема реплицирована.
ms.openlocfilehash: 4881cb85134fef81cd741d834f319a76d4028e59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833829"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="6272a-103">Подготовка текущего леса</span><span class="sxs-lookup"><span data-stu-id="6272a-103">Prepare Current Forest</span></span>

<span data-ttu-id="6272a-104">Чтобы подготовить лес доменных служб Active Directory, необходимо успешно расширить схему, как описано в разделе "Подготовка схемы" и убедиться, что схема реплицирована. [](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)</span><span class="sxs-lookup"><span data-stu-id="6272a-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="6272a-p101">После этого можно начать **Шаг 3. Подготовить текущий лес**. Чтобы подготовить лес, войдите в компьютер, расположенный в корне леса, как участник группы администраторов домена в корне леса или как участник группы администраторов предприятия для подготавливаемого леса.</span><span class="sxs-lookup"><span data-stu-id="6272a-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="6272a-107">На странице **Шаг 3. Подготовить текущий лес** мастера развертывания нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6272a-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="6272a-108">На странице **Подготовка леса** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6272a-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6272a-109">Подготовка леса позволяет выбрать, где разместить универсальные группы для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6272a-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="6272a-110">Выбирайте место в соответствии с требованиями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6272a-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="6272a-p103">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, а затем нажмите кнопку **Просмотреть журнал**. Убедитесь, что нет ошибок. Просмотрите предупреждения и определите, являются ли они ожидаемыми и типичными для вашей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="6272a-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="6272a-114">В столбце **действий** в журнале разйдите "Подготовка леса" **и** найдите результат выполнения в конце каждой задачи, чтобы убедиться, что подготовка леса успешно завершена, закроем журнал и нажмите кнопку **\<Success\>** **"Готово"**.</span><span class="sxs-lookup"><span data-stu-id="6272a-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="6272a-115">Дождись завершения репликации доменных служб **Active Directory** или принудительно выполните репликацию на все контроллеры домена, указанные в оснастке "Active Directory — сайты и службы" для корневого контроллера домена леса, прежде чем при запуске подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="6272a-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="6272a-116">Принудительная репликация между контроллерами доменов во всех сайтах приведет к выполнению репликации в сайтах за несколько минут.</span><span class="sxs-lookup"><span data-stu-id="6272a-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="6272a-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span><span class="sxs-lookup"><span data-stu-id="6272a-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="6272a-118">Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="6272a-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


