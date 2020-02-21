---
title: 'Lync Server 2013: Добавление пользовательского текста в мгновенные сообщения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e42c04c84d6df91b592bf4709daf36d6822aa49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="60cac-102">Добавление пользовательского текста в мгновенные сообщения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60cac-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60cac-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="60cac-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="60cac-104">Добавьте заявление об отказе или предупреждение в начало каждой беседы Lync 2013 для обмена мгновенными сообщениями с помощью командлетов командной консоли **New-CSClientPolicy** или **Set-CSClientPolicy** Lync Server с параметром Warning.</span><span class="sxs-lookup"><span data-stu-id="60cac-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="60cac-105">В приведенном ниже примере показано, как добавить напоминание о безопасности в верхней части окна беседы при начале новой беседы с IM:</span><span class="sxs-lookup"><span data-stu-id="60cac-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="60cac-106">Назначьте эту политику пользователям с помощью **Grant – CSClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="60cac-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="60cac-107">Дополнительные сведения см. в статье **New/CSClientPolicy** и **Grant – CSClientPolicy** в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60cac-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

