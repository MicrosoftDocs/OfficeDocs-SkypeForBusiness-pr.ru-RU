---
title: Подготовка схемы
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Для подготовки схемы для доменных служб Active Directory, для запуска на этапе подготовки схемы Скайп для мастер развертывания Business Server. Для запуска подготовки схемы нажмите кнопку Выполнить.
ms.openlocfilehash: adc0ad796b608671816d50a93f75dc89f2a4a13b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020135"
---
# <a name="prepare-schema"></a><span data-ttu-id="92479-104">Подготовка схемы</span><span class="sxs-lookup"><span data-stu-id="92479-104">Prepare Schema</span></span>
 
<span data-ttu-id="92479-105">Для подготовки схемы для доменных служб Active Directory, для запуска на этапе подготовки схемы Скайп для мастер развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="92479-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="92479-106">Для запуска подготовки схемы нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="92479-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="92479-107">На шаге "Подготовка схемы" считываются предоставленные файлы определений схемы из каталога \Program Files\Microsoft Lync Server 2013\Deployment\Setup в системе, где работает мастер развертывания.</span><span class="sxs-lookup"><span data-stu-id="92479-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="92479-108">Эти файлы имеются также на установочном носителе в каталоге \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="92479-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="92479-109">На шаге "Подготовка схемы" выполняется также расширение схемы и формируется отчет о состоянии процесса.</span><span class="sxs-lookup"><span data-stu-id="92479-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="92479-110">Пользователь получает уведомление о завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="92479-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="92479-111">На экране сводки можно просмотреть журналы процесса.</span><span class="sxs-lookup"><span data-stu-id="92479-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="92479-112">Просмотрите журналы для проверки успешного завершения подготовки.</span><span class="sxs-lookup"><span data-stu-id="92479-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="92479-113">Для расширения схемы вы должны войти в домен как участник группы администраторов схемы или группы администраторов предприятия.</span><span class="sxs-lookup"><span data-stu-id="92479-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="92479-114">Классы и атрибуты добавляются для расширения схемы доменных служб Active Directory для поддержки Скайп для сервера, службы и объектов-пользователей Business Server.</span><span class="sxs-lookup"><span data-stu-id="92479-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="92479-115">Перед расширением схемы следует создать резервную копию состояния системы для контроллера домена, выполняющего роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="92479-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> <span data-ttu-id="92479-116">Описание процесса резервного копирования Windows Server 2008 R2 с пакетом обновления 1, в разделе [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span><span class="sxs-lookup"><span data-stu-id="92479-116">For details about the backup process for Windows Server 2008 R2 with SP1, see [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198).</span></span> <span data-ttu-id="92479-117">Windows Server 2003 и Windows Server 2003 R2, в разделе [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span><span class="sxs-lookup"><span data-stu-id="92479-117">For Windows Server 2003 and Windows Server 2003 R2, see [https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="92479-118">Расширение схемы необратимо.</span><span class="sxs-lookup"><span data-stu-id="92479-118">Extending the schema is not reversible.</span></span> <span data-ttu-id="92479-119">Необходимо приложить все усилия для успешного расширения схемы и ограничения возможных последствий в случае его сбоя.</span><span class="sxs-lookup"><span data-stu-id="92479-119">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="92479-120">Это особенно важно в случае потери связи или любого другого сбоя на сервере.</span><span class="sxs-lookup"><span data-stu-id="92479-120">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="92479-121">Необходимо выполнить полную резервную копию Active Directory и резервной копии хозяин схемы.</span><span class="sxs-lookup"><span data-stu-id="92479-121">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="92479-122">Для выполнения резервного копирования контроллер домена хозяина схемы и полную резервную копию Active Directory:</span><span class="sxs-lookup"><span data-stu-id="92479-122">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="92479-123">Отсоедините от сети контроллер домена, содержащий роль хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="92479-123">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="92479-124">Выполните резервное копирование состояния системы контроллера домена, содержащего хозяина схемы.</span><span class="sxs-lookup"><span data-stu-id="92479-124">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="92479-125">Выполните расширение схемы.</span><span class="sxs-lookup"><span data-stu-id="92479-125">Extend the schema.</span></span>
    
4. <span data-ttu-id="92479-126">Если расширение схемы прошло успешно, снова присоедините контроллер домена к сети и убедитесь, что репликация активна и работает.</span><span class="sxs-lookup"><span data-stu-id="92479-126">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="92479-127">Если вдруг расширение схемы во время сбоя восстановите состояние системы контроллера домена и Active Directory с помощью резервной копии состояния системы, сделанные в более ранних версий.</span><span class="sxs-lookup"><span data-stu-id="92479-127">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="92479-128">Если вам потребуется просмотрите файлы журнала, создаваемые с Скайп для мастер развертывания Business Server, можно найти файлы на компьютере, на котором запускался мастер развертывания в каталоге пользователей в Active Directory пользователя, выполнившего действие.</span><span class="sxs-lookup"><span data-stu-id="92479-128">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="92479-129">Например, если пользователь вошел в систему от имени администратора домена в домене Contoso.net, файлов журнала, находятся в: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="92479-129">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

