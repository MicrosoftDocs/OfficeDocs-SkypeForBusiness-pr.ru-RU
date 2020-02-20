---
title: Изменение действия по умолчанию для клиентов, которые явно не поддерживаются или не ограничены
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b33cdb0b2055c76d5a3fbfa1db893a1267318e8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Изменение действия по умолчанию для клиентов, которые явно не поддерживаются или не ограничены в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

В дополнение к указанию версии клиентов, которые вы хотите поддерживать в среде Lync Server 2013, можно также задать действие по умолчанию для клиентов, у которых еще не определена политика версий. Это позволяет ограничить версии клиентов, используемые в среде Lync Server, которые могут помочь управлять затратами, связанными с поддержкой нескольких версий клиентов.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Изменение действия по умолчанию для клиентов, которые явно не поддерживаются или ограничены

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Клиенты**, а затем щелкните **Конфигурация версии клиента**.

4.  На странице **Конфигурация версии клиента** дважды щелкните **Глобальная** в списке конфигураций.

5.  В диалоговом окне **Конфигурация версии клиента** убедитесь, что флажок **Включить управление версиями** установлен, а затем в поле **Действие по умолчанию** выберите один из следующих параметров:
    
      - **Разрешить**   клиенту выполнять вход в систему, если версия клиента не отвечает ни одному фильтру в списке **политик версий клиентов** .
    
      - **Block**   запрещает клиенту входить в систему, если версия клиента не отвечает ни одному фильтру в списке **политик версий клиентов** .
    
      - **Блокировать с URL-адресом**   запрещает клиенту входить в систему, если версия клиента не отвечает ни одному фильтру в списке **политик версий клиентов** , и включает сообщение об ошибке с URL-адресом, по которому можно загрузить более новую версию клиента.
    
      - **Разрешить с помощью URL-адреса**   позволяет клиенту выполнить вход, если версия клиента не отвечает какому-либо фильтру в списке **политик версий клиентов** , и добавить сообщение об ошибке с URL-адресом, по которому можно загрузить более новую версию клиента.

6.  Если выбран параметра **Блокировать с URL-адресом** введите URL-адрес загрузки клиента, который нужно включить в сообщение об ошибке, в поле ** URL-адрес**.

7.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Отключение управления версиями клиента

  - Чтобы отключить управление версиями и разрешить всем клиентам входить в систему независимо от версии клиента, снимите флажок **Включить управление версиями** флажок, а затем нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Изменение действия по умолчанию с помощью командлетов Windows PowerShell

Действие по умолчанию, выполняемое при попытке пользователя выполнить вход с использованием клиентов, которые не поддерживаются явно или запрещено политикой версий клиентов, может управляться с помощью интерфейса командной строки Windows PowerShell и командлета **Set – CsClientVersionPolicy** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Настройка действия по умолчанию для блокировки доступа

  - Следующая команда определяет действие по умолчанию для сайта Redmond как блокировку. Это приведет к блокировке регистрации любого клиента, для которого не существует правила конфигурации клиентской версии.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Настройка действия по умолчанию для разрешения доступа

  - В этом примере действием по умолчанию для сайта Redmond является разрешение. Это приведет к разрешению регистрации любого клиента, для которого не существует правила конфигурации клиентской версии.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Дополнительные сведения см. в разделе справки для командлета [Set – CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>См. также


[Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

