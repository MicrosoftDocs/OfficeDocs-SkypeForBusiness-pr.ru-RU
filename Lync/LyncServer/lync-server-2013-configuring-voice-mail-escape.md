---
title: 'Lync Server 2013: Настройка ESC голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f08e12b97c51d68b4b08d10692802cb035ce8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="a532a-102">Настройка escape-последовательности голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a532a-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a532a-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a532a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a532a-104">Когда пользователь настраивает одновременный звонок на мобильный телефон, абонент, как правило, перенаправляется на личную голосовую почту пользователя, если мобильный телефон отключен, исчерпан заряд батареи или он находится вне зоны обслуживания.</span><span class="sxs-lookup"><span data-stu-id="a532a-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="a532a-105">С помощью Lync Server 2013 пользователи могут присоединиться к деловым подразделениям, направляемым в корпоративную почтовую систему.</span><span class="sxs-lookup"><span data-stu-id="a532a-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="a532a-106">В частности, можно настроить таймер, и если звонок отвечает на голосовую почту перевозчика в течение определенного периода времени, Lync Server отключается от системы голосовой почты перевозчика (и личной голосовой почты пользователя), а остальные пользователи конечные точки в корпоративной системе продолжают звонить.</span><span class="sxs-lookup"><span data-stu-id="a532a-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="a532a-107">Таким образом, абонент автоматически направляется в корпоративную систему голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="a532a-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="a532a-108">Эта конфигурация выполняется с помощью командлета командной консоли Lync Server **Set-ксвоицеполици**на уровне политики голосовой связи со следующими параметрами.</span><span class="sxs-lookup"><span data-stu-id="a532a-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="a532a-109">Настройка escape-последовательности голосовой почты</span><span class="sxs-lookup"><span data-stu-id="a532a-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="a532a-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a532a-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a532a-111">Задайте следующие параметры для **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="a532a-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="a532a-112">**EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.</span><span class="sxs-lookup"><span data-stu-id="a532a-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="a532a-p102">**PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимы значения из диапазона 0 – 8000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="a532a-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="a532a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="a532a-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a532a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a532a-116">See Also</span></span>


[<span data-ttu-id="a532a-117">Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a532a-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

