---
title: Подготовка схемы
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы подготовить схему для доменных служб Active Directory, вы запускаете шаг подготовки схемы в мастере развертывания Skype для бизнеса Server. Для запуска подготовки схемы нажмите кнопку Выполнить.
ms.openlocfilehash: 4b0d24ff89badf1b026e6c57a4fbb75f2d46936f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691804"
---
# <a name="prepare-schema"></a><span data-ttu-id="18410-104">Подготовка схемы</span><span class="sxs-lookup"><span data-stu-id="18410-104">Prepare Schema</span></span>
 
<span data-ttu-id="18410-105">Чтобы подготовить схему для доменных служб Active Directory, вы запускаете шаг подготовки схемы в мастере развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="18410-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="18410-106">Для запуска подготовки схемы нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="18410-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="18410-107">На этапе подготовки схемы выполняется чтение предоставленных файлов определения схемы в каталоге \Program Филес\скипе для Business Server 2019 \ Деплоймент\сетуп на компьютере, на котором запущен мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="18410-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="18410-108">Эти файлы имеются также на установочном носителе в каталоге \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="18410-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="18410-109">На шаге "Подготовка схемы" выполняется также расширение схемы и формируется отчет о состоянии процесса.</span><span class="sxs-lookup"><span data-stu-id="18410-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="18410-110">Пользователь получает уведомление о завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="18410-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="18410-111">На экране сводки можно просмотреть журналы процесса.</span><span class="sxs-lookup"><span data-stu-id="18410-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="18410-112">Просмотрите журналы для проверки успешного завершения подготовки.</span><span class="sxs-lookup"><span data-stu-id="18410-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="18410-113">Для расширения схемы вы должны войти в домен как участник группы администраторов схемы или группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="18410-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="18410-114">Классы и атрибуты добавляются для продления схемы доменных служб Active Directory для поддержки серверных объектов, служб и пользователей Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="18410-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="18410-115">Перед расширением схемы следует создать резервную копию состояния системы для контроллера домена, выполняющего роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="18410-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="18410-116">Расширение схемы необратимо.</span><span class="sxs-lookup"><span data-stu-id="18410-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="18410-117">Необходимо приложить все усилия для успешного расширения схемы и ограничения возможных последствий в случае его сбоя.</span><span class="sxs-lookup"><span data-stu-id="18410-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="18410-118">Это особенно важно в случае потери связи или любого другого сбоя на сервере.</span><span class="sxs-lookup"><span data-stu-id="18410-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="18410-119">Вы должны выполнить резервное копирование контроллера домена хозяина схемы и полную архивацию службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="18410-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="18410-120">Чтобы выполнить резервное копирование контроллера домена хозяина схемы и полную архивацию службы каталогов Active Directory, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="18410-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="18410-121">Отсоедините от сети контроллер домена, содержащий роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="18410-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="18410-122">Выполните резервное копирование состояния системы контроллера домена, содержащего хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="18410-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="18410-123">Выполните расширение схемы.</span><span class="sxs-lookup"><span data-stu-id="18410-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="18410-124">Если расширение схемы прошло успешно, снова присоедините контроллер домена к сети и убедитесь, что репликация активна и работает.</span><span class="sxs-lookup"><span data-stu-id="18410-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="18410-125">В случае неудачи в случае сбоя расширения схемы восстановите состояние системы контроллера домена и Active Directory с помощью резервной копии состояния системы, которую вы сделали раньше.</span><span class="sxs-lookup"><span data-stu-id="18410-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="18410-126">Если вам нужно просмотреть файлы журнала, созданные с помощью мастера развертывания Skype для бизнеса Server, вы можете найти файлы на компьютере, на котором был запущен мастер развертывания, в каталоге Users пользователя Active Directory, выполнившего шаг.</span><span class="sxs-lookup"><span data-stu-id="18410-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="18410-127">Например, если пользователь выполнил вход в качестве администратора домена в Contoso.net домена, файлы журнала находятся в: К:\усерс\администратор.контосо\аппдата\локал\темп</span><span class="sxs-lookup"><span data-stu-id="18410-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

