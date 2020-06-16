---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d883b5446c843ac8b79e2b29d15f8a1c99f0089
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Проверка выполнения пользовательской репликации

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

При запуске командлета **Move-CsUser** может возникать сбой из-за того, что сведения о пользователях между доменными службами Active Directory (AD DS) и базами данных Lync Server 2013 не синхронизируются из-за того, что начальная репликация не завершена. Время, необходимое для успешного завершения начальной синхронизации службы Replicator для Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, в котором размещается пул Lync Server 2013. При первом запуске сервера переднего плана Lync Server 2013 выполняется начальная синхронизация службы Replicator пользователя Lync Server 2013. После этого синхронизация выполняется с интервалом репликатора пользовательских данных. Чтобы проверить, что репликация пользовательских данных завершена до запуска командлета **Move-CsUser**, выполните следующие действия.

<div>

## <a name="to-verify-user-replication-has-completed"></a>Чтобы проверить, что репликация пользовательских данных завершена

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Нажмите кнопку **Пуск** и выберите пункт **Выполнить**.

3.  Введите **eventvwr.exe**, затем нажмите кнопку **ОК**.

4.  В окне просмотра событий щелкните **Журналы приложений и служб**, чтобы развернуть окно, а затем выберите "Lync Server".

5.  В области **Действия** щелкните пункт **Фильтровать текущий журнал**.

6.  В списке **Источники событий** щелкните пункт **LS User Replicator**.

7.  В **\<All Event IDs\>** поле введите **30024** , а затем нажмите кнопку **ОК**.

8.  В фильтрованном списке событий перейдите на вкладку **Общие** и найдите запись, указывающую, что репликация пользователей успешно завершена.

</div>

</div>

<span> </span>

</div>

</div>

</div>

