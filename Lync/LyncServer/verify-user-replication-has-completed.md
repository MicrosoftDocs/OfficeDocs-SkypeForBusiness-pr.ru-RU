---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="1dc8e-102">Проверка выполнения пользовательской репликации</span><span class="sxs-lookup"><span data-stu-id="1dc8e-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dc8e-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1dc8e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1dc8e-104">При запуске командлета **Move-CsUser** может возникнуть сбой из-за того, что сведения о пользователе между доменными службами Active Directory (AD DS) и базами данных Lync Server 2013 не синхронизованы, так как начальная репликация не завершена.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="1dc8e-105">Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="1dc8e-106">Начальная синхронизация службы репликатора пользователей Lync Server 2013 происходит при первом запуске сервера переднего плана Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="1dc8e-107">После этого синхронизация будет основана на интервале репликатора пользователей.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="1dc8e-108">Выполните описанные ниже действия, чтобы убедиться, что репликация пользователей завершилась, прежде чем запускать командлет **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="1dc8e-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="1dc8e-109">Проверка завершения репликации пользователя</span><span class="sxs-lookup"><span data-stu-id="1dc8e-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="1dc8e-110">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="1dc8e-111">Откройте меню **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="1dc8e-112">Введите **eventvwr. exe** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="1dc8e-113">В окне просмотра событий щелкните **журналы приложений и служб** , чтобы развернуть его, а затем выберите Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="1dc8e-114">В области **действия** щелкните **фильтр текущего журнала**.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="1dc8e-115">В списке **источники событий** выберите пункт **репликатор пользователей Ls**.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="1dc8e-116">Во \*\* \<всех кодах\> событий\*\* введите **30024** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="1dc8e-117">В списке отфильтрованных событий на вкладке **Общие** найдите запись, в которой указано, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="1dc8e-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

