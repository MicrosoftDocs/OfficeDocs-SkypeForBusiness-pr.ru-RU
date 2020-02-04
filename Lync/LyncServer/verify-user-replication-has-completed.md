---
title: Проверка выполнения пользовательской репликации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed93912b62e323186a902fb717548c16b405299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Проверка выполнения пользовательской репликации

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

При запуске командлета **Move-CsUser** может возникнуть сбой из-за того, что сведения о пользователе между доменными службами Active Directory (AD DS) и базами данных Lync Server 2013 не синхронизованы, так как начальная репликация не завершена. Время, необходимое для успешного завершения начальной синхронизации службы репликации пользователей Lync Server 2013, зависит от количества контроллеров домена, размещенных в лесу Active Directory, на котором размещается пул Lync Server 2013. Начальная синхронизация службы репликатора пользователей Lync Server 2013 происходит при первом запуске сервера переднего плана Lync Server 2013. После этого синхронизация будет основана на интервале репликатора пользователей. Выполните описанные ниже действия, чтобы убедиться, что репликация пользователей завершилась, прежде чем запускать командлет **Move-CsUser** .

<div>

## <a name="to-verify-user-replication-has-completed"></a>Проверка завершения репликации пользователя

1.  Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.

2.  Откройте меню **Пуск** и выберите команду **выполнить**.

3.  Введите **eventvwr. exe** и нажмите кнопку **ОК**.

4.  В окне просмотра событий щелкните **журналы приложений и служб** , чтобы развернуть его, а затем выберите Lync Server.

5.  В области **действия** щелкните **фильтр текущего журнала**.

6.  В списке **источники событий** выберите пункт **репликатор пользователей Ls**.

7.  Во ** \<всех кодах\> событий** введите **30024** и нажмите кнопку **ОК**.

8.  В списке отфильтрованных событий на вкладке **Общие** найдите запись, в которой указано, что репликация пользователей успешно завершена.

</div>

</div>

<span> </span>

</div>

</div>

</div>

