---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bed57b6e24db0ba6f75e323fe311aa4aaf262c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="8b6ff-102">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="8b6ff-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b6ff-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8b6ff-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8b6ff-104">При запуске командлета **Move-CsLegacyUser** могут возникать сбои из-за сведений о пользователях между доменными службами Active Directory (AD DS) и базами данных Lync Server 2013, так как начальная репликация не завершена.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="8b6ff-105">Время, необходимое для успешного завершения начальной синхронизации службы Replicator для Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, в котором размещается пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="8b6ff-106">При первом запуске сервера переднего плана Lync Server 2013 выполняется начальная синхронизация службы Replicator пользователя Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="8b6ff-107">После этого синхронизация определяется интервалом репликации пользователей.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="8b6ff-108">Выполните следующие действия, чтобы проверить завершение репликации пользователей перед выполнением командлета **Move-CsLegacyUser**.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="8b6ff-109">Проверка завершения репликации пользователей</span><span class="sxs-lookup"><span data-stu-id="8b6ff-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="8b6ff-110">На сервере переднего плана Lync Server 2013 откройте меню **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="8b6ff-111">Введите **eventvwr.exe**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="8b6ff-112">В окне просмотра событий щелкните **Журналы приложений и служб**, чтобы развернуть окно, а затем выберите "Lync Server".</span><span class="sxs-lookup"><span data-stu-id="8b6ff-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="8b6ff-113">В области **Действия** щелкните пункт **Фильтровать текущий журнал**.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="8b6ff-114">В списке **Источники событий** щелкните пункт **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="8b6ff-115">В **\<All Event IDs\>** поле введите **30024** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="8b6ff-116">В фильтрованном списке событий перейдите на вкладку **Общие** и найдите запись, указывающую, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="8b6ff-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

