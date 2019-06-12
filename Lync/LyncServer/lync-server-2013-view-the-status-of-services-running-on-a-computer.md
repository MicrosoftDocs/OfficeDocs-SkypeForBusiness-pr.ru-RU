---
title: 'Lync Server 2013: Просмотр состояния служб, запущенных на компьютере'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Просмотр состояния служб, запущенных на компьютере в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Вы можете использовать панель управления Lync Server 2013 для просмотра всех служб, запущенных на определенном компьютере в топологии Lync Server, и посмотреть состояние каждой службы.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>Просмотр состояния служб, запущенных на компьютере

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **топология**.

4.  На странице **Status (состояние** ) отсортируйте или выполните поиск по мере необходимости, чтобы найти нужный вам компьютер, а затем щелкните имя компьютера.

5.  Выполните одно из указанных ниже действий.
    
      - Чтобы просмотреть последние сведения о состоянии служб, запущенных на компьютере, щелкните **получить состояние службы**.
    
      - Чтобы просмотреть список конкретных служб, запущенных на компьютере, и состояние каждой из них, нажмите кнопку **Свойства**, а затем — кнопку **Закрыть** , чтобы вернуться в список.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Просмотр состояния службы с помощью командлетов Windows PowerShell

Вы также можете просмотреть состояние службы с помощью Windows PowerShell и командлета **Get-ксвиндовссервице** . Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-service-status"></a>Просмотр состояния службы

  - Чтобы просмотреть состояние службы на компьютере, введите в командной консоли Lync Server такую команду, как показано ниже, и нажмите клавишу ВВОД.
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Этой командой возвращается информация, аналогичная следующим сведениям:
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

Подробности можно найти в [статьях Get-ксвиндовссервице](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

</div>

<div>

## <a name="see-also"></a>См. также


[Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

