---
title: 'Lync Server 2013: откат перенесенных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8b8c53f835bbbaa363a91ef547dd1d301c8976
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="d5493-102">Откат перенесенных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5493-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5493-103">_**Тема последнего изменения:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="d5493-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="d5493-104">Если вы хотите выполнить откат в едином хранилище контактов, изменяйте контакты только в том случае, если вы вернете пользователя на Exchange 2010 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d5493-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="d5493-105">Чтобы выполнить откат, отключите политику для пользователя, а затем выполните командлет **Invoke-ксуксроллбакк** .</span><span class="sxs-lookup"><span data-stu-id="d5493-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="d5493-106">Просто запустить функцию **Invoke-ксуксроллбакк** недостаточно для обеспечения постоянной процедуры отката, так как единая миграция хранилища контактов инициируется повторно, если она не отключена.</span><span class="sxs-lookup"><span data-stu-id="d5493-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="d5493-107">Например, если пользователь выполняет откат, так как Exchange 2013 возвращается в Exchange 2010, а почтовый ящик пользователя перемещается в Exchange 2013, то единая миграция в магазине контактов начнется еще раз через семь дней после отката, пока единая база данных контактов по-прежнему включен для пользователя в политике служб пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5493-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5493-108">Командлет <STRONG>Move-CsUser</STRONG> автоматически откатывает хранилище контактов пользователя Exchange 2013 на Lync Server 2013 в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="d5493-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d5493-109">При перемещении пользователей из Lync Server 2013 в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d5493-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="d5493-110">Если миграция пользователей осуществляется между организациями, например, когда пользователь перемещается из Lync Online в Lync Server 2013 в локальной среде или наоборот.</span><span class="sxs-lookup"><span data-stu-id="d5493-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5493-111">Импорт данных из хранилища Объединенных контактов из резервной базы данных может привести к повреждению данных из хранилища контактов и данных пользователя, если в процессе экспорта и импорта изменился режим хранилища единого контакта.</span><span class="sxs-lookup"><span data-stu-id="d5493-111">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="d5493-112">Например:</span><span class="sxs-lookup"><span data-stu-id="d5493-112">For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d5493-113">Если вы экспортируете списки контактов перед тем, как контакты пользователей будут перенесены в Exchange 2013, а затем, после миграции, импортируйте эти данные в единое хранилище контактов и списки контактов, которые будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="d5493-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="d5493-114">Если вы экспортируете учетные данные после миграции пользователей в Exchange 2013, откати миграции, а также по какой – либо причине импорт данных из нее после миграции, данные в едином хранилище контактов и списки контактов будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="d5493-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5493-115">Перед перемещением почтового ящика Exchange из Exchange 2013 в Exchange 2010 администратор Exchange должен удостовериться, что администратор сервера Lync Server отключил контакты пользователей Lync Server с Exchange 2013 на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5493-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="d5493-116">Чтобы вернуть контакты из хранилища Объединенных контактов в Lync Server, ознакомьтесь с процедурой "откатить контакты из хранилища контактов из Exchange 2013 на Lync Server 2013" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d5493-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="d5493-117">Ниже описана процедура отката контактов пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5493-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="d5493-118">Если вы используете командлет **Move-CsUser** для перемещения пользователей между lync Server 2013 и Lync Server 2010, вы можете пропустить эти действия, так как командлет **Move-CsUser** автоматически откатывает унифед Store Contact при перемещении пользователей с Lync Server 2013 на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d5493-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="d5493-119">В разделе **Move-CsUser** не отключена политика хранилища контактов, поэтому миграция в единое хранилище контактов будет повторяться, если пользователь перейдет на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5493-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="d5493-120">Откат контактов пользователей из Lync Server 2013 и Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d5493-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="d5493-121">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d5493-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5493-122">Отключите единое хранилище контактов, чтобы пользователи могли выполнить откат, чтобы они не были повторно перенесены после отката.</span><span class="sxs-lookup"><span data-stu-id="d5493-122">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="d5493-123">(Выполните это действие только в том случае, если вы хотите убедиться, что пользователи не будут переноситься в будущем.) Чтобы отключить единое хранилище контактов для отдельных пользователей, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="d5493-123">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="d5493-124">Например:</span><span class="sxs-lookup"><span data-stu-id="d5493-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="d5493-125">Перед перемещением пользователя из Lync Server 2013 в Lync Server 2010 верните список контактов для указанных пользователей на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5493-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5493-126">Если это действие не задано, список собеседников будет потерян.</span><span class="sxs-lookup"><span data-stu-id="d5493-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="d5493-127">Выполнять откат указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5493-127">Roll back the specified users.</span></span> <span data-ttu-id="d5493-128">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d5493-128">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="d5493-129">Например:</span><span class="sxs-lookup"><span data-stu-id="d5493-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5493-130">Мы не рекомендуем использовать параметр – Force для принудительного отката.</span><span class="sxs-lookup"><span data-stu-id="d5493-130">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="d5493-131">Если вы используете этот параметр, контакты пользователей будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="d5493-131">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="d5493-132">Откат Объединенных Объединенных контактов из Exchange 2013 на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5493-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="d5493-133">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d5493-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d5493-134">Отключите единое хранилище контактов, чтобы пользователи могли выполнить откат, чтобы они не были повторно перенесены после отката.</span><span class="sxs-lookup"><span data-stu-id="d5493-134">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="d5493-135">Чтобы отключить единое хранилище контактов для отдельных пользователей, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="d5493-135">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="d5493-136">Например:</span><span class="sxs-lookup"><span data-stu-id="d5493-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="d5493-137">Выполнять откат указанных пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5493-137">Roll back the specified users.</span></span> <span data-ttu-id="d5493-138">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d5493-138">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="d5493-139">Например:</span><span class="sxs-lookup"><span data-stu-id="d5493-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5493-140">Сначала необходимо выполнить откат пользователя Lync Server, а затем переместить почтовый ящик Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d5493-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="d5493-141">Администратор Exchange блокирует переход на Exchange, пока не завершится откат сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5493-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="d5493-142">Мы не рекомендуем использовать параметр – Force для принудительного отката.</span><span class="sxs-lookup"><span data-stu-id="d5493-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="d5493-143">Если вы используете этот параметр, контакты пользователей будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="d5493-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="d5493-144">После того как вы перейдете на сервер Lync Server, администратор Exchange может восстановить пользователя Exchange из Exchange 2013 в Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="d5493-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

