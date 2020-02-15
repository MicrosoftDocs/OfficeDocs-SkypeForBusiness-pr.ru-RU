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
ms.openlocfilehash: 2b7951b0dd9a6841d66c1782322f6c44a4e16d99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="d9113-102">Новая функция голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9113-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9113-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d9113-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d9113-104">Lync Server 2013 вводит escape-адрес голосовой почты, что обеспечивает возможность управления голосовой почтой.</span><span class="sxs-lookup"><span data-stu-id="d9113-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="d9113-105">Эта новая возможность позволяет обнаруживать, был ли звонок направлен в голосовую почту, и предотвращать немедленную переадресацию звонка в голосовую почту мобильного телефона пользователя, не позволяющую пользователю ответить на вызов.</span><span class="sxs-lookup"><span data-stu-id="d9113-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="d9113-106">Этот сценарий реализуется, когда пользователь включает одновременные звонки на мобильный телефон, который отключен, разрядился или находится вне зоны доступа.</span><span class="sxs-lookup"><span data-stu-id="d9113-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="d9113-107">Задержка голосовой почты определяет то, что вызов был сразу же направлен в голосовую почту мобильного телефона пользователя и разъединяет вызов.</span><span class="sxs-lookup"><span data-stu-id="d9113-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="d9113-108">Это позволяет звонить на другие конечные точки пользователя, чтобы тот мог на ответить на вызов.</span><span class="sxs-lookup"><span data-stu-id="d9113-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="d9113-109">Если пользователь не ответит на звонок, то только тогда он будет направлен в корпоративную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="d9113-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d9113-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d9113-110">See Also</span></span>


[<span data-ttu-id="d9113-111">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9113-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="d9113-112">Новые функции корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9113-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

