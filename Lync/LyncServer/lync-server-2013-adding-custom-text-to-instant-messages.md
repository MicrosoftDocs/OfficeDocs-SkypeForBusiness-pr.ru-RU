---
title: 'Lync Server 2013: добавление пользовательского текста в мгновенные сообщения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb6746ea5897d779a202bc428b6c7259a1191f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="6d914-102">Добавление пользовательского текста в мгновенные сообщения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d914-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d914-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6d914-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6d914-104">Добавляйте заявление об отказе или предупреждение в начало каждой из мгновенных сообщений Lync 2013, используя командлеты командной консоли **New-CSClientPolicy** или **Set-CSClientPolicy** Lync Server с параметром "с предупреждением".</span><span class="sxs-lookup"><span data-stu-id="6d914-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="6d914-105">В приведенном ниже примере в верхней части окна беседы добавляется напоминание о безопасности при запуске новой ТЕКСТовой беседы.</span><span class="sxs-lookup"><span data-stu-id="6d914-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="6d914-106">С помощью **Grant-CSClientPolicy** можно назначить пользователям новую политику.</span><span class="sxs-lookup"><span data-stu-id="6d914-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="6d914-107">Подробные сведения можно найти в разделе **New-CSClientPolicy** и **Grant-CSClientPolicy** в документации по среде управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d914-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

