---
title: 'Lync Server 2013: экспорт файла конфигурации маршрута голосовых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4128dc1e2d3a300d0305336d87f36f0d6a06a055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a>Экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Если вы хотите сохранить конфигурацию маршрутизации голосовой связи, не публикуя ее, выполните следующие действия, чтобы воспользоваться командами экспорта и импорта панели управления Lync Server для сохранения и получения моментального снимка конфигурации маршрутизации голосовой связи. При импорте файла конфигурации маршрутизации голосовой связи (. вкфг), но при изменении конфигурации маршрутизации голосовой связи на сервере страницы в группе " **Маршрутизация голосовых** вызовов" на панели управления Lync Server будут указывать на незафиксированные изменения маршрутизации голосовых вызовов. Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.

Если вы внесли какие-либо незафиксированные изменения параметров на любую страницу в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг). Это позволяет вносить изменения в конфигурацию маршрутизации голосовой связи во время нескольких сеансов перед публикацией изменений.

<div>

## <a name="to-export-a-voice-routing-configuration"></a>Экспорт конфигурации маршрутизации голосовых данных

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Маршрутизация голосовых данных**.

4.  В меню **Действия** щелкните пункт **Экспорт конфигурации**.

5.  Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

