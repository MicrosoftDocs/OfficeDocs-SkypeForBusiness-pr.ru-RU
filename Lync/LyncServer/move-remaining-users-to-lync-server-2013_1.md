---
title: Перемещение оставшихся пользователей на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a728afae37c2e8d317cd6c75872c75d358226475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="d285a-102">Перемещение оставшихся пользователей на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d285a-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d285a-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="d285a-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="d285a-104">Вы можете переместить пользователей на новое развертывание Lync Server 2013 с помощью панели управления Lync Server или командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d285a-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="d285a-105">Чтобы обеспечить плавный переход на Lync Server 2013, необходимо соблюдать определенные требования.</span><span class="sxs-lookup"><span data-stu-id="d285a-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="d285a-106">Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этом разделе, можно найти в статье [Настройка миграции клиентов](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="d285a-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="d285a-107">Подробное руководство по перемещению пользователей описано в разделе [этап 6: перемещение пользователей в пилотный пул](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d285a-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d285a-108">Вы не можете использовать оснастку "пользователи и компьютеры Active Directory" и средства администрирования Microsoft Office Communications Server 2007 R2 для перемещения пользователей из старой среды в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d285a-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d285a-109">Для командлета <STRONG>Move-кслегациусер</STRONG> необходимо, чтобы имена пользователей были правильно сформированы и не имели начальных и конечных пробелов.</span><span class="sxs-lookup"><span data-stu-id="d285a-109">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces.</span></span> <span data-ttu-id="d285a-110">Вы не можете переместить учетную запись пользователя с помощью командлета <STRONG>Move-кслегациусер</STRONG> , если он содержат начальные или конечные пробелы.</span><span class="sxs-lookup"><span data-stu-id="d285a-110">You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="d285a-111">Когда пользователь перемещается в пул Lync Server 2013, данные для пользователя перемещаются в базу данных на сервер, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="d285a-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d285a-112">Сюда входят активные собрания, созданные устаревшим пользователем.</span><span class="sxs-lookup"><span data-stu-id="d285a-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="d285a-113">Например, если пользователь с устаревшим подключением настроил Конференц- <STRONG>зал</STRONG> для собраний, она будет доступна в новом пуле Lync Server 2013 после перемещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="d285a-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="d285a-114">Сведения о том, как получить доступ к собранию, будут по-прежнему совпадать с <STRONG>URL-адресом Конференции и идентификатором конференции</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d285a-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="d285a-115">Единственная разница заключается в том, что Конференция теперь размещена в пуле Lync Server 2013, а не в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d285a-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d285a-116">Пользователям в службах для Lync Server 2013 не требуется развертывать обновленные клиенты в одно и то же время.</span><span class="sxs-lookup"><span data-stu-id="d285a-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="d285a-117">Новые функции будут доступны пользователям только в том случае, если они обновлены до нового клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d285a-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="d285a-118">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="d285a-118">Post Migration Task</span></span>

1.  <span data-ttu-id="d285a-119">После перемещения пользователей убедитесь, что им назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d285a-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="d285a-120">Чтобы убедиться в том, что пользователи, размещенные на Lync Server 2013, работают без проблем с федеративными пользователями, расположенными на сервере Office Communications Server 2007 R2, политике конференц-связи, назначенной для мигрировавших пользователей, должно быть разрешение анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="d285a-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="d285a-121">Политики конференц-связи, разрешающие анонимным участникам возможность **приглашать анонимных пользователей** , выделены в окне Lync Server 2013, и установить для **аллованонимауспартиЦипантсинмитингс** значение **true** в выходных данных из командлет **Get-ксконференЦингполици** в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d285a-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="d285a-122">Дополнительные сведения о настройке политик конференц-связи с помощью командной консоли Lync Server можно найти в разделе [Set/ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d285a-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

