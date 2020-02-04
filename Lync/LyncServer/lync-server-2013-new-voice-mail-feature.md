---
title: 'Lync Server 2013: новая функция голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27dbea942488181eb69695f78713c9e126c32aab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="f5fec-102">Новая функция голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5fec-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5fec-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f5fec-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f5fec-104">Lync Server 2013 представляет голосовую почту, а именно улучшенные возможности управления голосовой почтой.</span><span class="sxs-lookup"><span data-stu-id="f5fec-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="f5fec-105">Эта новая функция может определять, когда звонок направляется на голосовую почту, и предотвращает немедленное перенаправление звонка на голосовую почту пользователя, не предоставляя пользователю возможность ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="f5fec-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="f5fec-106">Это происходит, когда пользователь включает Одновременный звонок на мобильный телефон, а его мобильный телефон выключен, выходит за пределы батареи или выходит за пределы диапазона.</span><span class="sxs-lookup"><span data-stu-id="f5fec-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="f5fec-107">Управляющая Голосовая почта обнаруживает, что звонок немедленно отвечал на голосовую почту пользователя, и отсоединяет Звонок на голосовую почту мобильного телефона.</span><span class="sxs-lookup"><span data-stu-id="f5fec-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="f5fec-108">Звонок продолжает звонить по другим конечным точкам пользователя, предоставляя пользователю возможность ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="f5fec-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="f5fec-109">Если пользователь не отвечает на звонок, Звонок направляется в корпоративную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="f5fec-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f5fec-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f5fec-110">See Also</span></span>


[<span data-ttu-id="f5fec-111">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5fec-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="f5fec-112">Новые возможности корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5fec-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

