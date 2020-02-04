---
title: 'Lync Server 2013: дополнительные требования к программному обеспечению'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Дополнительные требования к программному обеспечению для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-12-08_

В дополнение к требованиям к оборудованию и операционной системе для серверных платформ Lync Server 2013 требует установки дополнительного программного обеспечения на серверах, которые вы развертываете.

<div>


> [!NOTE]  
> Сведения о требованиях к платформе для серверов Lync Server можно найти в разделе <A href="lync-server-2013-server-hardware-platforms.md">аппаратные платформы сервера для Lync server 2013</A> и <A href="lync-server-2013-server-and-tools-operating-system-support.md">серверных и инструментальных средств, поддерживаемых операционной системой в Lync Server 2013</A>. Дополнительные сведения о требованиях к системе для клиентских компьютеров и устройств можно найти <A href="lync-server-2013-planning-for-clients-and-devices.md">в разделе Планирование клиентов и устройств в Lync Server 2013</A> в документации по планированию. Сведения о требованиях к программному обеспечению для администрирования описаны <A href="lync-server-2013-administrative-tools-software-requirements.md">в разделе Требования к программному обеспечению для администраторов в Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Дополнительное программное обеспечение, необходимое для всех внутренних серверных ролей

В этом разделе перечислены программы, необходимые для всех внутренних ролей сервера, которые являются всеми ролями сервера Lync Server, кроме пограничного сервера. Требования к пограничным серверам и пулам Edge перечислены ниже в разделе **дополнительное программное обеспечение для пограничного сервера**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

На каждом сервере, на котором работает Lync Server 2013, должны быть установлены правильные выпуски Windows PowerShell 3,0. Подробные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Платформа Microsoft .NET Framework 4.5.

Lync Server требует Microsoft .NET Framework 4,5 для всех внутренних серверных ролей и на любом компьютере, на котором выполняются средства администрирования сервера Lync Server или Microsoft Lync Server 2013; средство планирования. Для Lync Server 2013 необходимо вручную установить 64-разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013. Чтобы установить ее вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Установка Microsoft .NET Framework 4,5 на серверах под управлением Windows Server 2012

При установке Microsoft .NET Framework 4,5 на сервер, на котором работают Lync Server 2013 и Windows Server 2012, необходимо выполнить одно из дополнительных действий. После установки .NET Framework 4,5 Используйте Диспетчер серверов для установки активации HTTP.

**Установка активации .NET 4,5 HTTP в Windows Server 2012**

1.  В меню **Пуск** выберите пункт **программы**, а затем — **Администрирование**, а затем — **Диспетчер серверов**.

2.  В диспетчере серверов в разделе **Сводка по компонентам**выберите **Добавить функции**.

3.  Разверните **.NET Framework 4,5**.

4.  Выберите **Активация WCF** , если она еще не выбрана. Затем выберите **Активация HTTP**.

5.  Нажмите кнопку **Далее** и следуйте инструкциям, чтобы завершить установку.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Для поддержки сценариев проверки подлинности сервера и **сервера в Lync** Server 2013 необходимо установить Windows Identity Foundation. Для Windows Server 2008 R2 и Windows Server 2012 требуется выполнить различные процедуры для установки Windows Identify Foundation. Выберите серверную операционную систему из следующего списка:

  - Windows Server 2008 R2 для Windows Server 2008 R2 — убедитесь, что она уже установлена на вашем компьютере. Для этого выберите элемент **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **удостоверение для Windows (KB974405)**. Подробнее об установке Windows Identity Foundation можно узнать [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)в статье.

  - Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation. В **мастере добавления ролей и компонентов**в диспетчере серверов выберите **компоненты**. В списке выберите **Windows Identity Foundation 3,5** . Нажмите кнопку **Далее**, а затем — **установить**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Дополнительное программное обеспечение для всех серверов переднего плана и стандартных серверов выпусков

На всех серверах переднего плана и стандартных серверах выпусков также должны выполняться службы IIS с определенными модулями. Кроме того, все серверы переднего плана и серверы стандартных выпусков, для которых развернута Конференц-связь, приложение для присоединения к приостановке, объявление и группа ответа, должны запускать среду выполнения формата Windows Media

<div>

## <a name="internet-information-services-iis"></a>Службы IIS

Для серверов переднего плана и стандартных серверов выпусков должны выполняться службы IIS со следующими модулями:

  - Статическое содержимое

  - Документ по умолчанию

  - Ошибки HTTP

  - ASP.NET

  - Расширяемость .NET

  - Расширения ISAPI (Internet Server API)

  - Фильтры ISAPI

  - Ведение журнала HTTP

  - Средства ведения журналов

  - Трассировка

  - Проверка подлинности Windows

  - Фильтрация запросов

  - Сжатие статического содержимого

  - Сжатие динамического содержимого

  - Консоль управления IIS

  - Сценарии и средства управления для служб IIS

  - Анонимная проверка подлинности (устанавливается по умолчанию при установке IIS).

  - Проверка подлинности с сопоставлением сертификатов клиентов

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Среда выполнения формата Windows Media и возможности рабочего стола Windows

