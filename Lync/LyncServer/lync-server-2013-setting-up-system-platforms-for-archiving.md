---
title: 'Lync Server 2013: Настройка системных платформ для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13682b7507e133dd49c102bf6c25293ff5da2c08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Настройка системных платформ для архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-09_

Прежде чем приступать к развертыванию архива, необходимо установить требуемую операционную систему и любое другое необходимое программное обеспечение на оборудовании, удовлетворяющем требованиям к системе.

  - **Развертывание платформы**   Lync Server 2013 для Lync Server 2013 не имеет серверов архивации. Вместо этого агенты сбора данных Объединенные данные выполняются на серверах переднего плана и серверах стандартных выпусков для сбора данных для архивации, поэтому для размещения архивации не требуется отдельная системная платформа.

  - **Платформа для хранения данных**   в Lync Server 2013 вы можете хранить данные с помощью одного из указанных ниже способов.
    
      - **Интеграция с Microsoft Exchange**   если вы хотите сохранить данные архивации в Lync Server 2013 с помощью развертывания Exchange 2013, вместо или Помимо настройки отдельной базы данных для хранения данных архивации необходимо, чтобы на сервере Exchange Server была установлена версия Exchange 2013. Подробные сведения о настройке системных платформ для Exchange 2013 можно найти в документации по продукту Exchange.
    
      - **SQL Server**   если вы хотите использовать отдельную базу данных SQL Server для хранения данных для архивации, вместо или помимо использования интеграции с Microsoft Exchange необходимо настроить системную платформу для базы данных перед развертыванием архивации. Конкретные требования к системной платформе зависят от того, используете ли вы Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 для базы данных архивирования. Подробные сведения о настройке системных платформ для этих баз данных можно найти в документации по продукту Microsoft SQL Server 2008 R2 и Microsoft SQL Server 2012.

  - **Платформа файлового сервера**   Lync Server 2013 хранит архивные файлы Lync Server в том же расположении, которое вы указали для хранения файлов при настройке серверов переднего плана или стандартных серверов выпусков. Вы не можете указать отдельное расположение для хранения файлов, поэтому для архивации файлов не требуется отдельная системная платформа. Если вы используете Microsoft Exchange Integration, Exchange 2013 файлы для архивации данных Lync хранятся на серверах Exchange 2013 для пользователей, использующих эти серверы Exchange.

</div>

<span> </span>

</div>

</div>

</div>

