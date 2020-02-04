---
title: 'Lync Server 2013: программные требования для средств администрирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a>Программные требования для средств администрирования в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-07_

В этой статье описывается программное обеспечение, необходимое для установки и использования средств администрирования Lync Server 2013 в дополнение к требованиям к операционной системе.

<div>

## <a name="microsoft-net-framework-45"></a>Платформа Microsoft .NET Framework 4.5.

Для Lync Server 2013 требуется 64-разрядная версия Microsoft .NET Framework 4,5.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Windows PowerShell 3,0 необходима для работы любого компонента Microsoft Lync Server 2013. Дополнительные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="windows-installer-version-45"></a>Установщик Windows версии 4,5

Lync Server 2013 использует технологию установщика Windows для установки, удаления и обслуживания различных ролей сервера. Установщик Windows версии 4,5 можно использовать в качестве распространяемого компонента для операционной системы Windows Server. Установщик Windows 4,5 поставляется с Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2 означает, что вам не нужно загружать служебную программу для любого компьютера, на котором работает Lync Server 2013. (Lync Server 2013 можно установить только на компьютерах под управлением Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2.)

Тем не менее, если вы хотите установить консоль управления Lync Server или построитель топологии Lync Server на рабочей станции администратора, вам может потребоваться загрузить установщик Windows 4,5. Эта служебная программа поставляется в Windows 7 и Windows 2008 R2, но не в предыдущих версиях операционной системы Windows. Вы можете скачать установщик Windows 4,5 из центра загрузки Майкрософт по адресу <http://go.microsoft.com/fwlink/p/?linkid=197395>.

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a>Подключаемый модуль браузера Microsoft Silverlight 5

Панель управления Lync Server 2013 — это веб-инструмент, и необходимо установить последнюю версию подключаемого модуля браузера Microsoft Silverlight 5. Если вы запускаете панель управления Lync Server 2013, если это программное обеспечение не установлено или если установлено более ранняя версия, откроется панель управления Lync Server 2013 с предложением установить требуемую версию.

</div>

<div>

## <a name="see-also"></a>См. также


[Поддержка сервера и средств в операционной системе в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Требования к инфраструктуре средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Административные права и разрешения, необходимые для установки и администрирования Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

