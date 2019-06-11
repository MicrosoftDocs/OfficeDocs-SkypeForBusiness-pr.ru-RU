---
title: 'Lync Server 2013: разрешение группового приема для пользователей и назначение номера группы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9523a76eb9cd23dd4c8ee531520341aaf82f508
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="e0b22-102">Включение отправки группового звонка для пользователей в Lync Server 2013 и назначение номера группы</span><span class="sxs-lookup"><span data-stu-id="e0b22-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0b22-103">_**Тема последнего изменения:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e0b22-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e0b22-104">После того как вы добавите номера групп для отправки звонков в таблицу "приостановить Звонок", вы назначаете номера групп для пользователей и включаете для них функцию отправки групп.</span><span class="sxs-lookup"><span data-stu-id="e0b22-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="e0b22-105">Используйте вспомогательный набор ресурсов для активации дополнительных компонентов (Сефаутил), чтобы назначить групповые номера и включить функцию отправки групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="e0b22-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0b22-106">В гибридном развертывании не назначайте группу отправки группового звонка пользователям, которые находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="e0b22-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="e0b22-107">Пользователи, которые подключены к сети, не могут принимать участие в расправке групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="e0b22-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e0b22-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span><span class="sxs-lookup"><span data-stu-id="e0b22-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="e0b22-109">Назначение номера группы и включение отправки группового звонка для пользователя</span><span class="sxs-lookup"><span data-stu-id="e0b22-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="e0b22-110">Войдите в систему компьютера, на котором установлено средство SEFAUtil, с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e0b22-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="e0b22-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e0b22-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="e0b22-112">Например, чтобы назначить пользователю групповой номер 199, введите:</span><span class="sxs-lookup"><span data-stu-id="e0b22-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0b22-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e0b22-113">See Also</span></span>


[<span data-ttu-id="e0b22-114">Отключение отправки группового вызова для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0b22-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

