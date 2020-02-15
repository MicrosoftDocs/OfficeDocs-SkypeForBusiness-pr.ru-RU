---
title: Создание или изменение коллекции параметров конфигурации Lync Phone Edition
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
ms.openlocfilehash: 23248517bc0bba55c600e732c0a7edb96f468713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Создание или изменение коллекции параметров конфигурации Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

При установке Lync Server вы получаете глобальную коллекцию параметров Lync Phone Edition. Эти параметры применяются ко всем устройствам с Lync Phone Edition в развертывании. Вы можете изменить эти настройки в любое время. Вы также можете настроить новую коллекцию параметров, которая применяется к устройствам в определенном узле. Параметры узла имеют более высокий приоритет, чем глобальные параметры.

Параметры конфигурации состоят из имени коллекции, области (глобальная или узел), параметра безопасности SIP, уровня ведения журнала, уровня качества обслуживания (QoS) голосовой связи, параметра блокировки телефона и сведений о блокировке, т. е. а) каким по длине должен быть ПИН-код для разблокировки и б) как долго телефон может быть неактивным до автоматической блокировки.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Создание коллекции параметров конфигурации Lync Phone Edition или изменение параметров для существующей коллекции

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Клиенты**, затем нажмите кнопку навигации **Конфигурация устройства**.

4.  На странице **Конфигурация устройства** выполните одно из следующих действий.
    
      - Чтобы создать новую коллекцию параметров конфигурации Lync Phone Edition, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, просмотрите параметры по умолчанию и, если необходимо, внесите изменения.
    
      - Чтобы изменить параметры существующей коллекции, щелкните ее, откройте меню **Правка**, щелкните **Показать подробности** и внесите изменения.
        
        <div>
        

        > [!TIP]
        > Чтобы вернуться к параметрам глобальной коллекции по умолчанию, откройте меню <STRONG>Правка</STRONG>, щелкните <STRONG>Удалить</STRONG> и нажмите кнопку <STRONG>ОК</STRONG>. При этом глобальная коллекция не удаляется, просто восстанавливаются настройки по умолчанию.

        
        </div>

5.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание новых параметров конфигурации Lync Phone Edition с помощью командлетов Windows PowerShell

Вы можете создать параметры конфигурации Lync Phone Edition (только на уровне сайта) с помощью Windows PowerShell и командлета **New-CsUCPhoneConfiguration** . Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Создание новых параметров конфигурации Lync Phone Edition, использующих значения по умолчанию

  - Эта команда создает новый набор параметров конфигурации телефона UC для сайта Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Так как в предыдущей команде не были указаны параметры (кроме обязательного параметра Identity), новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех свойств.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Изменение значения отдельного свойства при создании новых параметров конфигурации Lync Phone Edition

  - Чтобы создать параметры, использующие разные значения свойств, просто укажите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации телефона UC, которые требуют блокировки телефона по умолчанию, используйте следующую команду:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Изменение значений нескольких свойств при создании новых параметров конфигурации Lync Phone Edition

  - Значения нескольких свойств можно изменить, указав несколько параметров. Например, следующая команда применяет блокировку телефона и также задает минимальную длину ПИН-кода (8 разрядов):
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Дополнительные сведения см. в разделе [New – CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).

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

