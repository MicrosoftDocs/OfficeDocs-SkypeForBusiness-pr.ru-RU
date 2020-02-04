---
title: Пользовательский интерфейс Lync Server 2013 в случае сбоя пула
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
ms.openlocfilehash: 2e6506ac67415ca19b33ee968d698d0ed574df8d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="37802-102">Взаимодействие с пользователем во время сбоя пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37802-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37802-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="37802-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="37802-104">Если вы перейдете из-за сбоя пула, все пользователи этого пула будут вынуждены выйти из нее, а затем войти в пул резервной копии.</span><span class="sxs-lookup"><span data-stu-id="37802-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="37802-105">В течение непродолжительного периода времени пользователи, вошедшие в резервный пул, могут находиться в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="37802-106">В режиме устойчивости пользователи не могут выполнять задачи, которые приводили к сохранению изменений на сервере Lync Server, например добавление контакта.</span><span class="sxs-lookup"><span data-stu-id="37802-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="37802-107">По завершении отработки отказа возможно полное обслуживание всех пользователей из резервного пула.</span><span class="sxs-lookup"><span data-stu-id="37802-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="37802-108">Любые сеансы, которые пользователь может вызвать, когда происходит сбой пула, и пользователь должен повторно установить эти сеансы после перемещения, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="37802-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="37802-109">При отработке отказа или переключении на основной ресурс пользователи не перемещаются.</span><span class="sxs-lookup"><span data-stu-id="37802-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="37802-110">Пользователи, размещенные в сбойном пуле, временно обслуживаются из резервного пула.</span><span class="sxs-lookup"><span data-stu-id="37802-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="37802-111">После восстановления пула домашних компьютеров администратор может не отменять эти пользователи на обслуживание первоначального пула домашних компьютеров.</span><span class="sxs-lookup"><span data-stu-id="37802-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="37802-112">Обратите внимание, что в Lync 2013 база данных сервера сведений о расположениях не реплицируется в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="37802-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="37802-113">Администратору рекомендуется регулярно создавать резервные копии базы данных сервера информирования о местонахождении и после отработки отказа восстанавливать базу данных этого сервера из последней резервную копии в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="37802-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="37802-114">Взаимодействие с пользователем во время перехода на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="37802-114">User Experience During Failover</span></span>

<span data-ttu-id="37802-115">Если пользователь в пуле не проходит, пользователь выходит из него. Любые одноранговые сеансы, в которых участвует пользователь, прекращаются, как и конференции, упорядоченные этим пользователем.</span><span class="sxs-lookup"><span data-stu-id="37802-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="37802-116">Пользователь может войти снова только после срабатывания таймера регистрации устойчивости или запуска процедуры отработки отказа администратором в зависимости от того, что произойдет раньше.</span><span class="sxs-lookup"><span data-stu-id="37802-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="37802-117">Следующий вход пользователя осуществляется в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="37802-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="37802-118">Пользователь, вошедший во время отработки отказа или ранее, до ее завершения находится в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="37802-119">Только после этого пользователь сможет устанавливать новые сеансы или повторно устанавливать предыдущие сеансы.</span><span class="sxs-lookup"><span data-stu-id="37802-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="37802-120">Взаимодействие с пользователем при восстановлении из восстановления</span><span class="sxs-lookup"><span data-stu-id="37802-120">User Experience During Failback</span></span>

