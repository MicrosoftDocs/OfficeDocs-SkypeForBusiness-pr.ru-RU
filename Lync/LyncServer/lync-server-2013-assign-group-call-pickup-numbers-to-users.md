---
title: 'Lync Server 2013: Назначение пользователям номеров для отправки групповых вызовов пользователям'
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
ms.openlocfilehash: 172a91c1a1417db6ffd938a48360c7d4bce3533c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="34139-102">Назначение номера группы для отправки звонков пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34139-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34139-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="34139-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="34139-104">После добавления номеров групп ответа групп в таблицу орбит парковки вызовов можно назначить группы пользователям.</span><span class="sxs-lookup"><span data-stu-id="34139-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="34139-105">Используйте дополнительное средство дополнительного набора ресурсов для активации функций расширения (SEFAUtil), чтобы назначить группы ответа на звонки пользователям.</span><span class="sxs-lookup"><span data-stu-id="34139-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34139-106">В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, размещенным в сети.</span><span class="sxs-lookup"><span data-stu-id="34139-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="34139-107">Пользователи, размещенные в Интернете, не могут участвовать в групповой отправке звонков.</span><span class="sxs-lookup"><span data-stu-id="34139-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="34139-108">Это значит, что их звонки не могут отвечать другим пользователям и они не могут отвечать на звонки другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="34139-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="34139-109">Назначение группе группового ответа на звонки пользователю</span><span class="sxs-lookup"><span data-stu-id="34139-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="34139-110">Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="34139-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="34139-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34139-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="34139-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="34139-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34139-113">См. также</span><span class="sxs-lookup"><span data-stu-id="34139-113">See Also</span></span>


[<span data-ttu-id="34139-114">Включение групповой отправки звонков для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34139-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="34139-115">Отключение групповой отправки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34139-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

