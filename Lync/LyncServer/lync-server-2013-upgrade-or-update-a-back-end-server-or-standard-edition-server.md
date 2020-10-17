---
title: Обновление или обновление внутреннего сервера или сервера Standard Edition
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
ms.openlocfilehash: 3afeee91457b2d10f506be81a146643a4598c9f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506646"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Обновление или обновление внутреннего сервера или сервера Standard Edition в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

В этом разделе объясняется, как установить обновление на фоновом сервере Enterprise Edition или сервере Standard Edition.

Если во время обновления внутренний сервер отключается хотя бы на 30 минут, пользователи могут перейти в режим устойчивости. После завершения обновления и подключения внутреннего сервера к серверам переднего плана в пуле пользователи снова получают полный набор функциональных возможностей. Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Обновление внутреннего сервера или сервера Standard Edition

1.  Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.

2.  Загрузите обновление и извлеките его на локальный жесткий диск.

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  Остановите службы Lync Server. В командной строке выполните следующую команду:
    
        Stop-CsWindowsService

5.  Остановите службу Интернета. В командной строке выполните следующую команду:
    
        net stop w3svc

6.  Закройте все окна командной консоли Lync Server.

7.  Установите обновление.

8.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

9.  Снова остановите службы Lync Server, чтобы получить сборки –d из глобального кэша сборок. В командной строке выполните следующую команду:
    
        Stop-CsWindowsService

10. Перезапустите службу Интернета. В командной строке выполните следующую команду:
    
        net start w3svc

11. Примените изменения, внесенные программой LyncServerUpdateInstaller.exe в базы данных SQL Server, выполнив одно из следующих действий:
    
      - Если это внутренний сервер выпуска Enterprise Edition, а на этом сервере нет размещенных баз данных, таких как архивация и отслеживание баз данных, введите в командной строке следующую команду:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Если это внутренний сервер выпуска Enterprise Edition и на этом сервере размещены размещенные базы данных, введите в командной строке следующую команду:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Если это сервер Standard Edition, введите в командной строке следующую команду:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

