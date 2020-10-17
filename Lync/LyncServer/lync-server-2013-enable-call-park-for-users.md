---
title: 'Lync Server 2013: включение парковки вызовов для пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528786"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Включение парковки вызовов для пользователей в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-11_

Пользователи не могут приостанавливать вызовы и получать приостановленные звонки до тех пор, пока они не будут включены в политику голосовых вызовов.

<div>


> [!NOTE]  
> По умолчанию парковки вызовов отключен для всех пользователей.



</div>

Можно включить приостановку вызовов в глобальной области, на уровне сайта или на уровне пользователя. Уровень пользователя имеет приоритет перед уровнем сайта, а тот в свою очередь — перед глобальным уровнем. Если у вас есть несколько политик голосовой связи, ознакомьтесь со всеми политиками, чтобы включить приостановку вызовов, а не только глобальную политику.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Использование панели управления Lync Server для включения парковки вызовов для пользователей

1.  Войдите на компьютер в качестве члена группы **RTCUniversalServerAdmins** или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.

4.  Перейдите на вкладку **Политика голосовой связи**.

5.  Дважды щелкните существующую политику голосовой связи, чтобы открыть диалоговое окно **Изменение политики голосовой связи**.

6.  В разделе **Функции звонков** установите флажок **Включить Парковку вызовов**.

7.  Чтобы сохранить политику голосовой связи, нажмите кнопку **ОК**.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Использование командлетов для включения парковки вызовов для пользователей

1.  Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполняем
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Например, чтобы включить приостановку вызовов для глобальной политики голосовой связи по умолчанию:
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>См. также


[Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

