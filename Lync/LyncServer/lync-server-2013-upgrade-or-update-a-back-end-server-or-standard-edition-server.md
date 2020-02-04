---
title: Обновление или переход на сервер Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0526cc7ba6a6abefd066bf07d845ffed3a4107ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Обновление или обновление серверного сервера или стандартного выпуска Standard в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

В этой статье объясняется, как установить обновление на обратном сервере Enterprise Edition или стандартном сервере Standard Edition.

Если сервер выходит за частоту не менее 30 минут после его обновления, пользователи могут перейти в режим устойчивости. После завершения обновления и повторного подключения серверов к внешним серверам из пула пользователи будут возвращены в полную функциональность. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Обновление внутреннего сервера или сервера Standard Edition

1.  Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.

2.  Загрузите обновление и извлеките его на локальный жесткий диск.

3.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

4.  Остановите службы Lync Server. В командной строке выполните следующую команду:
    
        Stop-CsWindowsService

5.  Остановите службу Интернета. В командной строке выполните следующую команду:
    
        net stop w3svc

6.  Закройте все окна команд Lync Server Management Shell.

7.  Установите обновление.

8.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

9.  Снова остановите службы Lync Server, чтобы перехватить сборки глобального кэша сборок (GAC) – d. В командной строке выполните следующую команду:
    
        Stop-CsWindowsService

10. Перезапустите службу Интернета. В командной строке выполните следующую команду:
    
        net start w3svc

11. Примените изменения, внесенные Линксерверупдатеинсталлер. exe, в базу данных SQL Server, выполнив одно из указанных ниже действий.
    
      - Если это сервер выпуска Enterprise Edition и на нем нет размещенных на нем баз данных, таких как архивация и мониторинг баз данных, введите в командной строке следующую команду:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Если этот сервер выпуска Enterprise Edition и на нем есть размещенные на сервере базы данных, введите в командной строке следующее:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Если это сервер Standard Edition, введите в командной строке следующее:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

