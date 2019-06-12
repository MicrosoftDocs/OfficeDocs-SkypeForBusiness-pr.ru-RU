---
title: 'Lync Server 2013: системные требования для серверов, на которых работает Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a>Системные требования для серверов, на которых работает Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-07-24_

<div>


> [!NOTE]  
> Сведения о требованиях к оборудованию можно найти в разделе <A href="lync-server-2013-server-hardware-platforms.md">аппаратные платформы сервера для Lync Server 2013</A>.



</div>

Общие требования к программному обеспечению для серверов Standard Edition и Enterprise Edition.

Серверы Lync Server 2013, Enterprise Edition предназначены для крупных организаций в качестве основных организационных развертываний. Корпоративная версия Enterprise Edition разработана таким образом, чтобы она выработала примерно 80 000 на одном пуле. Серверы Lync Server 2013, Standard Edition предназначены для небольших организаций и удаленных местоположений из основного развертывания Организации. Одна пара серверов стандартных выпусков может поддерживать до 5 000 пользователей.. Подробнее о различиях между серверами Standard Edition и корпоративными выпусками можно найти в статье [Обзор развертывания для Lync Server 2013](lync-server-2013-deployment-overview.md).

<div>

## <a name="operating-system-installation"></a>Установка операционной системы

<div>


> [!IMPORTANT]  
> Lync Server 2013 доступен только в 64-разрядном выпуске, для которого требуется 64-разрядное оборудование и более 64-разрядный выпуск операционной системы Windows Server. В этом выпуске недоступен 32-разрядный выпуск Lync Server 2013.



</div>

Сервер Standard Edition и Enterprise Edition могут использовать любые из указанных ниже вариантов.

  - Windows Server 2008 R2 с пакетом обновления 1 (SP1) или более поздней версии

  - Windows Server 2012

  - Windows Server 2012 R2

Установка программного обеспечения операционной системы на стандартном сервере выпуска Standard Edition или корпоративном выпуске. Примените все обновления, чтобы обновить операционную систему до последнего обновления и требуемый уровень обновления в соответствии со стандартами Организации. Дополнительные сведения о требованиях, предъявляемых к операционной системе, можно найти в документации поддержка [серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .

<div>


> [!NOTE]  
> Для Lync Server 2013 для работы с Windows Server 2012 R2 может потребоваться изменить значение раздела реестра в Windows Server. Это изменение может потребоваться для правильной работы сертификатов и для того, чтобы клиенты могли регистрироваться с бесперебойно работающими управляющими филиалами. Дополнительные сведения можно найти в <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>разделе.



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a>Дополнительное программное обеспечение для Lync Server 2013

В дополнение к обновлениям, которые необходимы для операционной системы, Lync Server 2013 требует наличия ролей операционной системы, функций и программного обеспечения для работы. Дополнительные сведения о дополнительном программном обеспечении, которое должно быть установлено перед публикацией топологии и установкой Lync Server 2013, можно найти в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a>Дополнительное программное обеспечение, необходимое для всех ролей сервера

На всех ролях сервера также необходимо убедиться, что установлен интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5.

Кроме того, интерфейс командной строки Windows PowerShell 3,0 и Microsoft .NET Framework 4,5 необходимы на любом компьютере, на котором выполняются средства администрирования Lync Server.

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013 требует установки Windows PowerShell 3,0 на всех компьютерах, которые участвуют в вашей топологии Lync Server. Подробнее об установке Windows PowerShell 3,0 можно узнать в разделе [Установка Windows powershell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

<div>


> [!NOTE]  
> В Windows Server&nbsp;2008&nbsp;R2 с пакетом обновления 1 (SP1) не удается установить интерфейс командной строки Windows PowerShell 3,0 перед установкой Microsoft .NET Framework 4,5.



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Платформа Microsoft .NET Framework 4.5.

При установке Microsoft .NET Framework 4,5 на сервер, на котором работает Lync Server 2013 на платформе Windows Server 2012 или Windows Server 2012 R2, необходимо выполнить одно из дополнительных действий. После установки .NET Framework 4,5 Используйте Диспетчер серверов для установки активации HTTP.

**Установка активации .NET 4,5 HTTP в Windows Server 2012 или Windows Server 2012 R2**

1.  В меню **Пуск** выберите пункт **программы**, а затем — **Администрирование**, а затем — **Диспетчер серверов**.

2.  В диспетчере серверов в разделе **Сводка по компонентам**выберите **Добавить функции**.

3.  Разверните **.NET Framework 4,5**.

4.  Выберите **Активация WCF** , если она еще не выбрана. Затем выберите **Активация HTTP**.

5.  Нажмите кнопку **Далее** и следуйте инструкциям, чтобы завершить установку.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

