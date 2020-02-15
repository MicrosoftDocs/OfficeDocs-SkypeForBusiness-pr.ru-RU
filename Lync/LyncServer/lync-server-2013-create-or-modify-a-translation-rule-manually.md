---
title: 'Lync Server 2013: создание или изменение правила трансляции вручную'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ae305052523c05bacb294928c1f81afd4e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Создание или изменение правила трансляции вручную в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-06_

Если требуется задать правило преобразования путем создания регулярного выражения для шаблона соответствия и правила преобразования, выполните следующие действия. Кроме того, можно ввести набор значений в инструменте **Создание правила преобразования** и включить панель управления Lync Server для создания соответствующего шаблона и правила преобразования. Дополнительные сведения см. в статье [Создание или изменение правила преобразования с помощью средства создания правил преобразования в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).

<div>

## <a name="to-define-a-translation-rule-manually"></a>Определение правила преобразования вручную

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Чтобы приступить к определению правила преобразования, выполните действия, описанные в статье [Настройка магистрали с обходом сервера, в Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) до этапа 10 или [Настройка магистрали без обхода сервера в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) с шага 9.

4.  В поле **Имя** на странице **Создание правила преобразования** или  **Изменение правила преобразования** введите имя, описывающее шаблон номера для преобразования.

5.  В поле **Описание** введите описание этого правила преобразования, например **Международный звонок из США** (необязательно).

6.  Внизу раздела **Построение правила преобразования** нажмите кнопку **Правка**.

7.  В диалоговом окне **Ввод регулярных выражений** введите следующее.
    
      - В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.
    
      - В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.
    
    Например, если ввести ** ^ \\+ (\\{9}\\d d +) $** в поле **сопоставить этот шаблон** и **011 $1** в **правиле преобразования**, то правило будет переводиться + 441235551010 на 011441235551010.

8.  Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.

9.  Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.

10. На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).
    
    <div>
    

    > [!NOTE]  
    > Всякий раз при создании или изменении правила преобразования необходимо выполнять команду <STRONG>Commit all</STRONG> (Сохранить все), чтобы опубликовать изменение конфигурации. Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Создание или изменение правила преобразования с помощью средства "Построение правила преобразования" в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

