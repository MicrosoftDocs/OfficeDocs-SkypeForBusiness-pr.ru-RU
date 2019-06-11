---
title: 'Lync Server 2013: создание и изменение политики мобильности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Создание и изменение политики Mobility Service в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете создать или изменить политику мобильности, чтобы позволить пользователям мобильных устройств использовать поддерживаемые возможности Lync, такие как обмен мгновенными сообщениями, присутствие и контакты. Вы можете создавать и изменять политики Mobility Service из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Создание политики мобильной связи с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Переход к **политике мобильной** связи.

4.  На странице " **политика мобильности** " нажмите кнопку **создать**и выполните одно из указанных ниже действий.
    
    1.  Чтобы создать политику мобильности сайта, нажмите кнопку **Политика сайта**, выберите сайт, нажмите кнопку **ОК**, проверьте параметры по умолчанию и, если нужно, внесите необходимые изменения.
    
    2.  Чтобы создать политику мобильности пользователей, нажмите кнопку **Политика пользователя**, введите имя, проверьте параметры по умолчанию и, если нужно, внесите необходимые изменения.

5.  Нажмите **Исполнить**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Изменение политики мобильной связи с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Переход к **политике мобильной** связи.

4.  На странице " **Политика Mobility Service** " выберите одну из существующих политик мобильной связи.

5.  В меню **Правка** щелкните **Подробнее**.

6.  Измените параметры.

7.  Нажмите **Исполнить**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Создание политик внешнего доступа с помощью командлетов Windows PowerShell

С помощью Windows PowerShell и командлета **New-ксмобилитиполици** можно создавать политики мобильной связи (в области сайта или на уровне пользователей). Кроме того, вы можете использовать командлет **Set-ксмобилитиполици** , чтобы изменить любую из существующих политик, включая глобальную политику. Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Создание политики Mobility Service в области сайта

  - Эта команда создает новую политику мобильности для сайта Redmond.
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Поскольку в предыдущей команде не указаны никакие параметры (кроме обязательного параметра удостоверения), политики будут использовать значения по умолчанию для всех его свойств.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Создание политики Mobility Service в области "на пользователя"

  - Чтобы создать политику мобильности в области "на пользователя", укажите уникальный идентификатор для политики.
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Изменение одного значения свойства при создании политики мобильной связи

  - Для создания политик, использующих различные значения свойств, включите соответствующие параметр и значение параметра. Например, эта команда создает политику мобильности, которая отключает вызов через work.
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Изменение нескольких значений свойства при создании политики мобильной связи

  - Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, эта команда создает политику, которая отключает и мобильность, и звонки через работу.
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Дополнительные сведения можно найти в разделе справки для командлетов [New-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) и [Set-ксмобилитиполици](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка политики мобильных устройств в Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

