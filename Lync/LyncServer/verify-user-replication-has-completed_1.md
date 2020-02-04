---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="fa154-102">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="fa154-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa154-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fa154-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fa154-104">При запуске командлета **Move-кслегациусер** может возникнуть сбой из-за сведений о пользователях в доменных службах Active Directory (AD DS) и баз данных Lync Server 2013, так как начальная репликация не завершена.</span><span class="sxs-lookup"><span data-stu-id="fa154-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="fa154-105">Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa154-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="fa154-106">Начальная синхронизация службы репликатора пользователей Lync Server 2013 происходит при первом запуске сервера переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa154-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="fa154-107">После этого синхронизация будет основана на интервале репликатора пользователей.</span><span class="sxs-lookup"><span data-stu-id="fa154-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="fa154-108">Выполните описанные ниже действия, чтобы убедиться, что репликация пользователей завершилась, прежде чем запускать командлет **Move-кслегациусер** .</span><span class="sxs-lookup"><span data-stu-id="fa154-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="fa154-109">Проверка завершения репликации пользователя</span><span class="sxs-lookup"><span data-stu-id="fa154-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="fa154-110">На сервере переднего плана Lync Server 2013 откройте меню **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="fa154-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="fa154-111">Введите **eventvwr. exe** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa154-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="fa154-112">В окне просмотра событий щелкните **журналы приложений и служб** , чтобы развернуть его, а затем выберите Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa154-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="fa154-113">В области **действия** щелкните **фильтр текущего журнала**.</span><span class="sxs-lookup"><span data-stu-id="fa154-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="fa154-114">В списке **источники событий** выберите пункт **репликатор пользователей Ls**.</span><span class="sxs-lookup"><span data-stu-id="fa154-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="fa154-115">Во \*\* \<всех кодах\> событий\*\* введите **30024** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa154-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="fa154-116">В списке отфильтрованных событий на вкладке **Общие** найдите запись, в которой указано, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="fa154-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

