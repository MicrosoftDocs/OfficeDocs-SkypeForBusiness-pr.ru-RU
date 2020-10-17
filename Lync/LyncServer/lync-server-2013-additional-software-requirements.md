---
title: 'Lync Server 2013: дополнительные требования к программному обеспечению'
description: 'Lync Server 2013: дополнительные требования к программному обеспечению.'
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
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553045"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a>Дополнительные требования к программному обеспечению для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-12-08_

В дополнение к требованиям к оборудованию и операционной системе для серверных платформ, Lync Server 2013 требует установки дополнительного программного обеспечения на развертываемых серверах.

<div>


> [!NOTE]  
> Дополнительные сведения о требованиях к платформе для серверов, на которых работает Lync Server, можно найти в статье <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools support в Lync Server 2013</A>. Для получения дополнительных сведений о требованиях к системе для клиентских компьютеров и устройств ознакомьтесь со статьей <A href="lync-server-2013-planning-for-clients-and-devices.md">планирование для клиентов и устройств в Lync Server 2013</A> в документации по планированию. Дополнительные сведения о требованиях к программному обеспечению для средств администрирования приведены <A href="lync-server-2013-administrative-tools-software-requirements.md">в статье требования к программному обеспечению для средств администрирования в Lync Server 2013</A>.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>Дополнительное программное обеспечение, необходимое для всех внутренних ролей сервера

В этом разделе перечислены программное обеспечение, необходимое для всех внутренних серверных ролей, которые являются ролями сервера Lync Server, кроме пограничного сервера. Требования к пограничным серверам и пограничным пулам перечислены далее в этом разделе под заголовком **дополнительное программное обеспечение для пограничных серверов**.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

На каждом сервере, на котором работает Lync Server 2013, должна быть установлена правильная версия Windows PowerShell 3,0. Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server требует Microsoft .NET Framework 4,5 для всех внутренних ролей сервера и на любом компьютере, на котором будут выполняться средства администрирования Lync Server или Microsoft Lync Server 2013, средство планирования. Для Lync Server 2013 необходимо вручную установить 64 – разрядную версию Microsoft .NET Framework 4,5 на сервере перед установкой Lync Server 2013. Чтобы установить его вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Установка Microsoft .NET Framework 4.5 на серверах под управлением Windows Server 2012

При установке Microsoft .NET Framework 4,5 на серверах, на которых будут работать Lync Server 2013 и Windows Server 2012, необходимо выполнить одно из дополнительных действий. После установки пакета .NET Framework 4.5 используйте диспетчер сервера для установки службы HTTP-активации.

**Установка службы HTTP-активации .NET 4.5 в ОС Windows Server 2012**

1.  В меню **Пуск** последовательно выберите пункты **Программы**, **Администрирование**, **Диспетчер сервера**.

2.  В диспетчере сервера в области **Сводка компонентов** выберите **Добавить компоненты**.

3.  Разверните **.NET Framework 4.5**.

4.  Выберите пункт **WCF-активация**, если он еще не выбран. Затем выберите **HTTP-активация**.

5.  Нажмите кнопку **Далее** и следуйте инструкциям для завершения установки.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

