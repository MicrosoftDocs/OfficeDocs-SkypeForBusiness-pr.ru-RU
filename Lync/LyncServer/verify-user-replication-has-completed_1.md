---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31bed57b6e24db0ba6f75e323fe311aa4aaf262c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Проверка выполнения пользовательской репликации

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

При запуске командлета **Move-CsLegacyUser** могут возникать сбои из-за сведений о пользователях между доменными службами Active Directory (AD DS) и базами данных Lync Server 2013, так как начальная репликация не завершена. Время, необходимое для успешного завершения начальной синхронизации службы Replicator для Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, в котором размещается пул Lync Server 2013. При первом запуске сервера переднего плана Lync Server 2013 выполняется начальная синхронизация службы Replicator пользователя Lync Server 2013. После этого синхронизация определяется интервалом репликации пользователей. Выполните следующие действия, чтобы проверить завершение репликации пользователей перед выполнением командлета **Move-CsLegacyUser**.

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Проверка завершения репликации пользователей

1.  На сервере переднего плана Lync Server 2013 откройте меню **Пуск** и выберите команду **выполнить**.

2.  Введите **eventvwr.exe**, затем нажмите кнопку **ОК**.

3.  В окне просмотра событий щелкните **Журналы приложений и служб**, чтобы развернуть окно, а затем выберите "Lync Server".

4.  В области **Действия** щелкните пункт **Фильтровать текущий журнал**.

5.  В списке **Источники событий** щелкните пункт **LS User Replicator**.

6.  В **\<All Event IDs\>** поле введите **30024** , а затем нажмите кнопку **ОК**.

7.  В фильтрованном списке событий перейдите на вкладку **Общие** и найдите запись, указывающую, что репликация пользователей успешно завершена.

</div>

</div>

<span> </span>

</div>

</div>

</div>

