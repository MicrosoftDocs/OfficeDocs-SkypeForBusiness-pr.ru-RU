---
title: 'Lync Server 2013: Назначение пользователям номеров для отправки групповых вызовов пользователям'
description: 'Lync Server 2013: Назначьте пользователям номера для отправки групповых вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566135"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="e1bdc-103">Назначение номера группы для отправки звонков пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bdc-103">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1bdc-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e1bdc-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e1bdc-105">После добавления номеров групп ответа групп в таблицу орбит парковки вызовов можно назначить группы пользователям.</span><span class="sxs-lookup"><span data-stu-id="e1bdc-105">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="e1bdc-106">Используйте дополнительное средство дополнительного набора ресурсов для активации функций расширения (SEFAUtil), чтобы назначить группы ответа на звонки пользователям.</span><span class="sxs-lookup"><span data-stu-id="e1bdc-106">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e1bdc-107">В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, размещенным в сети.</span><span class="sxs-lookup"><span data-stu-id="e1bdc-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="e1bdc-108">Пользователи, размещенные в Интернете, не могут участвовать в групповой отправке звонков.</span><span class="sxs-lookup"><span data-stu-id="e1bdc-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e1bdc-109">Это значит, что их звонки не могут отвечать другим пользователям и они не могут отвечать на звонки другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="e1bdc-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="e1bdc-110">Назначение группе группового ответа на звонки пользователю</span><span class="sxs-lookup"><span data-stu-id="e1bdc-110">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="e1bdc-111">Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e1bdc-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="e1bdc-112">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e1bdc-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="e1bdc-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1bdc-113">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1bdc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e1bdc-114">See Also</span></span>


[<span data-ttu-id="e1bdc-115">Включение групповой отправки звонков для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bdc-115">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="e1bdc-116">Отключение групповой отправки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bdc-116">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

