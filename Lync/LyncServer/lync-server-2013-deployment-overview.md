---
title: 'Lync Server 2013: обзор развертывания'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Обзор развертывания для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-03-12_

Основное различие между Lync Server 2013 Enterprise Edition и Lync Server 2013 Standard Edition состоит в том, что стандартный выпуск не поддерживает возможности высокой доступности, включенные в Enterprise Edition. Для обеспечения высокой доступности вам нужно развернуть несколько серверов переднего плана в пул, а затем вы можете создать зеркальную копию сервера под управлением SQL Server. С помощью Enterprise Edition вы можете выделять или определять отдельное сервер-посредник. Сервер мониторинга и сервер архивации могут использовать изолированный сервер, на котором работает SQL Server. Кроме того, у них могут быть экземпляры SQL Server, запущенные на сервере базы данных, для серверов и групп с внешними интерфейсами.

Серверы Lync Server 2013 Standard Edition предназначены для небольших организаций и удаленных расположений, которые географически удаляются из основного развертывания Организации. Два стандартных сервера выпуска, Объединенные вместе для перехода на другой ресурс, в случае аварии могут поддерживать до 5 000 пользователей. Вы не можете выдавать пул серверов стандартных выпусков (например, серверы переднего плана) в Enterprise Edition. Кроме того, база данных SQL Server, используемая в стандартном выпуске, — это размещенный сервер, на котором работает SQL Server Express, разработанный для обработки рабочих нагрузок сервера Standard Edition. Это не значит, что все роли должны располагаться на сервере Standard Edition. Вы можете использовать изолированные серверы обновлений и пограничные серверы. База данных SQL Server для централизованного управления хранилищем и целях Lync Server 2013 должны располагаться на сервере Standard Edition, расположенном на сервере с запущенным SQL Server. Сервер мониторинга и сервер архивации используют изолированный сервер с базой данных SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

