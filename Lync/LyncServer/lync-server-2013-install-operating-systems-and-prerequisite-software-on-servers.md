---
title: Установка операционных систем и необходимого программного обеспечения на серверы
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c41147d33dce792f88b30f72b36201ddb6c7d62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Установка операционных систем и необходимого программного обеспечения на серверы для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-07-24_

После того как вы настроили аппаратную и системную инфраструктуру, вам нужно установить соответствующие операционные системы и обновления Windows в дополнение ко всем остальным обязательным программам на каждом сервере, который вы развертываете. Сюда входят все серверные роли Lync Server 2013 и любые дополнительные серверы инфраструктуры или серверы SQL Server, необходимые для развертывания.

<div>


> [!NOTE]
> В этом разделе описывается установка операционной системы и необходимого программного обеспечения для внутренних серверов. Если вы развертываете пограничные серверы для поддержки внешних пользователей, вам также потребуется установить операционную систему и необходимое программное обеспечение для этих серверов, в том числе на пограничные серверы и обратное прокси-серверы. Подробнее о том, как подготовить серверы к поддержке внешних пользователей, можно найти в разделе <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Подготовка к установке серверов в демилитаризованной зоне для Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>Установка операционных систем Windows на серверах

На каждом сервере, который вы развертываете, установите соответствующую операционную систему Windows, как описано ниже.

  - **Серверы Lync Server 2013**   дополнительные сведения о требованиях к операционной системе для серверов, на которых работает Lync Server 2013, можно найти в документации поддержка [серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .

  - **Серверы баз данных**   дополнительные сведения о требованиях к операционной системе для серверов баз данных, включая серверную базу данных, архивированную базу данных и контрольную базу данных, можно найти в документации по SQL Server. Сведения о SQL Server 2012 можно найти в книге SQL Server 2012 на [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)сайте.

<div>


> [!NOTE]
> Если вы устанавливаете Lync Server 2013 на Windows Server&nbsp;2008&nbsp;R2 с пакетом обновления 1 (SP1), необходимо сначала установить обновление, описанное в статье Microsoft Knowledge on 2646886, исправление: повреждение кучи возникает, когда модуль вызывает метод инсертентитибоди в службах IIS 7,5 ", по адресу <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp. кбид = 2646886</A>.<BR>Кроме того, необходимо внести изменения в реестр, как описано в статье KB, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">события с кодами 32402, 61045 записываются в журнал на Lync server 2013 серверы переднего плана, установленные в Windows server 2012 R2</A>.



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>Установка центра обновления Windows на серверах

Установите на каждом сервере следующие обновления из центра обновления Windows.

  - **Обновление Windows для серверов с Lync Server 2013**   дополнительные сведения об обновлениях из центра обновления Windows, необходимых для серверов с Lync Server 2013, приведены в разделе [Дополнительные требования к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.

  - **Серверы баз данных**   дополнительные сведения об обновлениях, которые необходимы для серверов баз данных, включая серверную базу данных, архивированную базу данных и контрольную базу данных, можно найти в документации по SQL Server 2012. Сведения о SQL Server 2012 можно найти в книге SQL Server 2012 на [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)сайте.

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>Установка другого программного обеспечения на серверах

Для установки Lync Server 2013 требуется установить следующее дополнительное программное обеспечение на серверах:

  - **Необходимое программное обеспечение для серверов с Lync Server 2013**   дополнительные требования к программному обеспечению для серверов с Lync Server 2013 зависят от того, какая роль сервера развернута. Подробные сведения о конкретных требованиях к программному обеспечению для каждого сервера можно найти в разделе [Дополнительные требования к программному обеспечению для Lync server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.

  - ****   Для поддержки сценариев проверки подлинности сервера и сервера Lync Server Identity Foundation для Windows 2013 требуется установка Windows Identity Foundation. Чтобы убедиться, что она уже установлена на вашем компьютере, откройте панель управления, выберите пункты **программы и компоненты**, **Просмотреть установленные обновления**и просмотрите раздел **Microsoft Windows**. Подробнее об установке Windows Identity Foundation можно узнать [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)в статье.

  - **Microsoft .NET Framework 4,5**   для Lync Server 2013 требуется 64-разрядный выпуск Microsoft .NET Framework 4,5.

  - **Необходимое программное обеспечение для серверов**   баз данных дополнительные сведения об обновлении Windows, которое требуется для серверов баз данных, включая серверную базу данных, архивированную базу данных и контрольную базу данных, можно [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)найти в документации по SQL Server 2012 по адресу.
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 автоматически устанавливает Microsoft SQL Server 2012 Express на каждом стандартном сервере выпуска и каждый сервер, на котором работает Lync Server 2013, на котором расположено локальное хранилище конфигураций.

    
    </div>

  - **Среда выполнения**   формата Windows Media для всех серверов переднего плана и серверов Standard Edition, на которых будет развернута конференция, должна быть установлена среда выполнения формата Windows Media. Для работы с файлами Windows Media Audio (WMA), которые воспринимаются приложениями для приема, объявления и ответа, воспроизводится для объявлений и музыкальных файлов, которые требуются в среде выполнения формата Windows Media.
    
    <div>
    

    > [!NOTE]
    > Для Windows Server 2012 и Windows Server 2012 R2 среда выполнения формата Windows Media устанавливается вместе с Microsoft Media Foundation.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Для Windows Server&nbsp;2008 и windows Server&nbsp;2008&nbsp;R2 среда выполнения формата Windows Media устанавливается в составе рабочего стола Windows. Перед установкой Lync Server 2013 рекомендуется установить возможности рабочего стола Windows. Если Lync Server 2013 не находит это программное обеспечение на сервере, вам будет предложено установить его, а затем необходимо перезапустить сервер, чтобы завершить установку.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

