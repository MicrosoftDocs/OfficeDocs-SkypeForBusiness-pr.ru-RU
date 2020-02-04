---
title: Создание или изменение коллекции параметров конфигурации клиентской версии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Создание и изменение семейства параметров конфигурации клиентской версии в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Параметры конфигурации используются для включения и отключения управления версиями клиентов. Конфигурация глобальной клиентской версии устанавливается вместе с Lync Server и используется для включения или отключения управления версиями на клиенте для всего развертывания сервера. Вы также можете настроить параметры конфигурации клиента для отдельных сайтов. Вы можете создавать и изменять параметры конфигурации клиентской версии из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.

<div>


> [!NOTE]
> Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Создание и изменение параметров конфигурации клиентской версии с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации версии клиента** .

4.  На странице **Configuration Version (версия клиента** ) выполните указанные ниже действия.
    
      - Чтобы создать новую конфигурацию, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК** и обновите параметры.
    
      - Чтобы изменить конфигурацию, выберите ее, нажмите кнопку **изменить**, щелкните **Показать подробности**и внесите изменения в параметры.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание и изменение параметров конфигурации клиентской версии с помощью командлетов Windows PowerShell

Вы можете создать параметры конфигурации клиентской версии с помощью командлета **New-ксклиентверсионконфигуратион** и изменить их с помощью командлета **Set-ксклиентверсионконфигуратион** . Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Создание коллекции параметров конфигурации клиентской версии

  - Следующая команда создает новую коллекцию параметров конфигурации для версии клиента, примененную к сайту Redmond. В этом примере управление версиями клиента отключено для сайта Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Включение управления версиями на сайте

  - Эта команда включает управление версиями клиентов для сайта Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Отключение управления версиями клиента во всей Организации

  - В этом примере управление версиями клиента отключено для всех параметров конфигурации клиентской версии, используемых в Организации.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Дополнительные сведения можно найти в разделе справки по командлетам [New-ксклиентверсионконфигуратион](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) и [ксклиентверсионконфигуратион](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

