---
title: 'Lync Server 2013: средства управления Windows PowerShell и Lync Server'
description: 'Lync Server 2013: средства управления Windows PowerShell и Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546045"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Средства управления Windows PowerShell и Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-07-20_

В Microsoft Lync Server 2013 средства управления реализованы с помощью Windows PowerShell. Windows PowerShell включает в себя среду командной строки, зависящие от продукта команды и полный язык сценариев. Lync Server 2013 Tools, реализованные с помощью Windows PowerShell, включают следующие:

  - **Построитель топологий**. Построитель топологий используется для создания, настройки и публикации запланированной топологии, а также для проверки топологии перед началом установки сервера. При установке Lync Server 2013 на отдельных серверах серверы просчитываются опубликованную топологию как часть процесса установки, а программа установки развертывает сервер в соответствии с топологией. После установки сведения о конфигурации автоматически реплицируются на все серверы. Компоненты можно добавлять в развертывание только с помощью построителя топологий.

  - **Командная консоль Lync Server**. Консоль управления Lync Server можно использовать для полного управления развертыванием с помощью командной строки.

  - **Панель управления Lync Server**. Вы можете использовать пользовательский интерфейс панели управления Microsoft Lync Server 2013 для управления наиболее распространенными задачами в развертывании.

Эти средства используют командлеты Windows PowerShell для управления развертыванием, в том числе с помощью командлетов, относящихся к определенному продукту 550. Командлеты безопасности, включенные в Lync Server 2013, в основном используются для управления проверкой подлинности, а также правами и разрешениями пользователей. Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов). Кроме того, несколько командлетов позволяют использовать новую функцию управления доступом Role-Based (RBAC) для делегирования административного управления Lync Server 2013. Дополнительные сведения о командлетах Lync Server приведены в статье [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Функции безопасности скриптов для Windows PowerShell специально разработаны, чтобы помочь предотвратить некоторые проблемы безопасности, связанные с сценариями старых технологий, в том числе VBScript (VBScript). Функции безопасности Windows PowerShell предназначены для создания среды, в которой пользователи не могут легко или непреднамеренно запускать сценарии. По умолчанию функции безопасности Windows PowerShell включены. Вы можете изменить состояние этих функций в соответствии с потребностями сценариев и различными целями обеспечения безопасности. Это не означает, что командная консоль делает невозможной для пользователей запускать скрипты. Вместо этого оболочка по умолчанию делает ее недостаточной, чтобы пользователи могли запускать сценарии, не зная этого. Дополнительные сведения см. в разделе Безопасность сценариев Windows PowerShell в [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .

</div>

<span> </span>

</div>

</div>

</div>

