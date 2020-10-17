---
title: 'Lync Server 2013: Настройка параметров безопасности для Lync Phone Edition'
description: 'Lync Server 2013: Настройка параметров безопасности для Lync Phone Edition.'
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
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564355"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Помогите повысить безопасность устройств с Lync Phone Edition с помощью параметров безопасности SIP и параметров блокировки телефона.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Настройка параметров безопасности для Lync Phone Edition

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем элемент **Конфигурация устройств**.

4.  На странице **Конфигурация устройств** в списке конфигураций устройств дважды щелкните конфигурацию, для которой требуется изменить параметры безопасности.

5.  В разделе **Изменение конфигурации устройств** под заголовком **Безопасность SIP** укажите уровень безопасности SIP. По умолчанию установлен **высокий** уровень, который рекомендуется использовать.

6.  В окне **Изменение конфигурации устройств** в разделе **Блокировка телефона** установите или снимите флажок **Активировать блокировку устройства** (установлен по умолчанию) и указать минимальную длину ПИН-кода (6 символов по умолчанию) и период времени ожидания (10 минут по умолчанию). Рекомендуется использовать эти значения по умолчанию или увеличить длину ПИН-кода и уменьшить период времени ожидания.
    
    <div>
    

    > [!NOTE]  
    > Дополнительные сведения см <A href="lync-server-2013-enforce-phone-locking.md">в статье применение блокировки телефона в Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Настройка параметров безопасности для телефонов Lync Phone Edition с помощью командлетов Windows PowerShell

Для управления параметрами безопасности можно использовать командную консоль Lync Server и командлет **Get – CsUCPhoneConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-modify-the-sip-security-mode"></a>Изменение режима безопасности SIP

  - Эта команда задает для свойства SIPSecurityMode в глобальной коллекции параметров телефона UC значение Medium. Также можно задать значение Low или High (значение по умолчанию).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Изменение минимальной длины ПИН-кода

  - В этом примере параметры телефона изменяются, чтобы установить минимальную длину ПИН-кода в 7 символов.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Дополнительные сведения см. в статье [Get – CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

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

