---
title: 'Lync Server 2013: включение контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528766"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a>Включение контроля допуска звонков в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).

Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - [Get — CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set — CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove — CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>Включение службы контроля допуска звонков с помощью командной консоли Lync Server

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Включение службы контроля допуска звонков с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Network Configuration** (Параметры сети).

3.  Нажмите кнопку навигации **Global** (Глобальные).

4.  Выберите **Global** (Глобальные) в списке и затем в меню **Edit** (Изменить) выберите **Show Details** (Показать сведения).

5.  На странице **Edit Global Settings** (Изменение глобальных параметров) установите флажок **Enable call admission control** (Включить службу контроля допуска звонков).
    
    <div>
    

    > [!NOTE]  
    > Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок.

    
    </div>

6.  Щелкните **Commit** (Применить).

</div>

</div>

<span> </span>

</div>

</div>

</div>

