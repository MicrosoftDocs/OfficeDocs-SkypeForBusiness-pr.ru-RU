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
ms.openlocfilehash: cad247f2643261e02e475c459e703db843f18fbe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Настройка escape-последовательности голосовой почты в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Если пользователь настроит одновременные звонки на мобильный телефон, то в случае, когда его мобильный телефон окажется выключенным, разряженным или же будет находиться вне зоны действия, звонящий обычно будет маршрутизироваться на личную голосовую почту этого пользователя. С помощью Lync Server 2013 пользователи могут принять участие в бизнес-вызовах, направляемых в корпоративную систему голосовой почты. В частности, можно настроить таймер и при ответе на вызов голосовой почты перевозчика в пределах определенного периода времени Lync Server отключается от системы голосовой почты перевозчика (и личной голосовой почты пользователя), а оставшаяся часть пользователя конечные точки в корпоративной системе продолжают звонить. Таким образом звонящий будет автоматически маршрутизироваться в корпоративную систему голосовой почты пользователя.

Эта конфигурация выполняется с помощью командлета командной консоли Lync Server, **Set-CsVoicePolicy**на уровне политики голосовой связи со следующими параметрами.

<div>

## <a name="to-configure-voice-mail-escape"></a>Настройка escape-последовательности голосовой почты

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Задайте следующие параметры для **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.
    
      - **PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимыми являются значения из диапазона 0 – 8000 миллисекунд.

</div>

<div>

## <a name="example"></a>Пример

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка политики голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

