---
title: 'Lync Server 2013: поддержка программного обеспечения баз данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Поддержка программного обеспечения баз данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-12-01_

Lync Server 2013 поддерживает следующие системы управления базами данных:

  - **Серверная база данных интерфейсного пула, база данных архивации, база данных мониторинга, база данных сохраняемого чата и база данных соответствия сохраняемого чата**
    
      - Программное обеспечение для баз данных Microsoft SQL Server 2008 R2 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.
    
      - Microsoft SQL Server 2008 R2 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.
    
      - Microsoft SQL Server 2012 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.
    
      - Microsoft SQL Server 2012 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.

  - **Базы данных сервера Standard Edition и серверного сервера переднего плана**
    
      - Microsoft SQL Server 2012 Express (64-разрядная версия). Рекомендуется установить более новый пакет обновления.
        
        Мы поддерживаем обновление и обновление Microsoft SQL Server на серверах переднего и стандартном выпуске. Тем не менее, если вы вносите обновления или исправления на серверах переднего плана, необходимо учитывать требования кворума. Подробнее см. разделы [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) и [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64-bit Edition) автоматически устанавливается на Lync Server 2013 на каждом сервере Standard Edition и на каждом сервере переднего плана.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 не поддерживает 32-разрядный выпуск SQL Server. Вам следует использовать 64-разрядную версию.</P>
> <LI>
> <P>SQL Server Web Edition и SQL Server Workgroup Edition не поддерживаются. Вы не можете использовать их в Lync Server 2013.</P>
> <LI>
> <P>Lync Server 2013 поддерживает встроенное зеркальное отображение базы данных.</P>
> <LI>
> <P>Чтобы использовать роль сервера мониторинга, необходимо установить службы SQL Server Reporting Services.</P></LI></UL>



</div>

В пуле переднего плана серверная база данных может быть одним компьютером SQL Server.

<div>


> [!IMPORTANT]  
> При совместном использовании баз данных Lync Server с другими базами данных мы настоятельно рекомендуем оценить все факторы, которые могут повлиять на доступность и производительность, а также гарантируя, что если один из узлов завершается сбоем, оставшийся узел может обрабатывать загрузку. Для проверки возможностей отработки отказа мы рекомендуем провести тестирование для всех сценариев отработки отказа.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>Использование зеркального отображения и кластеризации SQL

Lync Server 2013 поддерживает использование либо SQL Mirroring, либо кластеризации SQL для каждой базы данных сервера Lync Server. Зеркальное отображение SQL можно легко настроить с помощью средства Topology Builder в Lync Server 2013. Для настройки отказоустойчивой кластеризации SQL необходимо использовать SQL Server.

Lync Server 2013 поддерживает как зеркальное отражение SQL, так и топологии кластеризации SQL для всех развертываний, в том числе гринфиелд развертываний и организаций, обновленных из предыдущих версий Lync Server.

Поддержка кластеризации SQL предназначена для активных и пассивных конфигураций. По соображениям производительности не следует предоставлять общий доступ к пассивному узлу для любого другого экземпляра SQL.

Включена поддержка описанных ниже функций.

  - Отказоустойчивая кластеризация двух узлов для указанных ниже продуктов.
    
      - Microsoft SQL Server 2012 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.
    
      - Microsoft SQL Server 2008 R2 Standard (64-разрядная версия). Рекомендуется установить более новый пакет обновления.

  - Отказоустойчивая кластеризации для узлов количеством до шестнадцати для указанных ниже продуктов.
    
      - Microsoft SQL Server 2012 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.
    
      - Программное обеспечение для баз данных Microsoft SQL Server 2008 R2 Enterprise (64-разрядная версия). Рекомендуется установить более новый пакет обновления.

Дополнительные сведения о зеркальном отображении SQL можно найти в разделе о [высокой доступности сервера в Lync server 2013](lync-server-2013-back-end-server-high-availability.md). Подробнее о том, как развертывать кластеризацию SQL, можно узнать в разделе [Настройка кластеризации SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).

Дополнительные сведения и рекомендации по работе с отказоустойчивой кластеризацией в SQL Server 2012 можно <http://technet.microsoft.com/en-us/library/hh231721.aspx>найти в разделе. Сведения об отказоустойчивой кластеризации в SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>можно найти в разделе.

</div>

</div>

<span> </span>

</div>

</div>

</div>

