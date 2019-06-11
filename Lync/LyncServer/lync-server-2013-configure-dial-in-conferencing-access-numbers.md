---
title: 'Lync Server 2013: настройка номеров доступа для конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d42d8fbe6d3f507d0cadb7dc879b940191c04603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="14870-102">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14870-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14870-103">_**Тема последнего изменения:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="14870-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="14870-104">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции.</span><span class="sxs-lookup"><span data-stu-id="14870-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="14870-105">Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="14870-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="14870-106">Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами.</span><span class="sxs-lookup"><span data-stu-id="14870-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="14870-107">Дополнительные сведения о регионах: [требования к конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="14870-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="14870-108">Дополнительные сведения о настройке абонентской группы для конференц-связи с телефонным подключением можно найти в разделе Настройка абонентской [группы для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="14870-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14870-109">Вы не можете использовать новый номер доступа для телефонного подключения, пока не завершится репликация этого номера доступа в доменных службах Active Directory (AD&nbsp;DS).</span><span class="sxs-lookup"><span data-stu-id="14870-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="14870-110">Репликация может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="14870-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="14870-111">Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.</span><span class="sxs-lookup"><span data-stu-id="14870-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="14870-112">Используйте командлет <STRONG>Set-ксдиалинконференЦингакцесснумбер</STRONG> , чтобы изменить отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="14870-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="14870-113">Не следует изменять объекты Active Directory вручную.</span><span class="sxs-lookup"><span data-stu-id="14870-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="14870-114">Дополнительные сведения об изменении номера для доступа можно найти в документации по командной консоли Lync Server Management Shell для командлета <STRONG>Set-ксдиалинконференЦингакцесснумбер</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="14870-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="14870-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="14870-115">In This Section</span></span>

[<span data-ttu-id="14870-116">Создание или изменение номера доступа к конференции с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14870-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14870-117">См. также</span><span class="sxs-lookup"><span data-stu-id="14870-117">See Also</span></span>


[<span data-ttu-id="14870-118">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14870-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="14870-119">Настройка абонентских групп для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14870-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

