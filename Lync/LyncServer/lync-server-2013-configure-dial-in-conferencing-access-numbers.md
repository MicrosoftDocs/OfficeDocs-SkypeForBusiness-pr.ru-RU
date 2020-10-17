---
title: 'Lync Server 2013: Настройка номеров доступа к конференц-связи с телефонным подключением'
description: 'Lync Server 2013: Настройка номеров доступа к конференц-связи с телефонным подключением.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565085"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="f51a6-103">Настройка номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f51a6-103">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f51a6-104">_**Последнее изменение темы:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="f51a6-104">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="f51a6-p101">При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="f51a6-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="f51a6-107">Прежде чем приступать к созданию номеров доступа, необходимо сначала спланировать регионы конференц-связи с телефонным подключением, а затем настроить абонентские группы в соответствии с регионами.</span><span class="sxs-lookup"><span data-stu-id="f51a6-107">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="f51a6-108">Сведения о регионах можно найти в статье Планирование [конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f51a6-108">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="f51a6-109">Дополнительные сведения о настройке абонентских группы для конференц-связи с телефонным подключением приведены [в статье Настройка абонентских группы для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="f51a6-109">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f51a6-110">Вы не можете использовать новый номер доступа для телефонного подключения &nbsp; , пока не завершится репликация этого номера доступа в доменных службах Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f51a6-110">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="f51a6-111">Репликация может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="f51a6-111">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f51a6-112">Завершив создание номеров доступа, можно изменить отображаемое имя для контактных объектов Active Directory, чтобы пользователи могли легко определить правильный номер доступа.</span><span class="sxs-lookup"><span data-stu-id="f51a6-112">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="f51a6-113">Чтобы изменить отображаемое имя, используйте командлет <STRONG>Set-CsDialInConferencingAccessNumber</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f51a6-113">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="f51a6-114">Объекты Active Directory не следует изменять вручную.</span><span class="sxs-lookup"><span data-stu-id="f51a6-114">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="f51a6-115">Для получения дополнительных сведений об изменении номера доступа, обратитесь к документации по командной консоли Lync Server для командлета <STRONG>Set – CsDialInConferencingAccessNumber</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="f51a6-115">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f51a6-116">Содержание</span><span class="sxs-lookup"><span data-stu-id="f51a6-116">In This Section</span></span>

[<span data-ttu-id="f51a6-117">Создание или изменение номера доступа к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f51a6-117">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f51a6-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f51a6-118">See Also</span></span>


[<span data-ttu-id="f51a6-119">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f51a6-119">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="f51a6-120">Настройка абонентских планов для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f51a6-120">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

