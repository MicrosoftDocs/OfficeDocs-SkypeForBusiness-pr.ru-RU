---
title: 'Lync Server 2013: создание или изменение правила трансляции вручную'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Создание и изменение правила трансляции вручную в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-08-06_

Если вы хотите определить правило перевода с помощью регулярного выражения для соответствующего шаблона и правила трансляции, выполните указанные ниже действия. Кроме того, вы можете ввести набор значений в инструменте **создать правило перевода** и включить для вас соответствующий шаблон и правило перевода с помощью панели управления Lync Server. Дополнительные сведения можно найти в разделе [Создание или изменение правила трансляции с помощью средства создания правил перевода в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Определение правила преобразования вручную

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Чтобы приступить к определению правила трансляции, выполните действия, описанные в разделе [Настройка канала передачи мультимедиа в Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) с помощью шага 10 или [Настройте магистраль без обхода мультимедиа в Lync Server 2013 на](lync-server-2013-configure-a-trunk-without-media-bypass.md) этапе 9.

4.  В поле **Имя** на странице **Создание правила трансляции** или **Изменение правила трансляции** введите имя, описывающее шаблон номера для преобразования.

5.  В поле **Описание** введите описание этого правила преобразования, например **US International long-distance dialing** (Международный звонок из США) (необязательно).

6.  Внизу раздела **Построение правила трансляции** нажмите кнопку **Правка**.

7.  В разделе **Ввод регулярных выражений** введите следующие данные.
    
      - В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.
    
      - В поле **Правило трансляции** укажите шаблон для формата преобразованных номеров.
    
    Например, если ввести ** ^ \\+ (\\d{9}\\d +) $** в соответствии с **этим шаблоном** и **011 $1** в **правиле перевода**, правило будет переведено + 441235551010 в 011441235551010.

8.  Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.

9.  Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.

10. На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.
    
    <div>
    

    > [!NOTE]  
    > Всякий раз при создании или изменении правила преобразования необходимо выполнять команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации. Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение правила трансляции с помощью инструмента "Создание правил перевода" в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Настройка магистрали без обхода мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