**Windows Identity Foundation** в Lync Server 2013 требует установки Windows Identity Foundation для поддержки сценариев проверки подлинности сервера и сервера. Windows Server 2008 R2 и Windows Server 2012 требуют различных процедур установки Windows Identify Foundation. Выберите серверную операционную систему из следующего списка:

  - Windows Server 2008 R2 для Windows Server 2008 R2 убедитесь, что она уже установлена на вашем компьютере. Для этого откройте раздел **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **Идентификация Windows Identity Foundation (KB974405)**. Подробные сведения об установке Windows Identity Foundation можно найти в разделе [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .

  - Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation. В **мастере добавления ролей и компонентов**диспетчера серверов выберите **компоненты**. В списке выберите **Windows Identity Foundation 3,5** . Нажмите кнопку **Далее**, а затем — **установить**.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>Дополнительное программное обеспечение для всех интерфейсных серверов и серверов Standard Edition

На всех серверах переднего плана и серверах Standard Edition также должны выполняться службы IIS с определенными модулями. Кроме того, для всех серверов переднего плана и серверов Standard Edition, на которых развернуты конференции, приложения для приостановки вызовов, объявления или группы ответа, необходимо запустить среду выполнения формата Windows Media.

<div>

## <a name="internet-information-services-iis"></a>IIS

Для серверов переднего плана и серверов Standard Edition должны выполняться службы IIS со следующими модулями:

  - Статическое содержимое

  - Документ по умолчанию

  - ошибки HTTP;

  - ASP.NET

  - расширяемость .NET;

  - расширения ISAPI;

  - Фильтры ISAPI

  - ведение журнала HTTP;

  - средства ведения журнала;

  - Образца

  - Проверка подлинности Windows

  - Фильтрация запросов

  - Сжатие статического содержимого

  - Сжатие динамического содержимого

  - Консоль управления IIS

  - сценарии и средства управления IIS;

  - анонимный доступ (устанавливается по умолчанию при установке служб IIS);

  - проверка подлинности с сопоставлением сертификата клиента.

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Среда выполнения формата Windows Media и возможности рабочего стола Windows

**Возможности рабочего стола Windows** На всех серверах переднего плана и серверах Standard Edition, на которых будет развернута конференция, должна быть установлена среда выполнения Windows Media Format Runtime, которая, кроме Windows Server 2012, установлена в составе Windows Desktop Experience. Для Windows Server 2012 требуется Microsoft Media Foundation. Компонент Windows Media Format Runtime необходим для воспроизведения файлов Windows Media Audio (WMA-файлов) приложениями "Парковка вызовов", "Оповещение" и "Группа ответа" при проигрывании оповещений и музыки.

Рекомендуется установить возможности рабочего стола Windows перед установкой Lync Server 2013. Если Lync Server 2013 не находит это программное обеспечение на сервере, будет предложено установить его, а затем необходимо перезапустить сервер для завершения установки.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Дополнительное программное обеспечение для серверов переднего плана и серверов Standard Edition под управлением Windows Server 2012

Для серверов переднего плана требуется .NET 3,5, который не устанавливается по умолчанию в Windows Server 2012. Чтобы установить ее, вставьте установочный носитель Windows Server 2012 в диск D и введите следующее:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Подробные сведения об установке .NET 3,5 на серверах под управлением Windows Server 2012 приведены в разделе "рекомендации по развертыванию Microsoft .NET Framework 3,5" <https://go.microsoft.com/fwlink/p/?linkid=275032> .

</div>

<div>

## <a name="additional-software-for-directors"></a>Дополнительное программное обеспечение для Директоров

Директоры должны запускать службы IIS со следующими модулями:

  - Статическое содержимое

  - Документ по умолчанию

  - ошибки HTTP;

  - ASP.NET

  - расширяемость .NET;

  - расширения ISAPI;

  - Фильтры ISAPI

  - ведение журнала HTTP;

  - средства ведения журнала;

  - Образца

  - Проверка подлинности Windows

  - Фильтрация запросов

  - сжатие статического содержимого;

  - консоль управления IIS;

  - сценарии и средства управления IIS;

  - анонимный доступ (устанавливается по умолчанию при установке служб IIS);

  - проверка подлинности с сопоставлением сертификата клиента.

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>Дополнительное программное обеспечение для интерфейсных серверов сохраняемого чата

На интерфейсных серверах сохраняемого чата должен работать компонент Windows Server, MSMQ.

Для получения сведений о включении MSMQ [щелкните здесь.](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>Дополнительное программное обеспечение для пограничных серверов

Для пограничных серверов требуется следующее программное обеспечение:

  - На каждом сервере, на котором работает Lync Server 2013, должна быть установлена правильная версия Windows PowerShell 3,0. Дополнительные сведения см. в статье [Установка Windows PowerShell 3,0 для Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).

  - Для Lync Server требуется Microsoft .NET Framework 4,5. Для Lync Server 2013, установленного в Windows Server 2008 R2, перед установкой Lync Server 2013 необходимо вручную установить выпуск 64 – bit для Microsoft .NET Framework 4,5 на сервере. Чтобы установить его вручную, скачайте Microsoft .NET 4,5 Framework из центра загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - **Windows Identity Foundation** в Lync Server 2013 требует установки Windows Identity Foundation для поддержки сценариев проверки подлинности сервера и сервера. Windows Server 2008 R2 и Windows Server 2012 требуют различных процедур установки Windows Identify Foundation. Выберите серверную операционную систему из следующего списка:
    
      - Windows Server 2008 R2 для Windows Server 2008 R2 убедитесь, что она уже установлена на вашем компьютере. Для этого откройте раздел **Установка и удаление программ**, **Просмотрите установленные обновления**и найдите в разделе **Windows** **Идентификация Windows Identity Foundation (KB974405)**. Подробные сведения об установке Windows Identity Foundation можно найти в разделе [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .
    
      - Windows Server 2012 для Windows Server 2012 вы используете **Диспетчер серверов** для установки Windows Identity Foundation. В **мастере добавления ролей и компонентов**диспетчера серверов выберите **компоненты**. В списке выберите **Windows Identity Foundation 3,5** . Нажмите кнопку **Далее**, а затем — **установить**.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>Не устанавливайте многоуровневые поставщики услуг на серверах-посредниках

Не устанавливайте клиентское программное обеспечение сервера Microsoft Internet Security and Acceleration (ISA) или любое другое программное обеспечение (LSP) на всех серверах переднего плана или отдельных серверах-посредниках. Установка этого ПО может привести к снижению скорости передачи трафика на сервере-посреднике.

</div>

<div>

## <a name="see-also"></a>См. также


[Требования к программному обеспечению для средств администрирования в Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

