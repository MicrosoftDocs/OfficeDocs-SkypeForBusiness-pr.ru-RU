---
title: 'Lync Server 2013: выполнение и мониторинг резервных копий'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b79fdbaceff06155389d101570b23d6143b9bbcc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536756"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Выполнение и мониторинг резервных копий в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-05-15_

Ваши бизнес-приоритеты должны учитывать спецификацию требований к резервному копированию и восстановлению в Организации. Выполнение резервного копирования серверов и данных является первой строкой обороны при аварийном планировании.

На компьютерах, на которых работают службы Lync Server 2013 или Server Roles, должна быть копия текущей топологии, текущих параметров конфигурации и текущих политик, прежде чем они смогут работать в своей роли. Lync Server несет ответственность за передачу этих сведений на каждый компьютер, которым она необходима.

Командлеты **Export — CsConfiguration** и **Import CsConfiguration** используются для резервного копирования и восстановления топологии Lync Server, параметров конфигурации и политик во время обновления центрального хранилища управления. Командлеты **Export – CsConfiguration** позволяют экспортировать данные в. ZIP-файл. Затем можно использовать командлет **Import-CsConfiguration** для чтения. ZIP-файл и восстановите топологию, параметры конфигурации и политики в центральном хранилище управления. После этого службы репликации Lync Server будут реплицировать восстановленные данные на другие компьютеры, на которых работают службы Lync Server.

Возможность экспорта и импорта данных конфигурации также используется при начальной настройке компьютеров, расположенных в сети периметра (например, на пограничных серверах). При настройке компьютера в сети периметра необходимо сначала выполнить репликацию вручную с помощью командлетов CsConfiguration: необходимо экспортировать данные конфигурации с помощью командлета **Export — CsConfiguration** , а затем скопировать. ZIP-файл на компьютер в сети периметра. После этого можно воспользоваться **Import-CsConfiguration** и параметром LocalStore для импорта данных. Это необходимо сделать только один раз. После этого репликация будет выполняться автоматически.

По умолчанию право на локальный запуск командлета **Export-CsConfiguration** имеют члены группы RTCUniversalServerAdmins. Чтобы получить список всех ролей RBAC, назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду из командной строки Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Все резервные базы данных SQL Server 2012 должны быть резервными копиями в соответствии с рекомендациями [SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).

Регулярное тестирование плана аварийного восстановления для инфраструктуры Lync Server 2013 следует выполнять в лабораторной среде, насколько это возможно. Для получения дополнительных сведений о тестировании аварийного восстановления обратитесь к разделу Monthly Tasks.

Обратите внимание на то, что частота резервного копирования может быть скорректирована в соответствии с целями точки восстановления и точки восстановления. Рекомендуется регулярно периодически создавать моментальные снимки в течение дня. Как правило, полное резервное копирование выполняется каждые 24 часа.

<div>

## <a name="see-also"></a>См. также


[Import — CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export — CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Рекомендации по SQL](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

