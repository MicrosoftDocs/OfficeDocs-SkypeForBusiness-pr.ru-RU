---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: При выполнении командлета Move-CsUser может произойдет сбой, так как данные пользователей между доменных служб Active Directory (AD DS) и Скайп Business Server 2019 баз данных не синхронизированы, из-за неполной первоначальной репликации. Время, необходимое для успешного завершения установки Скайп для начальной синхронизации службы Репликатор пользователей 2019 Business Server зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается Скайп для бизнеса Пул серверов 2019. Скайп для начальной синхронизации службы Репликатор пользователей 2019 Business Server процесса происходит при запуске Скайп для сервера переднего плана Business Server 2019 в первый раз. После этого синхронизации нажмите основано на интервал репликатора пользовательских данных. Выполните следующие действия, чтобы проверка пользовательской репликации выполнена перед запуском командлета Move-CsUser.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889510"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="4178a-107">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="4178a-107">Verify user replication has completed</span></span>

<span data-ttu-id="4178a-108">При выполнении командлета **Move-CsUser** может произойдет сбой, если данные пользователей между доменных служб Active Directory (AD DS) и Скайп Business Server 2019 баз данных не синхронизированы, из-за неполной первоначальной репликации.</span><span class="sxs-lookup"><span data-stu-id="4178a-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="4178a-109">Время, необходимое для успешного завершения установки Скайп для начальной синхронизации службы Репликатор пользователей 2019 Business Server зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается Скайп для бизнеса Пул серверов 2019.</span><span class="sxs-lookup"><span data-stu-id="4178a-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="4178a-110">Скайп для начальной синхронизации службы Репликатор пользователей 2019 Business Server процесса происходит при запуске Скайп для сервера переднего плана Business Server 2019 в первый раз.</span><span class="sxs-lookup"><span data-stu-id="4178a-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="4178a-111">После этого синхронизация выполняется на основе интервала репликатора пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="4178a-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="4178a-112">Выполните следующие действия, чтобы убедиться, что завершения репликации пользователей перед запуском командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="4178a-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="4178a-113">Чтобы убедиться, что завершения репликации пользователей</span><span class="sxs-lookup"><span data-stu-id="4178a-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="4178a-114">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4178a-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="4178a-115">В меню **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4178a-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="4178a-116">Введите **eventvwr.exe**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4178a-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="4178a-117">В окне просмотра событий щелкните **Журналы приложений и служб** , чтобы развернуть его и выберите Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="4178a-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="4178a-118">В области **действия** выберите **Фильтровать текущий журнал**.</span><span class="sxs-lookup"><span data-stu-id="4178a-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="4178a-119">В списке **Источники событий** щелкните **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="4178a-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="4178a-120">В \*\* \<все идентификаторы событий\>\*\*, введите **30024**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4178a-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="4178a-121">В фильтрованном списке событий перейдите на вкладку **Общие** найдите запись о том, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="4178a-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

