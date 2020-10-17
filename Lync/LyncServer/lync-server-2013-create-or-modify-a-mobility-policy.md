---
title: 'Lync Server 2013: создание или изменение политики мобильности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c54222d7fda3c3d5581db85b0fc264358e2bde22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501656"
---
# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Создание или изменение политики мобильности в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Вы можете создать или изменить политику мобильности, чтобы позволить мобильным пользователям использовать поддерживаемые мобильные устройства для доступа к функциональным возможностям Lync, таким как обмен мгновенными сообщениями, сведения о присутствии и контакты. Вы можете создавать и изменять политики мобильности из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Создание политики мобильности с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты** и затем нажмите кнопку навигации **Политика мобильности**.

4.  На странице **политика мобильности** нажмите кнопку **создать**, а затем выполните одно из следующих действий.
    
    1.  Чтобы создать политику мобильности сайта, щелкните элемент **Политика сайта**, выберите сайт, нажмите кнопку **ОК**, просмотрите параметры по умолчанию и при необходимости измените их.
    
    2.  Чтобы создать политику мобильности сайта, щелкните элемент **Политика пользователя**, выберите имя, просмотрите параметры по умолчанию и при необходимости измените их.

5.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Изменение политики мобильности с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты** и затем нажмите кнопку навигации **Политика мобильности**.

4.  На странице **политика мобильности** выберите одну из существующих политик мобильности.

5.  В меню **Правка** выберите пункт **Подробнее**.

6.  Измените параметры.

7.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Создание политик внешнего доступа с помощью командлетов Windows PowerShell

С помощью Windows PowerShell и командлета **New-CsMobilityPolicy** можно создавать политики мобильной связи (на уровне сайта или на уровне пользователя). Кроме того, вы можете использовать командлет **Set-CsMobilityPolicy** для изменения любых существующих политик, включая глобальную. Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Создание политики мобильности на уровне сайта

  - Данная команда создает новую политику мобильности для сайта Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Для всех свойств таких политик будут использоваться значения по умолчанию, так как в приведенной выше команде не заданы никакие параметры, кроме обязательного параметра Identity.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Создание политики мобильности на уровне пользователя

  - Чтобы создать политику мобильности на уровне пользователя, укажите для нее уникальный параметр Identity:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Изменение значения отдельного свойства при создании политики мобильности

  - Чтобы создать политики, использующие разные значения свойства, включайте в них соответствующий параметр со значением. Например, следующая команда создает политику мобильности, отключающую возможность "Позвонить с рабочего":
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Изменение значений нескольких свойств при создании политики мобильности

  - Посредством включения нескольких параметров можно изменять значения нескольких свойств. Например, следующая команда создает политику, отключающую как мобильность, так и возможность "Позвонить с рабочего":
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Дополнительные сведения см. в разделе справки для командлетов [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) и [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy).

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка политики мобильности в Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

