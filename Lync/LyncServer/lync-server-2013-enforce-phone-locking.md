---
title: 'Lync Server 2013: принудительное использование блокировки телефона'
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
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Принудительная Блокировка телефона в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Устройства Lync Phone Edition можно блокировать в целях обеспечения безопасности. Если вы используете блокировку телефона, устройство с Lync Phone Edition блокируется по истечении определенного периода времени. Когда телефон заблокирован, пользователь может звонить, но не может получить доступ к календарю, контактной информации, голосовой почте или звонкам либо использовать функцию поиска. Чтобы разблокировать телефон, пользователь введет PIN-код.

Для принудительного включения блокировки на телефоне включите и настройте ее с помощью панели управления Lync Server или командлетов Lync Server PowerShell. Вы можете включить блокировку на телефоне глобально или только на сайте, для которого она настроена.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Настройка и принудительное использование блокировки телефона

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Нажмите **Клиенты**и выберите **Конфигурация устройства**.

4.  На вкладке **Конфигурация устройства** в списке конфигураций устройств дважды щелкните конфигурацию, для которой вы хотите изменить параметры блокировки телефона.

5.  В диалоговом окне **изменение конфигурации устройства** убедитесь, что установлен флажок **Принудительная Блокировка устройства** .

6.  В поле **Минимальная длина ПИН-кода**введите значение по умолчанию для минимального числа цифр, которые должен содержать ПИН-код для разблокировки, или укажите новое значение. Диапазон длины PIN-кода состоит из 4 – 15 цифр, а значение по умолчанию — Six.

7.  В параметрах времени ожидания для **телефонного закрепления**введите значение по умолчанию для минимальной продолжительности времени, по истечении которого блокируется Телефон, или укажите новое значение. Диапазон времени ожидания равен от 0 до 60 минут, а значение по умолчанию — 10. Введите значение в формате чч: мм: СС.

8.  Нажмите **Исполнить**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Принудительная Блокировка телефона с помощью командлетов Windows PowerShell

С помощью командлета Set-Ксукфонеконфигуратион можно принудительно использовать блокировку телефона. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-enable-phone-locking"></a>Включение блокировки телефона

  - Следующая команда включает блокировку на телефоне для сайта Redmond. Чтобы отключить блокировку на телефоне, установите для свойства Енфорцефонелокк значение false ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Включение блокировки телефона и изменение времени ожидания блокировки телефона

  - Эта команда включает блокировку телефона, а также задает время ожидания блокировки в 30 минут.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Включение блокировки телефона в рамках всей Организации

  - В этом примере функция блокировки телефона включена для всех параметров конфигурации телефона UC, используемых в Организации.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Set-ксукфонеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

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

