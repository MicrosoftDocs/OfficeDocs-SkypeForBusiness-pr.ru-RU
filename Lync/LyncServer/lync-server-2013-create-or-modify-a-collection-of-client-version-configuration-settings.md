---
title: Создание или изменение коллекции параметров конфигурации версий клиентов
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
ms.openlocfilehash: 4d4a3b270ecf35d9fbc33accd8c46909a6e8755b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Создание или изменение коллекции параметров конфигурации версий клиентов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Параметры конфигурации используются для включения и отключения управления версиями клиентов. Конфигурация глобальной версии клиента устанавливается вместе с Lync Server и используется для включения или отключения управления версиями клиентов для всего развертывания сервера. Кроме того, можно настроить параметры конфигурации версий клиентов для отдельных сайтов. Вы можете создавать или изменять параметры конфигурации версий клиентов с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>


> [!NOTE]
> Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Создание или изменение параметров конфигурации версий клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .

4.  На странице **Конфигурация версии клиента** выполните следующие действия:
    
      - Чтобы создать новую конфигурацию, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК** и обновите параметры.
    
      - Чтобы изменить конфигурацию, выберите конфигурацию, нажмите кнопку **изменить**, щелкните **Показать сведения**и внесите изменения в параметры.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание или изменение параметров конфигурации версий клиентов с помощью командлетов Windows PowerShell

Вы можете создать параметры конфигурации версий клиентов с помощью командлета **New – CsClientVersionConfiguration** и изменить их с помощью командлета **Set – CsClientVersionConfiguration** . Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Создание новой коллекции параметров конфигурации версий клиентов

  - Следующая команда создает новую коллекцию параметров конфигурации версий клиентов, применяемых к сайту Redmond. В этом примере управление версиями клиентов отключено для сайта Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Включение управления версиями клиентов для сайта

  - Эта команда включает управление версиями клиентов для сайта Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Отключение управления версиями клиентов во всей Организации

  - В этом примере управление версиями клиентов отключено для всех параметров конфигурации версий клиентов, используемых в Организации.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлетов [New – CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) и [Set CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

