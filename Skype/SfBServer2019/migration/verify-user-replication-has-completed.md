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
description: При запуске командлета Move-CsUser может возникнуть сбой из-за того, что сведения о пользователях между доменными службами Active Directory (AD DS) и базами данных Skype для бизнеса Server 2019 не синхронизированы из-за неполной первоначальной репликации. Время, затраченное на успешное выполнение начальной синхронизации службы репликации пользователей Skype для бизнеса Server 2019, зависит от количества контроллеров домена, размещенных в лесу Active Directory, в котором размещается пул Skype для бизнеса Server 2019. Начальная синхронизация службы Replicator пользователей Skype для бизнеса Server 2019 происходит, когда сервер переднего плана Skype для бизнеса Server 2019 запускается в первый раз. После этого синхронизация определяется интервалом репликации пользователей. Чтобы проверить, что репликация пользовательских данных завершена до запуска командлета Move-CsUser, выполните следующие действия.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751651"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="2b037-107">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="2b037-107">Verify user replication has completed</span></span>

<span data-ttu-id="2b037-108">При запуске командлета **Move-CsUser** может возникнуть сбой, если данные пользователя между доменными службами Active Directory (AD DS) и базами данных Skype для бизнеса Server 2019 не синхронизированы из-за неполной первоначальной репликации.</span><span class="sxs-lookup"><span data-stu-id="2b037-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="2b037-109">Время, затраченное на успешное выполнение начальной синхронизации службы репликации пользователей Skype для бизнеса Server 2019, зависит от количества контроллеров домена, размещенных в лесу Active Directory, в котором размещается пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2b037-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2b037-110">Начальная синхронизация службы Replicator пользователей Skype для бизнеса Server 2019 происходит, когда сервер переднего плана Skype для бизнеса Server 2019 запускается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="2b037-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="2b037-111">После этого синхронизация основывается на интервале репликатора пользователей.</span><span class="sxs-lookup"><span data-stu-id="2b037-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="2b037-112">Выполните следующие действия, чтобы убедиться, что репликация пользователя завершена перед выполнением командлета **Move – CsUser** .</span><span class="sxs-lookup"><span data-stu-id="2b037-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="2b037-113">Проверка завершения репликации пользователей</span><span class="sxs-lookup"><span data-stu-id="2b037-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="2b037-114">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2b037-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="2b037-115">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2b037-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="2b037-116">Введите **eventvwr.exe**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2b037-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="2b037-117">В средстве просмотра событий щелкните **журналы приложений и служб** , чтобы развернуть его, а затем выберите Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2b037-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="2b037-118">В области **действия** щелкните **Фильтровать текущий журнал**.</span><span class="sxs-lookup"><span data-stu-id="2b037-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="2b037-119">В списке **Источники событий** щелкните пункт **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="2b037-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="2b037-120">В **\<All Event IDs\>** введите **30024**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2b037-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="2b037-121">В списке отфильтрованные события на вкладке **Общие** найдите запись о том, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="2b037-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

