---
title: 'Lync Server 2013: импорт файла конфигурации маршрута голосовых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35c955ade3383d79a9a69b101b23e2f5327ccb58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Если вы хотите сохранить конфигурацию маршрутизации голосовой связи, не публикуя ее, выполните следующие действия, чтобы воспользоваться командами экспорта и импорта панели управления Lync Server для сохранения и получения моментального снимка конфигурации маршрутизации голосовой связи. При импорте файла конфигурации маршрутизации голосовой связи (. вкфг), но при изменении конфигурации маршрутизации голосовой связи на сервере страницы в группе " **Маршрутизация голосовых** вызовов" на панели управления Lync Server будут указывать на незафиксированные изменения маршрутизации голосовых вызовов. Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.

Если вы внесли какие-либо незафиксированные изменения параметров на любую страницу в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг). Это позволяет вносить изменения в конфигурацию маршрутизации голосовой связи во время нескольких сеансов перед публикацией изменений.

<div>

## <a name="to-import-a-voice-routing-configuration"></a>Импорт конфигурации маршрутизации голосовой связи

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.

4.  В меню **действия** выберите пункт **Импорт конфигурации**.

5.  Найдите файл конфигурации, который необходимо импортировать, и нажмите кнопку **Открыть**.

6.  Нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.
    
    <div>
    

    > [!NOTE]  
    > При импорте файла конфигурации голосовой связи необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации. Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

