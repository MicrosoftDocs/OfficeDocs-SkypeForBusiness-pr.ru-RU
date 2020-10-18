---
title: 'Lync Server 2013: принудительная Блокировка телефона'
description: 'Lync Server 2013: принудительная Блокировка телефона.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575605"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a>Принудительная Блокировка телефона в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Устройства Lync Phone Edition могут быть заблокированы в целях обеспечения безопасности. Если вы настраиваете блокировку телефона, устройство, на котором работает Lync Phone Edition, будет заблокировано по истечении определенного периода времени. Когда телефон заблокирован, пользователь может совершать вызовы, но не может получать доступ к календарю и контактным данным, голосовой почте или журналам вызовов или использовать поиск. Чтобы разблокировать телефон, пользователь вводит ПИН-код.

Чтобы применить блокировку телефона, включите и настройте ее с помощью командлетов Lync Server Control Panel или Lync Server PowerShell. Вы можете принудительно включить блокировку по телефону на глобальном уровне или только на сайте, для которого она настроена.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Настройка и принудительная Блокировка телефона

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Щелкните элемент **Clients** (Клиенты) и затем элемент **Device Configuration** (Конфигурация устройства).

4.  В списке конфигураций на вкладке **Device Configuration** (Конфигурация устройства) дважды щелкните конфигурацию, для которой хотите изменить параметры блокировки телефона.

5.  В диалоговом окне **Edit Device Configuration** (Изменение конфигурации устройства) убедитесь, что установлен флажок **Enforce device locking** (Активировать блокировку устройства).

6.  В поле **Минимальная длина ПИН-кода**примите значение по умолчанию для минимального числа цифр, которые должен содержать ПИН-код для разблокировки, или укажите новое значение. Длина ПИН-кода составляет от четырех до 15 цифр, а значение по умолчанию — 6.

7.  В поле **время ожидания блокировки телефона**примите значение по умолчанию для минимального интервала времени до блокировки телефона или укажите новое значение. Диапазон времени ожидания составляет от 0 до 60 минут, а значение по умолчанию — 10. Введите значение в формате чч: мм: СС.

8.  Щелкните **Исполнить**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Принудительная Блокировка телефона с помощью командлетов Windows PowerShell

Блокировка телефона может быть применена с помощью командлета Set-CsUCPhoneConfiguration. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-phone-locking"></a>Включение блокировки телефона

  - Следующая команда служит для включения блокировки телефона для сайта Redmond. Чтобы отключить блокировку телефона, установите для свойства EnforcePhoneLock значение False ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Включение блокировки телефона и изменение времени ожидания для блокировки телефона

  - Эта команда служит для включения блокировки телефона, а также для установки значения таймаута блокировки телефона "30 минут".
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Включение блокировки телефона в пределах организации

  - В этом примере блокировка телефона включена для всех параметров конфигурации телефонной линии UC, используемых в организации.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>См. также


[Управление проверкой подлинности Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

