---
title: Lync Server 2013 пользовательский интерфейс при отказе пула
description: Lync Server 2013 пользовательский интерфейс при отказе пула.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0483a01b643d8195e7f8f6259c11ab6fc3561f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569795"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="bec6e-103">Взаимодействие с пользователем при отказе пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec6e-103">User experience during pool failure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bec6e-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="bec6e-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="bec6e-105">В случае отработки отказа пула все пользователи этого пула принудительно выходят из него и затем выполняют вход в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="bec6e-105">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="bec6e-106">В течение непродолжительного периода времени пользователи, выполнившие вход в резервный пул, могут находиться в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-106">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="bec6e-107">В режиме устойчивости пользователи не могут выполнять задачи, которые приводили к сохранению изменений в Lync Server, например добавление контакта.</span><span class="sxs-lookup"><span data-stu-id="bec6e-107">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="bec6e-108">После завершения отработки отказа все пользователи могут использовать любые службы резервного пула.</span><span class="sxs-lookup"><span data-stu-id="bec6e-108">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="bec6e-109">При сбое пула все сеансы пользователя прерываются. Чтобы продолжить, пользователю потребуется повторно создать сеансы после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="bec6e-109">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="bec6e-p102">В ходе отработки отказа или восстановления размещения пользователи не перемещаются. Пользователи, размещенные в сбойном пуле, временно обслуживаются резервным пулом. После восстановления исходного пула пользователи будут переведены на обслуживание исходным пулом.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="bec6e-113">Примечание в Lync 2013 база данных сервера сведений о расположениях не реплицируется в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="bec6e-113">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="bec6e-114">Администратору рекомендуется регулярно создавать резервные копии базы данных сервера информирования о местонахождении и использовать последнюю резервную копию для восстановления базы данных сервера в резервном пуле после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="bec6e-114">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="bec6e-115">Взаимодействие с пользователями в ходе отработки отказа</span><span class="sxs-lookup"><span data-stu-id="bec6e-115">User Experience During Failover</span></span>

<span data-ttu-id="bec6e-p104">Если пользователь находится в пуле, на котором произошел сбой, пользователь выходит из системы. Все одноранговые сеансы, в которых принимал участие пользователь, будут приостановлены, включая конференции, созданные пользователем. Пользователь не сможет выполнить вход до тех пор, пока не истечет время ожидания таймера устойчивости Регистратора или администратор не начнет процедуры аварийного восстановления, независимо от того, что произойдет раньше. Следующий вход пользователя будет осуществляться на резервном пуле. Если вход выполнен до завершения отработки отказа, то пользователи будут находиться в режиме устойчивости до завершения отработки отказа. После завершения отработки отказа пользователи смогут создать новые сеансы или восстановить предыдущие сеансы.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="bec6e-121">Взаимодействие с пользователями в ходе восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="bec6e-121">User Experience During Failback</span></span>

