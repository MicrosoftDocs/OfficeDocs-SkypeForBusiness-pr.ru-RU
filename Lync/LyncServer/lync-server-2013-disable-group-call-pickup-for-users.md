---
title: 'Lync Server 2013: отключение отправки группового ответа на звонки для пользователей'
description: 'Lync Server 2013: отключение отправки группового ответа на вызовы для пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f5b4542cf7bb8ea5be524d2695701979ec2987
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568195"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="f8980-103">Отключение групповой отправки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8980-103">Disable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8980-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f8980-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f8980-105">Используйте следующую процедуру для отключения групповой отправки звонков для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8980-105">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8980-106">Когда вы отключаете групповой ответ на звонки для пользователя, номер группы ответа на звонки, назначенный пользователю, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="f8980-106">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="f8980-107">Если вы попытаетесь повторно включить запрос групп для этого пользователя, необходимо снова назначить номер группы ответа на звонки с помощью параметра/енаблеграуппиккуп.</span><span class="sxs-lookup"><span data-stu-id="f8980-107">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="f8980-108">Отключение групповой отправки вызовов для пользователя</span><span class="sxs-lookup"><span data-stu-id="f8980-108">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="f8980-109">Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="f8980-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="f8980-110">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8980-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="f8980-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8980-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8980-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f8980-112">See Also</span></span>


[<span data-ttu-id="f8980-113">Назначение номера группы для отправки звонков пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8980-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="f8980-114">Включение групповой отправки звонков для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8980-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

