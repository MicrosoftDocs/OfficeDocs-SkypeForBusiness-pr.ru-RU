---
title: 'Lync Server 2013: Включение управления допуском звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Включение управления допуском звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети CAC необходимо включить функцию CAC для обеспечения ограничения пропускной способности. Это можно сделать с помощью панели управления Lync Server.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Активация CAC с помощью панели управления Lync Server

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Конфигурация сети** , а затем — **Глобальная**.

4.  На **глобальной** странице щелкните **глобальную** конфигурацию.
    
    <div>
    

    > [!NOTE]  
    > Для любого развертывания Microsoft Lync Server 2013 можно настроить только одну сеть, поэтому в списке никогда не будет более одной конфигурации сети. Вы не можете переименовать глобальную конфигурацию.

    
    </div>

5.  В меню **Правка** щелкните **Подробнее**.

6.  На странице **изменение глобальных параметров** установите флажок **включить управление допуском звонков** , а затем нажмите кнопку **сохранить**.

При нажатии кнопки **зафиксировать**вы запускаете тест конфигурации. Диалоговое окно " **изменение глобальных параметров** " закроется и будет возвращено на **глобальную** страницу. Вы получите предупреждение о том, что в конфигурации сети обнаружены ошибки или несоответствия (например, если каждый регион не подключен к каждому из них через маршрут между регионами).

Если вы вносите изменения в конфигурацию сети, вы можете снова выполнить проверку, открыв глобальную конфигурацию и выбрав команду **Commit (сохранить**). Отключить CAC сначала не требуется: Оставьте флажок установленным, а затем нажмите кнопку **сохранить**. Это можно сделать в любое время, не внося каких – либо изменений в конфигурацию.

</div>

<div>

## <a name="see-also"></a>См. также


[Общие сведения об управлении допуском звонков в Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Планирование контроля допуска звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Настройка управления допуском звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-Кснетворкконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

