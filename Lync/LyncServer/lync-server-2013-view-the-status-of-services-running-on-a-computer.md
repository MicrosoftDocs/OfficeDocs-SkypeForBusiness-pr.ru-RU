---
title: 'Lync Server 2013: Просмотр состояния служб, запущенных на компьютере'
description: 'Lync Server 2013: Просмотр состояния служб, запущенных на компьютере.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22aeb13f2beb5d3b0ee5eec8109eceeb14e40213
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571355"
---
# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Просмотр состояния служб, запущенных на компьютере в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Вы можете использовать панель управления Lync Server 2013 для просмотра всех служб, запущенных на определенном компьютере в вашей топологии Lync Server, и просмотра состояния каждой службы.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>To view the status of services running on a computer

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  In the left navigation bar, click **Topology**.

4.  На странице **Состояние** отсортируйте список или выполните по нему поиск, чтобы найти интересующий вас компьютер, а затем щелкните имя этого компьютера.

5.  Do any of the following:
    
      - To see the latest status of services running on the computer, click **Get service status**.
    
      - Чтобы просмотреть список конкретных служб, запущенных на компьютере, и состояние каждой из них, щелкните **Свойства**, а затем нажмите кнопку **Закрыть** для возврата в список.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Просмотр состояния службы с помощью командлетов Windows PowerShell

Вы также можете просмотреть состояние службы с помощью Windows PowerShell и командлета **Get – CsWindowsService** . Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-service-status"></a>Просмотр состояния службы

  - Чтобы просмотреть состояние службы на компьютере, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    Эта команда возвращает следующую информацию:
    
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

Дополнительные сведения см. в статье [Get – CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).

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

