---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: При запуске командлета Move-CsUser может возникнуть сбой из-за того, что сведения о пользователях между доменными службами Active Directory (AD DS) и базами данных Skype для бизнеса Server 2019 не синхронизованы, так как начальная репликация не завершена. Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Skype для бизнеса Server 2019, зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается Skype для бизнеса. Пул серверов 2019. Начальная синхронизация службы репликатора пользователей в Skype для бизнеса Server 2019 происходит, когда сервер клиентского доступа Skype для бизнеса Server 2019 запускается в первый раз. После этого синхронизация будет основана на интервале репликатора пользователей. Выполните описанные ниже действия, чтобы убедиться, что репликация пользователей завершилась, прежде чем запускать командлет Move-CsUser.
ms.openlocfilehash: 12bb3c29f703287934358f331dc945830e318afb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243713"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="ddc9a-107">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="ddc9a-107">Verify user replication has completed</span></span>

<span data-ttu-id="ddc9a-108">При запуске командлета **Move-CsUser** может возникнуть сбой в случае, если сведения о пользователе между доменными службами Active Directory (AD DS) и базой данных Skype для бизнеса Server 2019 не синхронизованы, так как начальная репликация не завершена.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="ddc9a-109">Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Skype для бизнеса Server 2019, зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается Skype для бизнеса. Пул серверов 2019.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ddc9a-110">Начальная синхронизация службы репликатора пользователей в Skype для бизнеса Server 2019 происходит, когда сервер клиентского доступа Skype для бизнеса Server 2019 запускается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="ddc9a-111">После этого синхронизация будет основываться на интервале репликатора пользователей.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="ddc9a-112">Выполните описанные ниже действия, чтобы убедиться, что репликация пользователя завершена до запуска командлета **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="ddc9a-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="ddc9a-113">Проверка завершения репликации пользователя</span><span class="sxs-lookup"><span data-stu-id="ddc9a-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="ddc9a-114">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ddc9a-115">Откройте меню **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="ddc9a-116">Введите **eventvwr. exe**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="ddc9a-117">В окне просмотра событий щелкните **журналы приложений и служб** , чтобы развернуть его, а затем выберите Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="ddc9a-118">В области **действия** щелкните **фильтр текущего журнала**.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="ddc9a-119">В списке **источники событий** выберите пункт **репликатор пользователей Ls**.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="ddc9a-120">Во \*\* \<всех кодах\>событий\*\*введите **30024**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="ddc9a-121">В списке фильтрованных событий на вкладке **Общие** найдите запись о том, что репликация пользователей выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="ddc9a-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

