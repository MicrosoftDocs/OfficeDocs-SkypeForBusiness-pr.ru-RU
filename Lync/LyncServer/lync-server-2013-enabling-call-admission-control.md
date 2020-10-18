---
title: 'Lync Server 2013: включение контроля допуска звонков'
description: 'Lync Server 2013: включение контроля допуска звонков.'
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
ms.openlocfilehash: b2f5737f83a1965b920f2a23e1aabbbaec2af7b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572645"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Включение контроля допуска звонков в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Контроль допуска звонков — это сеть, состоящая из областей, узлов и подсетей, которая позволяет размещать ограничения на передачу аудио- и видеоданных на основе доступной пропускной способности. После настройки сети контроля допуска звонков необходимо включить контроль допуска звонков, чтобы ограничения пропускной способности вступили в силу. Для этого можно использовать панель управления Lync Server.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Включение контроля допуска звонков с панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Глобальная**.

4.  На странице **Глобальная** выберите конфигурацию **Глобальная**.
    
    <div>
    

    > [!NOTE]  
    > Для любого развертывания Microsoft Lync Server 2013 можно настроить только одну сеть, поэтому в списке не будет более одной конфигурации сети. Переименовать глобальную конфигурацию нельзя.

    
    </div>

5.  В меню **Правка** выберите пункт **Показать подробности**.

6.  На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков** и нажмите кнопку **Зафиксировать**.

При нажатии кнопки **Зафиксировать** запускается проверка конфигурации. Диалоговое окно **изменения глобальных параметров** закрывается, возвращая вас на страницу **Глобально**. Если в конфигурации будут обнаружены какие-либо ошибки или несоответствия, препятствующие ее корректной работе (например, если каждая область не связана с каждой другой областью промежуточным маршрутом), то вы получите предупреждение.

При внесении изменений в конфигурацию сети можно снова выполнить проверку правильности, открыв глобальную конфигурацию и нажав кнопку **Зафиксировать**. Предварительно отключать контроль допуска звонков не требуется: оставьте этот флажок установленным и нажмите **Зафиксировать**. Это можно делать в любое время даже без внесения изменений в конфигурацию.

</div>

<div>

## <a name="see-also"></a>См. также


[Обзор контроля допуска звонков в Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Планирование контроля допуска звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Настройка контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get — CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set — CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove — CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

