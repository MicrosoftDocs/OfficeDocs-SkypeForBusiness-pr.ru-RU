---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: При запуске Move-CsUser может возникнуть сбой, так как сведения о пользователе между доменными службами Active Directory (AD DS) и базами данных Skype для бизнеса Server 2019 не синхронизируются, так как начальная репликация не завершена. Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Skype для бизнеса Server 2019, зависит от количества контроллеров домена, которые размещены в лесу Active Directory, в котором размещен пул Skype для бизнеса Server 2019. Начальная синхронизация службы репликатора пользовательских данных Skype для бизнеса Server 2019 происходит, когда сервер переднего интерфейса Skype для бизнеса Server 2019 впервые запущен. После этого синхронизация определяется интервалом репликации пользователей. Чтобы проверить, что репликация пользовательских данных завершена до запуска командлета Move-CsUser, выполните следующие действия.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751651"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="fde28-107">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="fde28-107">Verify user replication has completed</span></span>

<span data-ttu-id="fde28-108">При запуске cmdlet **Move-CsUser** может возникнуть сбой, если данные пользователя между доменными службами Active Directory (AD DS) и базами данных Skype для бизнеса Server 2019 не синхронизируются, так как начальная репликация не завершена.</span><span class="sxs-lookup"><span data-stu-id="fde28-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="fde28-109">Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Skype для бизнеса Server 2019, зависит от количества контроллеров домена, которые размещены в лесу Active Directory, в котором размещен пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fde28-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fde28-110">Начальная синхронизация службы репликатора пользовательских данных Skype для бизнеса Server 2019 происходит, когда сервер переднего интерфейса Skype для бизнеса Server 2019 впервые запущен.</span><span class="sxs-lookup"><span data-stu-id="fde28-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="fde28-111">После этого синхронизация будет основана на интервале репликатора пользователей.</span><span class="sxs-lookup"><span data-stu-id="fde28-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="fde28-112">Выполните следующие действия, чтобы убедиться, что репликация пользователей завершена, прежде чем запускать **cmdlet Move-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="fde28-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="fde28-113">Проверка завершения репликации пользователей</span><span class="sxs-lookup"><span data-stu-id="fde28-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="fde28-114">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fde28-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="fde28-115">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fde28-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="fde28-116">Введите **eventvwr.exe** и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="fde28-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="fde28-117">В окне  просмотра событий щелкните журналы приложений и служб, чтобы развернуть его, а затем выберите Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fde28-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="fde28-118">В области **действий** щелкните **"Фильтр текущего журнала".**</span><span class="sxs-lookup"><span data-stu-id="fde28-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="fde28-119">В списке **Источники событий** щелкните пункт **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="fde28-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="fde28-120">In **\<All Event IDs\>** , enter **30024**, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="fde28-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="fde28-121">В списке отфильтрованных событий на вкладке **"Общие"** найди запись, которая утверждает, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="fde28-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

