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

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a>Настройка escape-последовательности голосовой почты в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Когда пользователь настраивает одновременный звонок на мобильный телефон, абонент, как правило, перенаправляется на личную голосовую почту пользователя, если мобильный телефон отключен, исчерпан заряд батареи или он находится вне зоны обслуживания. С помощью Lync Server 2013 пользователи могут присоединиться к деловым подразделениям, направляемым в корпоративную почтовую систему. В частности, можно настроить таймер, и если звонок отвечает на голосовую почту перевозчика в течение определенного периода времени, Lync Server отключается от системы голосовой почты перевозчика (и личной голосовой почты пользователя), а остальные пользователи конечные точки в корпоративной системе продолжают звонить. Таким образом, абонент автоматически направляется в корпоративную систему голосовой почты.

Эта конфигурация выполняется с помощью командлета командной консоли Lync Server **Set-ксвоицеполици**на уровне политики голосовой связи со следующими параметрами.

<div>

## <a name="to-configure-voice-mail-escape"></a>Настройка escape-последовательности голосовой почты

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Задайте следующие параметры для **Set-CsVoicePolicy**:
    
      - **EnableVoicemailEscapeTimer** — включает или отключает таймер escape-последовательности.
    
      - **PSTNVoicemailEscapeTimer** — задает значение времени ожидания в миллисекундах. Значение по умолчанию составляет 1500 миллисекунд; допустимы значения из диапазона 0 – 8000 миллисекунд.

</div>

<div>

## <a name="example"></a>Пример

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка политик голосовой связи и записей использования ТСОП для авторизации функций звонков и предоставления привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

