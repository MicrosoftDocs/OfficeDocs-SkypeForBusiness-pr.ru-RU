---
title: 'Lync Server 2013: подготовка к установке и установка анализатора соответствия рекомендациям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303df28b307a2d23bdc468d1c53977030d0cf8df
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Подготовка и установка анализатора соответствия рекомендациям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

Необходимо выполнить вход в систему как член группы администраторов, чтобы выполнить задачи, приведены в этом разделе.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Системные требования для установки анализатора соответствия рекомендациям

Чтобы запустить Lync Server 2013, анализатор соответствия рекомендациям для проверки среды, на компьютере должна быть установлена версия 64 (разрядная версия) одной из следующих операционных систем:

  - Windows Server 2008 R2 с пакетом обновления 1 (SP1) (SP1), стандартная операционная система

  - Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1)

  - Операционная система Windows Server 2012 Datacenter

  - Windows Server 2012 Standard операционная система

  - Операционная система Windows Server 2012 Enterprise

  - Операционная система Windows Server 2012 R2 Datacenter

  - Windows Server 2012 R2 (стандартная операционная система)

  - Операционная система Windows Server 2012 R2 Enterprise

  - Операционная система Windows 8

  - Операционная система Windows 7

На компьютере также должны работать следующие компоненты:

  - Microsoft .NET Framework 4,5. Для Lync Server 2013 необходимо вручную установить 64 – разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013.

  - Lync Server 2013, основные компоненты.

  - Пакет обратной совместимости WMI. Для получения дополнительных сведений обратитесь к разделу [Установка обратной СОВМЕСТИМОСТИ WMI](install-wmi-backward-compatibility-package.md) в документации по миграции.

  - Windows PowerShell 3.0. Дополнительные сведения приведены в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) в документации по развертыванию.

Анализатор соответствия рекомендациям можно установить на компьютерах с поддерживаемой операционной системой, не использующей Lync Server 2013, основные компоненты или пакет обратной совместимости WMI, но с помощью анализатора соответствия рекомендациям на этих компьютерах можно просматривать отчеты, а не для запуска проверок.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Выбор компьютера для установки

Мы рекомендуем установить Lync Server 2013, анализатор соответствия рекомендациям на компьютере, выделенном для управления Lync Server 2013. Средство можно установить на сервере, работающем под управлением Lync Server 2013 или на административном компьютере, на котором запущены средства администрирования Lync Server 2013. При установке средства на сервере, на котором работает Lync Server, рекомендуется использовать это средство для сканирования только этого сервера.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Установка анализатора соответствия рекомендациям

Вы можете скачать анализатор соответствия рекомендациям для Lync Server 2013 по [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539)адресу.

Чтобы установить анализатор соответствия рекомендациям, запустите файл установщика Microsoft RtcBPA.msi на компьютере, где необходимо установить средство, затем следуйте инструкциям на экране. Расположением по умолчанию для установки программных \<файлов являются\>\\файлы\\программ системного диска Lync\\Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

