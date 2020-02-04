---
title: Создание и изменение коллекции параметров конфигурации Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Создание и изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

При установке сервера Lync Server вы получаете глобальную коллекцию параметров Lync Phone Edition. Эти параметры применяются ко всем устройствам, на которых работает Lync Phone Edition в развертывании. Вы можете в любое время изменить эти параметры. Вы также можете настроить новый набор параметров, которые применяются к устройствам на определенном сайте. Параметры сайта имеют приоритет над глобальными параметрами.

Параметры конфигурации включают имя коллекции, область (Global или site), параметр безопасности SIP, уровень ведения журнала, уровень обслуживания голоса (QoS), параметр блокировки телефона и данные блокировки телефона, то есть как долго a) разблокировки персональный идентификационный номер ( ПИН-код) должен быть и b) телефон не оставался бездействиям, прежде чем он будет заблокирован.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Создание коллекции параметров конфигурации Lync Phone Edition или изменение параметров для существующей коллекции

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации устройства** .

4.  На странице **Конфигурация устройства** выполните одно из указанных ниже действий.
    
      - Чтобы создать коллекцию параметров конфигурации Lync Phone Edition, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, проверьте параметры по умолчанию и, если нужно, внесите необходимые изменения.
    
      - Чтобы изменить параметры в существующей коллекции, щелкните ее, выберите в меню **Правка** команду **Показать подробности**и внесите необходимые изменения.
        
        <div>
        

        > [!TIP]
        > Чтобы вернуться к использованию параметров по умолчанию для глобальной коллекции, щелкните глобальную коллекцию, выберите в меню <STRONG>Правка</STRONG> команду <STRONG>Удалить</STRONG>, а затем нажмите кнопку <STRONG>ОК</STRONG>. Это не приведет к удалению глобальной коллекции; оно просто восстанавливает значения по умолчанию.

        
        </div>

5.  Нажмите **Исполнить**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание новых параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell

Вы можете создавать параметры конфигурации Lync Phone Edition (только на уровне сайта) с помощью Windows PowerShell и командлета **New-ксукфонеконфигуратион** . Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Создание новых параметров конфигурации Lync Phone Edition, использующих значения по умолчанию

  - Эта команда создает новый набор параметров конфигурации телефона в UC для сайта Redmond.
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Изменение одного значения свойства при создании новых параметров конфигурации Lync Phone Edition

  - Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров настройки телефонной связи UC, которая по умолчанию требует блокировки на телефоне, используйте такую команду:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Изменение нескольких значений свойства при создании новых параметров конфигурации Lync Phone Edition

  - Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, эта команда обеспечивает принудительную блокировку телефона, а также задает минимальную длину ПИН-кода в 8 цифр.
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Подробности можно найти в разделе [New-ксукфонеконфигуратион](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>См. также


[Удаление существующей коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Настройка параметров безопасности для Lync Phone Edition в Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Принудительная Блокировка телефона в Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

