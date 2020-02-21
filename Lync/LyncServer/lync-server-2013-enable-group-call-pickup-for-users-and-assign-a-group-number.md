---
title: 'Lync Server 2013: Включение групповой отправки звонков для пользователей и назначение номера группы'
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
ms.openlocfilehash: 0b4c0bc47862eaaf2cf74d29190325d9d09ee939
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="00711-102">Включение групповой отправки звонков для пользователей в Lync Server 2013 и назначение номера группы</span><span class="sxs-lookup"><span data-stu-id="00711-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00711-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="00711-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="00711-104">После добавления номеров групп ответа на звонки в таблицу орбит парковки вызовов необходимо назначить номера групп пользователям и включить для них функцию отправки групп.</span><span class="sxs-lookup"><span data-stu-id="00711-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="00711-105">Используйте дополнительное средство дополнительного набора ресурсов для активации дополнительных компонентов (SEFAUtil), чтобы назначить номера групп и включить отправке звонков групп.</span><span class="sxs-lookup"><span data-stu-id="00711-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00711-106">В гибридном развертывании не назначайте группу группового ответа на звонки пользователям, размещенным в сети.</span><span class="sxs-lookup"><span data-stu-id="00711-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="00711-107">Пользователи, размещенные в Интернете, не могут участвовать в групповой отправке звонков.</span><span class="sxs-lookup"><span data-stu-id="00711-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="00711-108">Это значит, что их звонки не могут отвечать другим пользователям и они не могут отвечать на звонки другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="00711-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="00711-109">Назначение номера группы и включение групповой отправки звонков для пользователя</span><span class="sxs-lookup"><span data-stu-id="00711-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="00711-110">Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="00711-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="00711-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="00711-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="00711-112">Например, чтобы назначить пользователю номер группы 199, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="00711-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00711-113">См. также</span><span class="sxs-lookup"><span data-stu-id="00711-113">See Also</span></span>


[<span data-ttu-id="00711-114">Отключение групповой отправки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00711-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

