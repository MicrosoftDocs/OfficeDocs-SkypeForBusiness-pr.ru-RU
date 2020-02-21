---
title: Проверка того, что репликация пользователя завершена
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96e8df3cb77e6b53596ae17e15fed6b05243a99a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="a904a-102">Проверка того, что репликация пользователя завершена</span><span class="sxs-lookup"><span data-stu-id="a904a-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a904a-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a904a-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a904a-104">При запуске командлета **Move-CsUser** может возникать сбой из-за того, что сведения о пользователях между доменными службами Active Directory (AD DS) и базами данных Lync Server 2013 не синхронизируются из-за того, что начальная репликация не завершена.</span><span class="sxs-lookup"><span data-stu-id="a904a-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="a904a-105">Время, необходимое для успешного завершения начальной синхронизации службы Replicator для Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, в котором размещается пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a904a-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="a904a-106">При первом запуске сервера переднего плана Lync Server 2013 выполняется начальная синхронизация службы Replicator пользователя Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a904a-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="a904a-107">После этого синхронизация выполняется с интервалом репликатора пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="a904a-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="a904a-108">Чтобы проверить, что репликация пользовательских данных завершена до запуска командлета **Move-CsUser**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a904a-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="a904a-109">Чтобы проверить, что репликация пользовательских данных завершена</span><span class="sxs-lookup"><span data-stu-id="a904a-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="a904a-110">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a904a-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="a904a-111">Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a904a-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="a904a-112">Введите **eventvwr.exe**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a904a-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="a904a-113">В окне просмотра событий щелкните **Журналы приложений и служб**, чтобы развернуть окно, а затем выберите "Lync Server".</span><span class="sxs-lookup"><span data-stu-id="a904a-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="a904a-114">В области **Действия** щелкните пункт **Фильтровать текущий журнал**.</span><span class="sxs-lookup"><span data-stu-id="a904a-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="a904a-115">В списке **Источники событий** щелкните пункт **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="a904a-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="a904a-116">Во \*\* \<всех идентификаторах\> событий\*\* введите **30024** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a904a-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="a904a-117">В фильтрованном списке событий перейдите на вкладку **Общие** и найдите запись, указывающую, что репликация пользователей успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="a904a-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

