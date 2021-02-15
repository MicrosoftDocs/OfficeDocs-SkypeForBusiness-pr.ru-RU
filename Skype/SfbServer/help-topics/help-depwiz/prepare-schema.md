---
title: Подготовка схемы
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
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Чтобы подготовить схему для доменных служб Active Directory, запустите этап подготовки схемы в мастере развертывания Skype для бизнеса Server. Нажмите кнопку Выполнить, чтобы начать подготовку схемы. На этапе подготовки схемы считыются предоставленные файлы определения схемы в каталоге /Program Files/Microsoft Lync Server 2013/Deployment/Setup в системе, в которую запущен мастер развертывания. Эти файлы также доступны на установщике в каталоге поддержки и схемы. Шаг "Подготовка схемы" осуществляет расширение схемы и сообщает о состоянии процесса. Вы получите уведомление, когда процесс завершится. На экране сводки можно просмотреть журналы процесса. Просмотрите журналы и убедитесь, что подготовка была успешно завершена.
ms.openlocfilehash: c6c29dfd8e9b0908091e61a569ca56a467a014d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829799"
---
# <a name="prepare-schema"></a><span data-ttu-id="39956-110">Подготовка схемы</span><span class="sxs-lookup"><span data-stu-id="39956-110">Prepare Schema</span></span>
 
<span data-ttu-id="39956-111">Чтобы подготовить схему для доменных служб Active Directory, запустите этап подготовки схемы в мастере развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="39956-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="39956-112">Нажмите кнопку **Выполнить**, чтобы начать подготовку схемы.</span><span class="sxs-lookup"><span data-stu-id="39956-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="39956-113">На этапе подготовки схемы считыются предоставленные файлы определения схемы в каталоге \Program Files\Microsoft Lync Server 2013\Deployment\Setup в системе, в которую запущен мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="39956-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="39956-114">Эти файлы имеются также на установочном носителе в каталоге \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="39956-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="39956-115">Шаг "Подготовка схемы" осуществляет расширение схемы и сообщает о состоянии процесса.</span><span class="sxs-lookup"><span data-stu-id="39956-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="39956-116">Вы получите уведомление, когда процесс завершится.</span><span class="sxs-lookup"><span data-stu-id="39956-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="39956-117">На экране сводки можно просмотреть журналы процесса.</span><span class="sxs-lookup"><span data-stu-id="39956-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="39956-118">Просмотрите журналы и убедитесь, что подготовка была успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="39956-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39956-119">Для расширения схемы вы должны войти в домен как участник группы администраторов схемы или группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="39956-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="39956-120">Классы и атрибуты добавляются для расширения схемы доменных служб Active Directory для поддержки объектов сервера, службы и пользователей Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="39956-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="39956-121">Перед расширением схемы создайте резервную копию состояния системы контроллера домена, содержащего роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="39956-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="39956-122">Подробные сведения о процессе резервного копирования Windows Server 2008 R2 с sp1 см. в [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198) .</span><span class="sxs-lookup"><span data-stu-id="39956-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="39956-123">Для Windows Server 2003 и Windows Server 2003 R2 [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199) см.</span><span class="sxs-lookup"><span data-stu-id="39956-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="39956-124">Расширение схемы необратимо.</span><span class="sxs-lookup"><span data-stu-id="39956-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="39956-125">Вы должны постараться максимально ограничить возможные последствия неудачного расширения схемы и приложить все усилия, чтобы это расширение было успешным.</span><span class="sxs-lookup"><span data-stu-id="39956-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="39956-126">В частности, это критично при потере соединения или любом другом сбое сервера.</span><span class="sxs-lookup"><span data-stu-id="39956-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="39956-127">Необходимо выполнить резервное копирование контроллера домена хозяина схемы и полную резервную копию Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39956-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="39956-128">Чтобы выполнить резервное копирование контроллера домена хозяина схемы и полную резервную копию Active Directory:</span><span class="sxs-lookup"><span data-stu-id="39956-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="39956-129">Отсоедините от сети контроллер домена, содержащий роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="39956-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="39956-130">Выполните резервное копирование состояния системы контроллера домена, содержащего хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="39956-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="39956-131">Выполните расширение схемы.</span><span class="sxs-lookup"><span data-stu-id="39956-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="39956-132">Если расширение схемы прошло успешно, снова присоедините контроллер домена к сети и убедитесь, что репликация активна и работает.</span><span class="sxs-lookup"><span data-stu-id="39956-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="39956-133">В маловероятном случае сбоя расширения схемы восстановите состояние систем контроллера домена и Active Directory с помощью резервной копии состояния системы, которую вы использовали ранее.</span><span class="sxs-lookup"><span data-stu-id="39956-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="39956-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span><span class="sxs-lookup"><span data-stu-id="39956-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="39956-135">Например, если пользователь вошел с учетной записью администратора домена в домене Contoso.net, файлы журнала будут расположены в папке C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="39956-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

