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
ms.openlocfilehash: 966182705fd3f18bfa10d1d6042e1c3c94204e9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500216"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="5b9ae-102">Перемещение оставшихся пользователей на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9ae-102">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b9ae-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="5b9ae-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="5b9ae-104">Вы можете переместить пользователей в новое развертывание Lync Server 2013 с помощью панели управления Lync Server или командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="5b9ae-105">Для обеспечения плавного перехода на Lync Server 2013 необходимо соблюдение определенных требований.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="5b9ae-106">Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этой статье, можно найти в разделе [Настройка клиентов для миграции](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="5b9ae-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="5b9ae-107">Подробное описание действий по перемещению пользователей приведено в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="5b9ae-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5b9ae-108">Вы не можете использовать оснастку "Active Directory — пользователи и компьютеры" или средства администрирования Lync Server 2010 для перемещения пользователей из старой среды в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="5b9ae-109">При перемещении пользователя в пул Lync Server 2013 данные для пользователя перемещаются в фоновую базу данных, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5b9ae-110">Это относится к активным собраниям, созданным пользователем старой системы.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="5b9ae-111">Например, если устаревший пользователь настроил Конференц- <STRONG>зал для собраний</STRONG> , эта конференция по-прежнему будет доступна в новом пуле Lync Server 2013 после перемещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="5b9ae-112">Сведения для доступа к этому собранию — те же <STRONG>URL-адрес и код конференции</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="5b9ae-113">Единственное отличие состоит в том, что Конференция теперь размещается в пуле Lync Server 2013, а не в пуле Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5b9ae-114">Пользователям в Lync Server 2013 не требуется развертывать обновленные клиенты одновременно.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="5b9ae-115">Новые функциональные возможности станут доступными пользователям только после обновления до новой версии клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="5b9ae-116">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="5b9ae-116">Post Migration Task</span></span>

1.  <span data-ttu-id="5b9ae-117">После перемещения пользователей убедитесь, что для них назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="5b9ae-118">Чтобы убедиться, что собрания, организованные пользователями, размещенными в Lync Server 2013, тесно взаимодействуют с федеративными пользователями, размещенными на Lync Server 2010, политика конференц-связи, назначенная для перенесенных пользователей, должна иметь анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="5b9ae-119">Политики конференц-связи, которые позволяют анонимным участникам разрешить **участникам приглашать анонимных пользователей** , выбранные в панели управления lync Server 2013 и иметь для **аллованонимауспартиЦипантсинмитингс** значение **true** в выходных данных командлета **Get-CsConferencingPolicy** в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="5b9ae-120">Сведения о настройке политики конференц-связи с помощью консоли управления Lync Server можно найти в статье [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b9ae-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

