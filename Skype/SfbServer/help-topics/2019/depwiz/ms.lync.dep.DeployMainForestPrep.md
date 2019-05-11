---
title: Подготовка текущего леса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы подготовить лес доменных служб Active Directory, необходимо успешно расширить схему, как описано в разделе Running Schema Preparation и убедитесь в том, что схема была реплицирована.
ms.openlocfilehash: 5cf217e054f513b8e3fcbc203cf4c0d76719e7cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893695"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="862a8-103">Подготовка текущего леса</span><span class="sxs-lookup"><span data-stu-id="862a8-103">Prepare Current Forest</span></span>

<span data-ttu-id="862a8-104">Чтобы подготовить лес доменных служб Active Directory, необходимо успешно расширить схему, как описано в разделе [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)и убедитесь в том, что схема была реплицирована.</span><span class="sxs-lookup"><span data-stu-id="862a8-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="862a8-p101">После этого можно перейти к странице **Шаг 3. Подготовить текущий лес**. Для подготовки леса войдите в систему на компьютере в корне леса как участник группы администраторов домена в корне леса или администраторов предприятия для подготавливаемого леса.</span><span class="sxs-lookup"><span data-stu-id="862a8-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="862a8-107">На странице **Шаг 3. Подготовить текущий лес** мастера развертывания нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="862a8-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="862a8-108">На странице **Подготовка леса** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="862a8-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="862a8-109">Подготовка леса позволяет выбрать поместить универсальных групп для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="862a8-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="862a8-110">Выберите расположение в соответствии с требованиями организации.</span><span class="sxs-lookup"><span data-stu-id="862a8-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="862a8-p103">На странице **Выполнение команд** найдите запись **Состояние задачи: Завершено**, затем нажмите кнопку **Просмотр журнала**. Убедитесь в отсутствии ошибок. Просмотрите предупреждения и определите, являются ли они ожидаемыми и типичными для данной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="862a8-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="862a8-114">В столбце **Действие** в журнале, разверните узел **Подготовка леса**, найдите \*\* \<успешно\> \*\* результат выполнения в конце каждой задачи для проверки этого процедура подготовки леса успешно завершена, закройте журнал и нажмите кнопку Готово \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="862a8-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="862a8-115">Дождитесь завершения репликации доменных служб Active Directory или выполните принудительную репликацию на все контроллеры доменов, перечисленных в **Active Directory — сайты и службы** оснастку для контроллера корневого домена леса, перед запуском подготовки домена.</span><span class="sxs-lookup"><span data-stu-id="862a8-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="862a8-116">Принудительной репликации между контроллерами домена на всех сайтах Active Directory должны стать причиной репликацию в пределах сайта в минутах.</span><span class="sxs-lookup"><span data-stu-id="862a8-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="862a8-117">Если вам потребуется просмотрите файлы журнала, создаваемые с Скайп для мастер развертывания Business Server, их можно найти на компьютере, на котором запускался мастер развертывания в каталоге пользователи из доменных служб Active Directory пользователя, выполнившего действие.</span><span class="sxs-lookup"><span data-stu-id="862a8-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="862a8-118">Например, если пользователь вошел в систему от имени администратора домена в домене Contoso.net, файлов журнала, находятся в: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="862a8-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


