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
ms.openlocfilehash: 2f00b1eb3406c1a3d425727820da8686f96f1dae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>Импорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Если вы хотите сохранить конфигурацию голосовой связи, не публикуя ее, выполните указанные ниже действия, чтобы использовать команды экспорта и импорта на панели управления Lync Server, чтобы сохранить и извлечь снимок конфигурации голосовой маршрутизации. При импорте файла конфигурации голосовой маршрутизации (. вкфг) изменения, внесенные в конфигурацию голосовой маршрутизации на сервере, будут указывать на наличие незафиксированных изменений, внесенных в голосовую почту, на странице в группе " **Маршрутизация** голосовых сообщений" на панели управления Lync Server. Those uncommitted changes are the differences between the two configurations that require reconciliation.

Если вы внесли какие-либо незафиксированные изменения параметров на любой странице в группе, изменения будут сохранены в файле экспортированной конфигурации голосовой связи (. вкфг). Это позволит вам вносить изменения в конфигурацию голосовой маршрутизации во время нескольких сеансов, прежде чем публиковать изменения.

<div>

## <a name="to-import-a-voice-routing-configuration"></a>Импорт конфигурации маршрутизации голосовых данных

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.

4.  В меню **Действия** щелкните пункт **Импорт конфигурации**.

5.  Найдите импортируемый файл конфигурации и нажмите кнопку **Открыть**.

6.  Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.
    
    <div>
    

    > [!NOTE]  
    > При каждом импорте файла конфигурации голосовой связи вам следует запускать команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации. Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Экспорт файла конфигурации голосового маршрута в Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

