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
ms.openlocfilehash: 05678690718563dac9187ee275d3809016b78d33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="bf0de-102">Откат перенесенных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf0de-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf0de-103">_**Последнее изменение темы:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="bf0de-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="bf0de-104">Если необходимо выполнить откат единой системы хранения контактов, выполните откат контактов только в том случае, если пользователь перемещается обратно в Exchange 2010 или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf0de-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="bf0de-105">Для выполнении отката отключите политику для пользователя, а затем выполните командлет **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="bf0de-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="bf0de-106">Выполнения одного командлета **Invoke-CsUcsRollback**недостаточно для обеспечения постоянного отката, поскольку если политика не отключена, то миграция универсального хранилища контактов будет инициирована повторно.</span><span class="sxs-lookup"><span data-stu-id="bf0de-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="bf0de-107">Например, если выполняется откат пользователя, так как сервер Exchange 2013 возвращается в Exchange 2010, а затем почтовый ящик пользователя перемещается в Exchange 2013, то процесс миграции единого хранилища контактов будет начат за семь дней после отката до тех пор, пока единое хранилище контактов все еще включено для пользователя в политике служб пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf0de-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bf0de-108">Командлет <STRONG>Move – CsUser</STRONG> автоматически выполняет откат хранилища контактов пользователя из Exchange 2013 к Lync Server 2013 в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="bf0de-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bf0de-109">При перемещении пользователей из Lync Server 2013 в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf0de-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="bf0de-110">При переносе локальных пользователей, например, когда пользователь перемещается из Lync Online в локальную среду Lync Server 2013 или наоборот.</span><span class="sxs-lookup"><span data-stu-id="bf0de-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bf0de-p102">Импорт данных универсального хранилища контактов из резервной копии базы данных может привести к повреждению данных универсального хранилища контактов и пользовательских данных, если режим универсального хранилища контактов изменится с экспорта на импорт. Пример:</span><span class="sxs-lookup"><span data-stu-id="bf0de-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bf0de-113">Если вы экспортируете списки контактов перед тем, как контакты пользователей будут перенесены в Exchange 2013, а затем, после миграции, будут повреждены данные и списки контактов в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="bf0de-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="bf0de-114">Если вы экспортируете данные о проходе после миграции пользователей в Exchange 2013, выполните откат миграции, а затем по каким – либо причинам вы импортируете данные из после миграции, данные в едином хранилище контактов и списки контактов будут повреждены.</span><span class="sxs-lookup"><span data-stu-id="bf0de-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bf0de-115">Перед перемещением почтового ящика Exchange из Exchange 2013 в Exchange 2010 администратор Exchange должен убедиться в том, что администратор сервера Lync Server выполнил откат контактов пользователя Lync Server из Exchange 2013 в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf0de-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="bf0de-116">Чтобы откатить контакты универсального хранилища контактов в Lync Server, ознакомьтесь с разделом "откатить контакты универсального хранилища контактов из Exchange 2013 в Lync Server 2013" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bf0de-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="bf0de-117">В следующей процедуре описывается откат контактов пользователей.</span><span class="sxs-lookup"><span data-stu-id="bf0de-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="bf0de-118">Если вы используете командлет **Move-CsUser** для перемещения пользователей между lync Server 2013 и Lync Server 2010, вы можете пропустить эти действия, так как командлет **Move-CsUser** автоматически выполняет откат хранилища контактов унифед при перемещении пользователей из Lync Server 2013 в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf0de-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="bf0de-119">**Move-CsUser** не отключает политику универсального хранилища контактов, поэтому миграция в единое хранилище контактов повторяется, если пользователь перемещается обратно в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf0de-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="bf0de-120">Откат контактов пользователей с Lync Server 2013 до Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bf0de-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="bf0de-121">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf0de-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bf0de-p105">Чтобы предотвратить повторную миграцию после отката, отключите универсальное хранилище контактов для пользователей, к которым применяется операция отката. (Выполните это действие только в том случае, если хотите убедиться, что в будущем не будет выполнена повторная миграция пользователей.) Чтобы отключить универсальное хранилище контактов для отдельных пользователей, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bf0de-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="bf0de-124">Например:</span><span class="sxs-lookup"><span data-stu-id="bf0de-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="bf0de-125">Перед перемещением пользователя из Lync Server 2013 в Lync Server 2010 выполните откат списка контактов для указанных пользователей на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf0de-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf0de-126">Если этот шаг пропущен, список собеседников будет утерян.</span><span class="sxs-lookup"><span data-stu-id="bf0de-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="bf0de-p106">Выполните откат требуемых пользователей. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="bf0de-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="bf0de-129">Например:</span><span class="sxs-lookup"><span data-stu-id="bf0de-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf0de-p107">Не рекомендуется использовать параметр –Force для принудительного отката. При использовании этого параметра контакты пользователей будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="bf0de-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="bf0de-132">Откат контактов универсального хранилища контактов из Exchange 2013 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf0de-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="bf0de-133">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf0de-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bf0de-p108">Чтобы предотвратить повторную миграцию после отката, отключите универсальное хранилище контактов для пользователей, к которым применяется операция отката. Чтобы отключить универсальное хранилище контактов для отдельных пользователей, введите в командной строке следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="bf0de-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="bf0de-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="bf0de-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="bf0de-p109">Выполните откат требуемых пользователей. В командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="bf0de-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="bf0de-139">Например:</span><span class="sxs-lookup"><span data-stu-id="bf0de-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bf0de-140">Необходимо сначала вернуть пользователя Lync Server, а затем переместить почтовый ящик Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="bf0de-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="bf0de-141">Администратор Exchange блокирует откат Exchange до завершения отката Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf0de-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="bf0de-142">Не рекомендуется использовать параметр Force для выполнения принудительного отката.</span><span class="sxs-lookup"><span data-stu-id="bf0de-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="bf0de-143">При использовании этого параметра контакты пользователей будут утеряны.</span><span class="sxs-lookup"><span data-stu-id="bf0de-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="bf0de-144">После отката пользователя до Lync Server администратор Exchange может выполнить откат пользователя Exchange с Exchange 2013 на сервер Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="bf0de-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