<span data-ttu-id="bec6e-p105">Восстановление размещения может быть выполнено в то время, как затронутый пользователь выполнил вход в резервный пул. В ходе восстановления размещения пользователь остается в системе резервного пула и может продолжить работу. Обратите внимание на то, что на восстановление размещения требуется несколько минут. Так, для пула с 20 000 пользователей оно занимает приблизительно 60 минут.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="bec6e-125">В следующих таблицах представлены дополнительные сведения о том, как пользователи, работающие с клиентами Lync 2013 и Microsoft Lync 2010, затрагиваются во время и после восстановления размещения, а также в том, как пользователи из других пулов видят и взаимодействуют с пользователем в пуле, который не прошел обратно.</span><span class="sxs-lookup"><span data-stu-id="bec6e-125">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="bec6e-126">Пользователи с Microsoft Office Communicator 2007 R2 не могут войти в систему до полного сбоя фонового пула.)</span><span class="sxs-lookup"><span data-stu-id="bec6e-126">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="bec6e-p107">Термин *затронутый пользователь* относится к любому пользователю, который был переведен из основного пула и обслуживается резервным пулом. По определению пользователь, который изначально находился на резервном пуле, не является затронутым пользователем.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="bec6e-129">Взаимодействие с затронутым пользователем пула в ходе восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="bec6e-129">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec6e-130">Состояние пользователя или задача</span><span class="sxs-lookup"><span data-stu-id="bec6e-130">User state or task</span></span></th>
<th><span data-ttu-id="bec6e-131">В ходе восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="bec6e-131">During failback</span></span></th>
<th><span data-ttu-id="bec6e-132">После завершения восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="bec6e-132">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec6e-133">Состояние пользователя, который уже выполнил вход</span><span class="sxs-lookup"><span data-stu-id="bec6e-133">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="bec6e-p108">Пользователь остается подключенным к резервному пулу. В определенный момент времени пользователь выйдет из системы и затем снова выполнит вход на исходном пуле в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-136">Состояние входа пользователя не изменяется и он переходит в обычный режим.</span><span class="sxs-lookup"><span data-stu-id="bec6e-136">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec6e-137">Вход нового пользователя</span><span class="sxs-lookup"><span data-stu-id="bec6e-137">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="bec6e-138">Пользователь может выполнить вход в пул в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-138">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-139">Пользователь может выполнить вход в исходный пул в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="bec6e-139">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec6e-140">Текущие конференции, созданные затронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="bec6e-140">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="bec6e-p109">Все модальности конференции приостанавливаются. Кнопка "Повторно присоединиться" будет отображаться, но ни один пользователь не сможет присоединиться повторно, если затронутый пользователь находится в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-p110">Все модальности работают. Для повторного присоединения к конференции участникам требуется нажать кнопку "Повторно присоединиться".</span><span class="sxs-lookup"><span data-stu-id="bec6e-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec6e-145">Текущие конференции, созданные незатронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="bec6e-145">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="bec6e-p111">Конференция будет продолжена и затронутый пользователь останется подключенным к конференции. Возможности затронутого пользователя в режиме устойчивости ограничены.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-148">Конференция будет продолжена, затронутый пользователь останется подключенным к конференции, а все модальности начнут работу после выхода из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-148">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec6e-149">Создание расписания и изменение запланированных собраний, создание запланированных конференций</span><span class="sxs-lookup"><span data-stu-id="bec6e-149">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="bec6e-150">Невозможно в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-150">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-151">Доступно для всех модальностей.</span><span class="sxs-lookup"><span data-stu-id="bec6e-151">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec6e-152">Сведения о присутствии, отображаемые остальным пользователям того же пула</span><span class="sxs-lookup"><span data-stu-id="bec6e-152">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="bec6e-153">Сведения о присутствии отсутствуют, если пользователь выполнил вход в резервный пул в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="bec6e-153">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-154">Отображается последнее состояние присутствия, заданное пользователем, при этом изменения состояния присутствия не отображаются.</span><span class="sxs-lookup"><span data-stu-id="bec6e-154">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec6e-155">Доступность списка контактов и службы адресной книги</span><span class="sxs-lookup"><span data-stu-id="bec6e-155">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="bec6e-156">Недоступно</span><span class="sxs-lookup"><span data-stu-id="bec6e-156">Not available</span></span></p></td>
<td><p><span data-ttu-id="bec6e-157">Available</span><span class="sxs-lookup"><span data-stu-id="bec6e-157">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec6e-158">Все одноранговые сеансы и модальности</span><span class="sxs-lookup"><span data-stu-id="bec6e-158">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="bec6e-159">Available</span><span class="sxs-lookup"><span data-stu-id="bec6e-159">Available</span></span></p></td>
<td><p><span data-ttu-id="bec6e-160">Available</span><span class="sxs-lookup"><span data-stu-id="bec6e-160">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="bec6e-161">Взаимодействие с пользователями, размещенными в незатронутом пуле, в ходе восстановления размещения другого пула</span><span class="sxs-lookup"><span data-stu-id="bec6e-161">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec6e-162">Задача пользователя</span><span class="sxs-lookup"><span data-stu-id="bec6e-162">User task</span></span></th>
<th><span data-ttu-id="bec6e-163">В ходе восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="bec6e-163">During failback</span></span></th>
<th><span data-ttu-id="bec6e-164">После завершения восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="bec6e-164">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec6e-165">Просмотр сведений о присутствии затронутого пользователя</span><span class="sxs-lookup"><span data-stu-id="bec6e-165">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="bec6e-166">Отображается последнее состояние присутствия, заданное затронутым пользователем.</span><span class="sxs-lookup"><span data-stu-id="bec6e-166">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-p112">Незатронутые пользователи могут просматривать обновленные сведения о присутствии затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="bec6e-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec6e-169">Текущие конференции, созданные затронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="bec6e-169">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="bec6e-170">Все модальности конференции приостанавливаются.</span><span class="sxs-lookup"><span data-stu-id="bec6e-170">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-p113">Все модальности работают. Для повторного присоединения к конференции участникам требуется нажать кнопку "Повторно присоединиться".</span><span class="sxs-lookup"><span data-stu-id="bec6e-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec6e-173">Текущие конференции, созданные незатронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="bec6e-173">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="bec6e-174">Конференция будет продолжена, затронутый пользователь может остаться в конференции и все модальности будут работать.</span><span class="sxs-lookup"><span data-stu-id="bec6e-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="bec6e-175">Конференция будет продолжена, затронутый пользователь может остаться в конференции и все модальности будут работать.</span><span class="sxs-lookup"><span data-stu-id="bec6e-175">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec6e-176">Все одноранговые сеансы и модальности</span><span class="sxs-lookup"><span data-stu-id="bec6e-176">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="bec6e-177">Available</span><span class="sxs-lookup"><span data-stu-id="bec6e-177">Available</span></span></p></td>
<td><p><span data-ttu-id="bec6e-178">Available</span><span class="sxs-lookup"><span data-stu-id="bec6e-178">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

