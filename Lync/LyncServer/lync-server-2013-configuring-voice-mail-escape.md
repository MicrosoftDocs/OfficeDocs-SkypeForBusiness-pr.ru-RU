---
title: 'Lync Server 2013: Настройка escape-последовательности голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131b36b87a3d930662cdd863dd4ebc1d0d69163e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="ff434-102">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff434-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff434-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ff434-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ff434-104">Если пользователь настроит одновременные звонки на мобильный телефон, то в случае, когда его мобильный телефон окажется выключенным, разряженным или же будет находиться вне зоны действия, звонящий обычно будет маршрутизироваться на личную голосовую почту этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff434-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="ff434-105">С помощью Lync Server 2013 пользователи могут принять участие в бизнес-вызовах, направляемых в корпоративную систему голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="ff434-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="ff434-106">В частности, можно настроить таймер и при ответе на вызов голосовой почты перевозчика в пределах определенного периода времени Lync Server отключается от системы голосовой почты перевозчика (и личной голосовой почты пользователя), а оставшаяся часть пользователя конечные точки в корпоративной системе продолжают звонить.</span><span class="sxs-lookup"><span data-stu-id="ff434-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="ff434-107">Таким образом звонящий будет автоматически маршрутизироваться в корпоративную систему голосовой почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="ff434-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="ff434-108">Эта конфигурация выполняется с помощью командлета командной консоли Lync Server, **Set-CsVoicePolicy**на уровне политики голосовой связи со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="ff434-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="ff434-109">Настройка escape-последовательности голосовой почты</span><span class="sxs-lookup"><span data-stu-id="ff434-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="ff434-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ff434-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ff434-111">Задайте следующие параметры для **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="ff434-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="ff434-112">**EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="ff434-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="ff434-p102">**PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимыми являются значения из диапазона 0 – 8000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="ff434-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="ff434-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ff434-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff434-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ff434-116">See Also</span></span>


[<span data-ttu-id="ff434-117">Настройка политики голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff434-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

