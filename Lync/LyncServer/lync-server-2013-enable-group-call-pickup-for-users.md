---
title: 'Lync Server 2013: Включение групповой отправки звонков для пользователей'
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
ms.openlocfilehash: 69b17ab937d5dd095565e912b26129706b047e69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="9fabf-102">Включение групповой отправки звонков для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fabf-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fabf-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="9fabf-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="9fabf-104">Использование средства SEFAUtil Resource Kit для включения групповой отправки звонков для пользователей.</span><span class="sxs-lookup"><span data-stu-id="9fabf-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="9fabf-105">Пользователям должен быть назначен номер группы с типом Грауппиккуп в таблице орбит парковки вызовов для включения групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="9fabf-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="9fabf-106">Вы назначаете номер группы ответа на звонки и включаете запрос групп в то же время, используя параметр/енаблеграуппиккуп при запуске SEFAUtil. exe.</span><span class="sxs-lookup"><span data-stu-id="9fabf-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="9fabf-107">Включение групповой отправки звонков для пользователя</span><span class="sxs-lookup"><span data-stu-id="9fabf-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="9fabf-108">Войдите на компьютер, на котором установлено средство SEFAUtil с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9fabf-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="9fabf-109">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9fabf-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="9fabf-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="9fabf-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fabf-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9fabf-111">See Also</span></span>


[<span data-ttu-id="9fabf-112">Назначение номера группы для отправки звонков пользователям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fabf-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="9fabf-113">Отключение групповой отправки вызовов для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fabf-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

