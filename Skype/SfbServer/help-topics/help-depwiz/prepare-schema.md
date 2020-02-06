---
title: Подготовка схемы
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Чтобы подготовить схему для доменных служб Active Directory, вы запускаете шаг подготовки схемы в мастере развертывания Skype для бизнеса Server. Для запуска подготовки схемы нажмите кнопку Выполнить. Шаг подготовки схемы считывает предоставленные файлы определения схемы в каталог/програм Files/Microsoft Lync Server 2013/развертывание/Настройка в системе, на которой запущен мастер развертывания. Эти файлы также доступны на установочном носителе в каталоге поддержки/схемы. На шаге "Подготовка схемы" выполняется также расширение схемы и формируется отчет о состоянии процесса. Пользователь получает уведомление о завершении процесса. На экране сводки можно просмотреть журналы процесса. Просмотрите журналы для проверки успешного завершения подготовки.
ms.openlocfilehash: ae4c44adf8c94efa7b87c9f1a4f5f142a7117276
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823483"
---
# <a name="prepare-schema"></a><span data-ttu-id="eba1c-110">Подготовка схемы</span><span class="sxs-lookup"><span data-stu-id="eba1c-110">Prepare Schema</span></span>
 
<span data-ttu-id="eba1c-111">Чтобы подготовить схему для доменных служб Active Directory, вы запускаете шаг подготовки схемы в мастере развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="eba1c-111">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="eba1c-112">Для запуска подготовки схемы нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="eba1c-112">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="eba1c-113">На шаге "Подготовка схемы" считываются предоставленные файлы определений схемы из каталога \Program Files\Microsoft Lync Server 2013\Deployment\Setup в системе, где работает мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="eba1c-113">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="eba1c-114">Эти файлы имеются также на установочном носителе в каталоге \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="eba1c-114">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="eba1c-115">На шаге "Подготовка схемы" выполняется также расширение схемы и формируется отчет о состоянии процесса.</span><span class="sxs-lookup"><span data-stu-id="eba1c-115">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="eba1c-116">Пользователь получает уведомление о завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="eba1c-116">It will also notify you when the process is complete.</span></span> <span data-ttu-id="eba1c-117">На экране сводки можно просмотреть журналы процесса.</span><span class="sxs-lookup"><span data-stu-id="eba1c-117">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="eba1c-118">Просмотрите журналы для проверки успешного завершения подготовки.</span><span class="sxs-lookup"><span data-stu-id="eba1c-118">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eba1c-119">Для расширения схемы вы должны войти в домен как участник группы администраторов схемы или группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="eba1c-119">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="eba1c-120">Классы и атрибуты добавляются для продления схемы доменных служб Active Directory для поддержки сервера, службы и объектов пользователей Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="eba1c-120">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server 2015 server, service, and user objects.</span></span> <span data-ttu-id="eba1c-121">Перед расширением схемы следует создать резервную копию состояния системы для контроллера домена, выполняющего роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="eba1c-121">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="eba1c-122">Подробные сведения о процессе резервного копирования для Windows Server 2008 R2 с пакетом [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)обновления 1 (SP1) можно найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="eba1c-122">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="eba1c-123">Для Windows Server 2003 и Windows Server 2003 R2 вы видите [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span><span class="sxs-lookup"><span data-stu-id="eba1c-123">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="eba1c-124">Расширение схемы необратимо.</span><span class="sxs-lookup"><span data-stu-id="eba1c-124">Extending the schema is not reversible.</span></span> <span data-ttu-id="eba1c-125">Необходимо приложить все усилия для успешного расширения схемы и ограничения возможных последствий в случае его сбоя.</span><span class="sxs-lookup"><span data-stu-id="eba1c-125">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="eba1c-126">Это особенно важно в случае потери связи или любого другого сбоя на сервере.</span><span class="sxs-lookup"><span data-stu-id="eba1c-126">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="eba1c-127">Вы должны выполнить резервное копирование контроллера домена хозяина схемы и полную архивацию службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eba1c-127">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="eba1c-128">Чтобы выполнить резервное копирование контроллера домена хозяина схемы и полную архивацию службы каталогов Active Directory, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="eba1c-128">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="eba1c-129">Отсоедините от сети контроллер домена, содержащий роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="eba1c-129">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="eba1c-130">Выполните резервное копирование состояния системы контроллера домена, содержащего хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="eba1c-130">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="eba1c-131">Выполните расширение схемы.</span><span class="sxs-lookup"><span data-stu-id="eba1c-131">Extend the schema.</span></span>
    
4. <span data-ttu-id="eba1c-132">Если расширение схемы прошло успешно, снова присоедините контроллер домена к сети и убедитесь, что репликация активна и работает.</span><span class="sxs-lookup"><span data-stu-id="eba1c-132">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="eba1c-133">В случае неудачи в случае сбоя расширения схемы восстановите состояние системы контроллера домена и Active Directory с помощью резервной копии состояния системы, которую вы сделали раньше.</span><span class="sxs-lookup"><span data-stu-id="eba1c-133">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eba1c-134">Если вам нужно просмотреть файлы журнала, созданные с помощью мастера развертывания Skype для бизнеса Server, вы можете найти файлы на компьютере, на котором был запущен мастер развертывания, в каталоге Users пользователя Active Directory, выполнившего шаг.</span><span class="sxs-lookup"><span data-stu-id="eba1c-134">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="eba1c-135">Например, если пользователь выполнил вход в качестве администратора домена в Contoso.net домена, файлы журнала находятся в: К:\усерс\администратор.контосо\аппдата\локал\темп</span><span class="sxs-lookup"><span data-stu-id="eba1c-135">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