**Возможности рабочего стола Windows** Все серверы переднего плана и стандартные серверы выпусков, на которых будет развернута конференция, должны иметь установленную среду выполнения формата Windows Media (за исключением Windows Server 2012, установленной в составе рабочего стола Windows. Для Windows Server 2012 требуется Microsoft Media Foundation. Для работы с файлами Windows Media Audio (WMA), которые воспринимаются приложениями для приема, объявления и ответа, воспроизводится для объявлений и музыкальных файлов, которые требуются в среде выполнения формата Windows Media.

Перед установкой Lync Server 2013 рекомендуется установить возможности рабочего стола Windows. Если Lync Server 2013 не находит это программное обеспечение на сервере, вам будет предложено установить его, а затем необходимо перезапустить сервер, чтобы завершить установку.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Дополнительное программное обеспечение для серверов переднего плана и серверов Standard Edition, работающих под управлением Windows Server 2012

Для серверов с внешними интерфейсами требуется .NET 3,5, который не установлен по умолчанию в Windows Server 2012. Чтобы установить его, вставьте установочный носитель Windows Server 2012 в дисковод D и введите следующую команду:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Подробные сведения об установке .NET 3,5 на серверах под управлением Windows Server 2012 можно найти в разделе "вопросы по <https://go.microsoft.com/fwlink/p/?linkid=275032>развертыванию Microsoft .net Framework 3,5".

</div>

<div>

## <a name="additional-software-for-directors"></a>Дополнительное программное обеспечение для режиссеров

Режиссеры должны запускать службы IIS со следующими модулями:

  - Статическое содержимое

  - Документ по умолчанию

  - Ошибки HTTP

  - ASP.NET

  - Расширяемость .NET

  - Расширения ISAPI (Internet Server API)

  - Фильтры ISAPI

  - Ведение журнала HTTP

  - Средства ведения журналов

  - Трассировка

  - Проверка подлинности Windows

  - Фильтрация запросов

  - Сжатие статического содержимого

  - Консоль управления IIS

  - Сценарии и средства управления для служб IIS

  - Анонимная проверка подлинности (устанавливается по умолчанию при установке IIS).

  - Проверка подлинности с сопоставлением сертификатов клиентов

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Дополнительное программное обеспечение для серверов клиентского чата с постоянным подключением

На серверах, использующих сохраняемый чат, должны быть запущены очередь сообщений (также называемая MSMQ), которая является компонентом Windows Server.

Чтобы узнать, как включить MSMQ, [нажмите здесь.](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Дополнительное программное обеспечение для пограничных серверов

Для пограничных серверов требуется следующее программное обеспечение:

  - На каждом сервере, на котором работает Lync Server 2013, должны быть установлены правильные выпуски Windows PowerShell 3,0. Подробные сведения можно найти в разделе [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Для Lync Server требуется Microsoft .NET Framework 4,5. Для Lync Server 2013, установленного в Windows Server 2008 R2, перед установкой Lync Server 2013 необходимо вручную установить версию 64-bit Microsoft .NET Framework 4,5 на сервере. Чтобы установить ее вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Для поддержки сценариев проверки подлинности сервера и **сервера в Lync** Server 2013 необходимо установить Windows Identity Foundation. Для Windows Server 2008 R2 и Windows Server 2012 требуется выполнить различные процедуры для установки Windows Identify Foundation. Выберите серверную операционную систему из следующего списка:
    
      - Windows Server 2008 R2 для Windows Server 2008 R2 — убедитесь, что она уже установлена на вашем компьютере. Для этого выберите элемент **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **удостоверение для Windows (KB974405)**. Подробнее об установке Windows Identity Foundation можно узнать [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)в статье.
    
      - Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation. В **мастере добавления ролей и компонентов**в диспетчере серверов выберите **компоненты**. В списке выберите **Windows Identity Foundation 3,5** . Нажмите кнопку **Далее**, а затем — **установить**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Не устанавливайте провайдеры многоуровневых соединителей на серверах мультимедиа

Не устанавливайте клиентское программное обеспечение сервера Microsoft Internet Security and Acceleration (ISA) или любое другое программное обеспечение, которое можно получить с любого другого поставщика многоуровневой службы (LSP), на любом сервере переднего плана или отдельном сервере. Установка этого программного обеспечения может привести к ухудшению производительности мультимедийного трафика.

</div>

<div>

## <a name="see-also"></a>См. также


[Программные требования для средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

