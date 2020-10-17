---
title: Перемещение оставшихся пользователей на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81d74c9cc578909061d098d349e685817b71e4d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500176"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="d3769-102">Перемещение оставшихся пользователей на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3769-102">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3769-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="d3769-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="d3769-104">Вы можете переместить пользователей в новое развертывание Lync Server 2013 с помощью панели управления Lync Server или командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3769-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="d3769-105">Для обеспечения плавного перехода на Lync Server 2013 необходимо соблюдение определенных требований.</span><span class="sxs-lookup"><span data-stu-id="d3769-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="d3769-106">Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этой статье, можно найти в разделе [Настройка клиентов для миграции](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="d3769-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="d3769-107">Подробное описание действий по перемещению пользователей приведено [в статье этап 6: перемещение пользователей в пилотный пул](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d3769-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3769-108">Вы не можете использовать оснастку "Active Directory — пользователи и компьютеры" или средства администрирования Microsoft Office Communications Server 2007 R2 для перемещения пользователей из старой среды в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3769-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3769-p102">Для выполнения командлета <STRONG>Move-CsLegacyUser</STRONG> требуется, чтобы имена пользователей были правильно сформированы и не содержали пробелов в начале и в конце. Учетную запись пользователя невозможно переместить с помощью командлета <STRONG>Move-CsLegacyUser</STRONG>, если в начале или конце учетной записи содержатся пробелы.</span><span class="sxs-lookup"><span data-stu-id="d3769-p102">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces. You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="d3769-111">При перемещении пользователя в пул Lync Server 2013 данные для пользователя перемещаются в фоновую базу данных, связанную с новым пулом.</span><span class="sxs-lookup"><span data-stu-id="d3769-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d3769-112">Это относится к активным собраниям, созданным пользователем старой системы.</span><span class="sxs-lookup"><span data-stu-id="d3769-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="d3769-113">Например, если устаревший пользователь настроил Конференц- <STRONG>зал для собраний</STRONG> , эта конференция по-прежнему будет доступна в новом пуле Lync Server 2013 после перемещения пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3769-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="d3769-114">Сведения для доступа к этому собранию — те же <STRONG>URL-адрес и код конференции</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d3769-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="d3769-115">Единственное отличие состоит в том, что Конференция теперь размещается в пуле Lync Server 2013, а не в пуле Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d3769-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d3769-116">Пользователям в Lync Server 2013 не требуется развертывать обновленные клиенты одновременно.</span><span class="sxs-lookup"><span data-stu-id="d3769-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="d3769-117">Новые функциональные возможности станут доступными пользователям только после обновления до новой версии клиентского программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="d3769-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="d3769-118">Задача после миграции</span><span class="sxs-lookup"><span data-stu-id="d3769-118">Post Migration Task</span></span>

1.  <span data-ttu-id="d3769-119">После перемещения пользователей убедитесь, что для них назначена политика конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d3769-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="d3769-120">Чтобы обеспечить согласованность собраний, организованных пользователями, размещенными в Lync Server 2013, с федеративными пользователями, размещенными на сервере Office Communications Server 2007 R2, политика конференц-связи, назначенная для перенесенных пользователей, должна поддерживать анонимных участников.</span><span class="sxs-lookup"><span data-stu-id="d3769-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="d3769-121">Политики конференц-связи, которые позволяют анонимным участникам разрешить **участникам приглашать анонимных пользователей** , выбранные в панели управления lync Server 2013 и иметь для **аллованонимауспартиЦипантсинмитингс** значение **true** в выходных данных командлета **Get-CsConferencingPolicy** в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3769-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="d3769-122">Сведения о настройке политики конференц-связи с помощью консоли управления Lync Server можно найти в статье [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3769-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

