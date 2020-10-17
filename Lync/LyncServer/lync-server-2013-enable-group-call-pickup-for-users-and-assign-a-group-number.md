---
title: 'Lync Server 2013: Включение групповой отправки звонков для пользователей и назначение номера группы'
description: 'Lync Server 2013: Включение групповой отправки звонков для пользователей и назначение номера группы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03fcb20bfd88842dc8b29100b9ece595bf76254
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559645"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="e644f-103">Включение групповой отправки звонков для пользователей в Lync Server 2013 и назначение номера группы</span><span class="sxs-lookup"><span data-stu-id="e644f-103">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e644f-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e644f-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e644f-105">После добавления номеров групп ответа на звонки в таблицу орбит парковки вызовов необходимо назначить номера групп пользователям и включить для них функцию отправки групп.</span><span class="sxs-lookup"><span data-stu-id="e644f-105">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="e644f-106">Используйте дополнительное средство дополнительного набора ресурсов для активации дополнительных компонентов (SEFAUtil), чтобы назначить номера групп и включить отправке звонков групп.</span><span class="sxs-lookup"><span data-stu-id="e644f-106">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e644f-107">В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, размещенным в сети.</span><span class="sxs-lookup"><span data-stu-id="e644f-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="e644f-108">Пользователи, размещенные в Интернете, не могут участвовать в групповой отправке звонков.</span><span class="sxs-lookup"><span data-stu-id="e644f-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e644f-109">Это значит, что их звонки не могут отвечать другим пользователям и они не могут отвечать на звонки другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="e644f-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="e644f-110">Назначение номера группы и включение групповой отправки звонков для пользователя</span><span class="sxs-lookup"><span data-stu-id="e644f-110">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="e644f-111">Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e644f-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="e644f-112">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e644f-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="e644f-113">Например, чтобы назначить пользователю номер группы 199, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e644f-113">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e644f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e644f-114">See Also</span></span>


[<span data-ttu-id="e644f-115">Отключение групповой отправки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e644f-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

