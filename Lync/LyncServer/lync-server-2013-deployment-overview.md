---
title: 'Lync Server 2013: Общие сведения о развертывании'
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
ms.openlocfilehash: 0b21d6c6a977fbb94a54114753f32c022aa5e713
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Обзор развертывания для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-03-12_

Основное различие между Lync Server 2013 Enterprise Edition и Lync Server 2013 Standard Edition заключается в том, что стандартный выпуск не поддерживает функции высокого уровня доступности, включенные в Enterprise Edition. Для обеспечения высокой доступности необходимо развернуть несколько серверов переднего плана в пул, а затем можно создать зеркальный набор для сервера, на котором работает SQL Server. В Enterprise Edition можно выбрать размещение или определение отдельного сервера-посредника. Сервер мониторинга и сервер архивации могут использовать изолированный сервер, на котором работает SQL Server. Или они могут иметь экземпляры SQL Server, запущенные на сервере баз данных, для серверов и пулов переднего плана.

Серверы, на которых работает Lync Server 2013 Standard Edition, предназначены для небольших организаций и удаленных расположений, которые географически удаляются из основного развертывания Организации. Два сервера Standard Edition, Объединенных для отработки отказа в случае аварии, могут поддерживать до 5 000 пользователей. Вы не можете осуществлять объединение серверов Standard Edition, например серверов переднего плана в Enterprise Edition. Кроме того, база данных SQL Server, используемая в стандартном выпуске, — это совмещенный сервер, на котором работает SQL Server Express, предназначенный для обработки рабочих нагрузок сервера Standard Edition. Это не означает, что все роли должны располагаться на сервере Standard Edition. У вас могут быть изолированные серверы-посредники и пограничные серверы. База данных SQL Server для центрального хранилища управления и в целях Lync Server 2013 должна размещаться на сервере Standard Edition, размещенном на сервере SQL Server. Сервер мониторинга и сервер архивации используют изолированный сервер с базой данных SQL Server.

</div>

<span> </span>

</div>

</div>

</div>

