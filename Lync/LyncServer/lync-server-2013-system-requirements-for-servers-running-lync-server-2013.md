---
title: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013'
description: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562655"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Системные требования для серверов, на которых работает Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-07-24_

<div>


> [!NOTE]
> Сведения о требованиях к оборудованию приведены в статье <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.



</div>

К серверам Standard Edition и Enterprise Edition применяются одинаковые требования к программному обеспечению.

Серверы, работающие под управлением Lync Server 2013, Enterprise Edition, предназначены для крупных организаций в качестве основного организационного развертывания. Сервер Enterprise Edition предназначен для масштабирования до приблизительно 80000 пользователей на пул. Серверы, на которых работает Lync Server 2013, Standard Edition, предназначены для небольших организаций и удаленных расположений из основного развертывания Организации. Одна из двух серверов Standard Edition может поддерживать до 5 000 пользователей.. Подробные сведения о различиях между серверами Standard Edition и серверами Enterprise Edition приведены в статье [Обзор развертывания для Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Установка операционной системы

<div>


> [!IMPORTANT]
> Lync Server 2013 доступен только в 64-разрядном выпуске, для которого требуется 64-разрядное оборудование, а также 64-разрядный выпуск операционной системы Windows Server. 32-разрядный выпуск Lync Server 2013 недоступен в этой версии.



</div>

Серверы Standard Edition и Enterprise Edition могут использовать любой из следующих операционных систем:

  - Windows Server 2008 R2 SP1 или последний пакет обновления.

  - Windows Server 2012

  - Windows Server 2012 R2

Установите операционную систему на сервер Standard Edition или сервер переднего плана Enterprise Edition. Установите все обновления, чтобы обновить операционную систему до последней версии в соответствии со стандартами организации. Дополнительные сведения о рабочих требованиях приведены в статье поддержка [серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

> [!NOTE] 
> Обновление на месте операционной системы не поддерживается в Lync Server 2013.  Необходимо развернуть отдельный пул и перенести пользователей в новый пул с другой операционной системой.

<div>


> [!NOTE]
> Для работы Lync Server 2013 в Windows Server 2012 R2 может потребоваться изменить значение раздела реестра в Windows Server. Это изменение может потребоваться для правильной работы сертификатов, а также для регистрации клиентов с помощью устройств для обеспечения связи в филиалах. Для получения дополнительных сведений см <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Дополнительное программное обеспечение для Lync Server 2013

В дополнение к обновлениям, необходимым для операционной системы, Lync Server 2013 требует, чтобы работали роли операционной системы, компоненты и программное обеспечение. Дополнительные сведения о дополнительном программном обеспечении, которое необходимо установить перед публикацией топологии и установкой Lync Server 2013, можно найти в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Необходимое программное обеспечение для всех ролей сервера

Для всех ролей сервера также необходимо убедиться, что установлены интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5.

Кроме того, интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5 необходимы на компьютере, на котором будут выполняться средства администрирования Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 требует установки Windows PowerShell 3,0 на каждом компьютере, который входит в топологию Lync Server. Более подробную информацию об установке Windows PowerShell 3,0 можно узнать в статье [Установка Windows powershell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]
> В Windows Server &nbsp; 2008 &nbsp; R2 с пакетом обновления 1 (SP1) интерфейс командной строки Windows PowerShell 3,0 не может быть установлен перед установкой Microsoft .net Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

При установке Microsoft .NET Framework 4,5 на серверах, на которых будет выполняться Lync Server 2013 в Windows Server 2012 или Windows Server 2012 R2, необходимо выполнить одно из дополнительных действий. После установки пакета .NET Framework 4.5 используйте диспетчер сервера для установки службы HTTP-активации.

**Установка HTTP-активации .NET 4,5 в Windows Server 2012 или Windows Server 2012 R2**

1.  В меню **Пуск** последовательно выберите пункты **Программы**, **Администрирование**, **Диспетчер сервера**.

2.  В диспетчере сервера в области **Сводка компонентов** выберите **Добавить компоненты**.

3.  Разверните **.NET Framework 4.5**.

4.  Выберите пункт **WCF-активация**, если он еще не выбран. Затем выберите **HTTP-активация**.

5.  Нажмите кнопку **Далее** и следуйте инструкциям для завершения установки.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

