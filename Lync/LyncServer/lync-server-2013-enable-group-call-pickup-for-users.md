---
title: 'Lync Server 2013: разрешение группового приема звонков для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="84fd4-102">Включение отправки группового звонка для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd4-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84fd4-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="84fd4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="84fd4-104">С помощью средства Сефаутил Resource Kit вы можете включить функцию отправки групп для пользователей.</span><span class="sxs-lookup"><span data-stu-id="84fd4-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="84fd4-105">Пользователи должны назначить номер группы с типом Грауппиккуп в таблице «орбита», чтобы включить функцию отправки группового звонка.</span><span class="sxs-lookup"><span data-stu-id="84fd4-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="84fd4-106">Вы назначаете номер группы для отправки звонков и включаете возможность отправки группового звонка одновременно с помощью параметра/енаблеграуппиккуп при запуске Сефаутил. exe.</span><span class="sxs-lookup"><span data-stu-id="84fd4-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="84fd4-107">Включение отправки группового звонка для пользователя</span><span class="sxs-lookup"><span data-stu-id="84fd4-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="84fd4-108">Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="84fd4-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="84fd4-109">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="84fd4-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="84fd4-110">Например:</span><span class="sxs-lookup"><span data-stu-id="84fd4-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84fd4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="84fd4-111">See Also</span></span>


[<span data-ttu-id="84fd4-112">Назначение номеров группового звонка пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd4-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="84fd4-113">Отключение отправки группового вызова для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fd4-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

