---
title: 'Lync Server 2013: Настройка параметров безопасности для Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Улучшите безопасность устройств с Lync Phone Edition, используя настройки безопасности SIP и параметры блокировки телефона.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Настройка параметров безопасности для Lync Phone Edition

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация устройства**.

4.  На странице **Конфигурация устройства** в списке конфигураций устройств дважды щелкните конфигурацию, для которой вы хотите изменить параметры безопасности.

5.  В разделе **изменение конфигурации устройства**в **системе безопасности SIP**укажите уровень безопасности SIP. Уровень по умолчанию — **High**, поэтому мы рекомендуем использовать.

6.  В диалоговом окне **изменение конфигурации устройства**в разделе **Блокировка телефона**установите или снимите флажок **Принудительная Блокировка устройства** (выбрано по умолчанию) и укажите минимальную длину PIN-кода (по умолчанию) и период ожидания (по умолчанию — по 5 минутам). Мы рекомендуем использовать эти значения по умолчанию или увеличив длину PIN-кода и (или) уменьшить период ожидания.
    
    <div>
    

    > [!NOTE]  
    > Подробнее смотрите в разделе <A href="lync-server-2013-enforce-phone-locking.md">принудительное использование блокировки телефона в Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Настройка параметров безопасности для телефонов Lync Phone Edition с помощью командлетов Windows PowerShell

Параметры безопасности можно управлять с помощью командной консоли Lync Server Management Shell и командлета **Get-ксукфонеконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-modify-the-sip-security-mode"></a>Изменение режима безопасности SIP

  - Эта команда задает средний уровень Сипсекуритимоде для глобальной коллекции параметров телефонной связи UC. Также можно установить низкий или высокий уровень безопасности SIP (значение по умолчанию).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Изменение минимальной длины PIN-кода

  - В этом примере все параметры телефонной связи по УНИКАЛЬности изменяются для использования минимальной длины в 7 цифр.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Подробности можно найти в [статьях Get-ксукфонеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

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

