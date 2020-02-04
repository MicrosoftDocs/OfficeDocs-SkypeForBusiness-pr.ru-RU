---
title: Перемещение оставшихся пользователей на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d60b3ba622e88978a8bbf555972c95979e8f8c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="ef92f-102">Перемещение оставшихся пользователей на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef92f-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef92f-103">_**Тема последнего изменения:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="ef92f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="ef92f-104">Вы можете переместить пользователей на новое развертывание Lync Server 2013 с помощью панели управления Lync Server или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ef92f-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="ef92f-105">Чтобы обеспечить плавный переход на Lync Server 2013, необходимо соблюдать определенные требования.</span><span class="sxs-lookup"><span data-stu-id="ef92f-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="ef92f-106">Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этом разделе, можно найти в статье [Настройка миграции клиентов](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="ef92f-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="ef92f-107">Подробное руководство по перемещению пользователей описано в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ef92f-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ef92f-108">Вы не можете использовать оснастку "пользователи и компьютеры Active Directory" и средства администрирования Lync Server 2010 для перемещения пользователей из старой среды в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef92f-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="ef92f-109">Когда пользователь перемещается в пул Lync Server 2013, данные для пользователя перемещаются в базу данных на сервер, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="ef92f-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ef92f-110">Сюда входят активные собрания, созданные устаревшим пользователем.</span><span class="sxs-lookup"><span data-stu-id="ef92f-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="ef92f-111">Например, если пользователь с устаревшим подключением настроил Конференц- <STRONG>зал для собраний</STRONG> , она будет доступна в новом пуле Lync Server 2013 после перемещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef92f-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="ef92f-112">Сведения о том, как получить доступ к собранию, будут по-прежнему совпадать с <STRONG>URL-адресом Конференции и идентификатором конференции</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ef92f-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="ef92f-113">Единственная разница заключается в том, что Конференция теперь размещена в пуле Lync Server 2013, а не в пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ef92f-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ef92f-114">Пользователям в службах для Lync Server 2013 не требуется развертывать обновленные клиенты в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="ef92f-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="ef92f-115">Новые функции будут доступны пользователям только в том случае, если они обновлены до нового клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="ef92f-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="ef92f-116">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="ef92f-116">Post Migration Task</span></span>

1.  <span data-ttu-id="ef92f-117">После перемещения пользователей убедитесь, что им назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ef92f-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="ef92f-118">Чтобы убедиться в том, что пользователи, размещенные на Lync Server 2013, работают без проблем с федеративными пользователями, расположенными на Lync Server 2010, политика конференц-связи, назначенная для мигрировавших пользователей, должна быть разрешена анонимным участникам.</span><span class="sxs-lookup"><span data-stu-id="ef92f-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="ef92f-119">Политики Конференции, разрешающие анонимным участникам разрешение **на приглашение** анонимных пользователей, выделены на панели управления lync Server 2013, и в выходных данных командлета **Get-КсконференЦингполици** в командной консоли Lync Server — значение **true** для **аллованонимауспартиЦипантсинмитингс** .</span><span class="sxs-lookup"><span data-stu-id="ef92f-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="ef92f-120">Дополнительные сведения о настройке политик конференц-связи с помощью командной консоли Lync Server можно найти в разделе [Set/ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef92f-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