<span data-ttu-id="37802-121">Переключение на основной ресурс может произойти во время сеанса работы пользователя в резервном пуле; во время переключения на основной ресурс этот сеанс продолжается.</span><span class="sxs-lookup"><span data-stu-id="37802-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="37802-122">Обратите внимание, что процесс восстановления после сбоя занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="37802-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="37802-123">Следует исходить из длительности 60 минут для пула, в котором работает 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="37802-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="37802-124">В приведенных ниже таблицах приведены дополнительные сведения о том, как повлияет пользователь, работающий с клиентом Lync 2013 или Microsoft Lync 2010, в процессе и после восстановления, а также о том, как пользователи в других пулах видят и работают с пользователем в пуле, который не прошел обратно.</span><span class="sxs-lookup"><span data-stu-id="37802-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="37802-125">Пользователи с помощью Microsoft Office Communicator 2007 R2 не могут войти в систему, пока не будет полностью восстановлен пул переднего плана.)</span><span class="sxs-lookup"><span data-stu-id="37802-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="37802-126">Термином *затронутый пользователь* обозначается любой пользователь, вышедший из исходного пула в ходе отработки отказа и обслуживаемый из резервного пула.</span><span class="sxs-lookup"><span data-stu-id="37802-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="37802-127">По определению, пользователи, первоначально размещенные в пуле резервных копий, не подвержены уязвимости.</span><span class="sxs-lookup"><span data-stu-id="37802-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="37802-128">Взаимодействие с затронутым пользователем пула в ходе восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="37802-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37802-129">Состояние пользователя или задача</span><span class="sxs-lookup"><span data-stu-id="37802-129">User state or task</span></span></th>
<th><span data-ttu-id="37802-130">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="37802-130">During failback</span></span></th>
<th><span data-ttu-id="37802-131">После завершения восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="37802-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37802-132">Состояние пользователя, который уже выполнил вход</span><span class="sxs-lookup"><span data-stu-id="37802-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="37802-p108">Пользователь остается подключенным к резервному пулу. В определенный момент времени пользователь выйдет из системы и затем снова выполнит вход на исходном пуле в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="37802-135">Состояние входа пользователя не изменяется, и он переходит в обычный режим.</span><span class="sxs-lookup"><span data-stu-id="37802-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37802-136">Вход нового пользователя</span><span class="sxs-lookup"><span data-stu-id="37802-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="37802-137">Пользователь может выполнить вход в пул в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="37802-138">Пользователь может выполнить вход в исходный пул в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="37802-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37802-139">Текущие конференции, созданные затронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="37802-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="37802-p109">Все модальности конференции приостанавливаются. Кнопка "Повторно присоединиться" будет отображаться, но ни один пользователь не сможет присоединиться повторно, если затронутый пользователь находится в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="37802-p110">Все модальности работают. Для повторного присоединения к конференции участникам требуется нажать кнопку "Повторно присоединиться".</span><span class="sxs-lookup"><span data-stu-id="37802-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37802-144">Текущие конференции, созданные незатронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="37802-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="37802-p111">Конференция будет продолжена, и затронутый пользователь останется подключенным к конференции. Возможности затронутого пользователя в режиме устойчивости ограничены.</span><span class="sxs-lookup"><span data-stu-id="37802-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="37802-147">Конференция будет продолжена, затронутый пользователь останется подключенным к конференции, а все модальности начнут работу после выхода из режима устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37802-148">Создание расписания и изменение запланированных собраний, создание запланированных конференций</span><span class="sxs-lookup"><span data-stu-id="37802-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="37802-149">Невозможно в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="37802-150">Доступно для всех модальностей.</span><span class="sxs-lookup"><span data-stu-id="37802-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37802-151">Сведения о присутствии, отображаемые остальным пользователям того же пула</span><span class="sxs-lookup"><span data-stu-id="37802-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="37802-152">Сведения о присутствии отсутствуют, если пользователь выполнил вход в резервный пул в режиме устойчивости.</span><span class="sxs-lookup"><span data-stu-id="37802-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="37802-153">Отображается последнее состояние присутствия, заданное пользователем, при этом изменения состояния присутствия не отображаются.</span><span class="sxs-lookup"><span data-stu-id="37802-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37802-154">Доступность списка контактов и службы адресной книги</span><span class="sxs-lookup"><span data-stu-id="37802-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="37802-155">Недоступно</span><span class="sxs-lookup"><span data-stu-id="37802-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="37802-156">Доступно</span><span class="sxs-lookup"><span data-stu-id="37802-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37802-157">Все одноранговые сеансы и модальности</span><span class="sxs-lookup"><span data-stu-id="37802-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="37802-158">Доступно</span><span class="sxs-lookup"><span data-stu-id="37802-158">Available</span></span></p></td>
<td><p><span data-ttu-id="37802-159">Доступно</span><span class="sxs-lookup"><span data-stu-id="37802-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="37802-160">Взаимодействие с пользователями, размещенными в незатронутом пуле, в ходе восстановления размещения другого пула</span><span class="sxs-lookup"><span data-stu-id="37802-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37802-161">Задача пользователя</span><span class="sxs-lookup"><span data-stu-id="37802-161">User task</span></span></th>
<th><span data-ttu-id="37802-162">Во время восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="37802-162">During failback</span></span></th>
<th><span data-ttu-id="37802-163">После завершения восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="37802-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37802-164">Просмотр сведений о присутствии затронутого пользователя</span><span class="sxs-lookup"><span data-stu-id="37802-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="37802-165">Отображается последнее состояние присутствия, заданное затронутым пользователем.</span><span class="sxs-lookup"><span data-stu-id="37802-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="37802-p112">Незатронутые пользователи могут просматривать обновленные сведения о присутствии затронутых пользователей.</span><span class="sxs-lookup"><span data-stu-id="37802-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37802-168">Текущие конференции, созданные затронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="37802-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="37802-169">Все модальности конференции приостанавливаются.</span><span class="sxs-lookup"><span data-stu-id="37802-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="37802-p113">Все модальности работают. Для повторного присоединения к конференции участникам требуется нажать кнопку "Повторно присоединиться".</span><span class="sxs-lookup"><span data-stu-id="37802-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37802-172">Текущие конференции, созданные незатронутым пользователем</span><span class="sxs-lookup"><span data-stu-id="37802-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="37802-173">Конференция будет продолжена, затронутый пользователь может остаться в конференции, и все модальности будут работать.</span><span class="sxs-lookup"><span data-stu-id="37802-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="37802-174">Конференция будет продолжена, затронутый пользователь может остаться в конференции, и все модальности будут работать.</span><span class="sxs-lookup"><span data-stu-id="37802-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37802-175">Все одноранговые сеансы и модальности</span><span class="sxs-lookup"><span data-stu-id="37802-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="37802-176">Доступно</span><span class="sxs-lookup"><span data-stu-id="37802-176">Available</span></span></p></td>
<td><p><span data-ttu-id="37802-177">Доступно</span><span class="sxs-lookup"><span data-stu-id="37802-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

