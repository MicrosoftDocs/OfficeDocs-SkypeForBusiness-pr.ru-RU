---
title: 'Lync Server 2013: выполнение подготовки домена'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe361e46753b66a8efdc860ceae406ab3734fee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Выполнение подготовки домена для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-04-16_

Для подготовки доменов можно использовать командлеты Setup или Командная консоль командной консоли Lync Server. Для подготовки домена используется командлет **Enable-CsAdDomain**.

Подготовка домена — это завершающий этап подготовки доменных служб Active Directory для Lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>Подготовка доменов с помощью программы установки

1.  Войдите на любой сервер в домене с помощью учетной записи, входящей в группу "Администраторы домена".

2.  В установочной папке или на носителе Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.

3.  Щелкните **Подготовить Active Directory** и дождитесь, когда определится состояние развертывания.

4.  Когда появится окно **Шаг 5. Подготовка текущего домена**, нажмите кнопку **Запустить**.

5.  На странице **Подготовка домена** нажмите кнопку **Далее**.

6.  На странице **Выполнение команд** найдите сообщение **Состояние задачи: завершено** и нажмите кнопку **Просмотреть журнал**.

7.  В столбце **действие** разверните узел **Подготовка домена**, найдите ** \<\> результат выполнения в** конце каждой задачи, чтобы убедиться, что подготовка домена выполнена успешно, закройте журнал и нажмите кнопку **Готово**.

8.  Дождитесь, пока завершится репликация Active Directory, или выполните принудительную репликацию на все контроллеры домена, перечисленные в оснастке "Active Directory — сайты и службы" для контроллера корневого домена леса.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>Использование командлетов для подготовки домена

1.  Войдите на любой сервер в домене в качестве члена группы администраторов домена.

2.  Установите основные компоненты Lync Server, как описано ниже.
    
    1.  В установочной папке или на носителе Lync Server 2013 запустите программу Setup. exe, чтобы запустить мастер развертывания Lync Server.
    
    2.  Будет предложено установить распространяемый пакет Microsoft Visual C++, нажмите кнопку **Да**.
    
    3.  Появится диалоговое окно установки Lync Server 2013, в котором вы можете указать расположение для установки файлов Lync Server. Оставьте расположение по умолчанию или нажмите кнопку **Обзор**, чтобы выбрать другое расположение, а затем нажмите кнопку **Установить**.
    
    4.  На странице лицензионного соглашения установите флажок **Я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК**. Установщик устанавливает основные компоненты Lync Server 2013.

3.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

4.  Выполняем
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Пример:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Если не указать параметр Domain, значением по умолчанию будет локальный домен.

5.  Убедитесь, что подготовка домена завершилась успешно. Выполните следующую команду.
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Например:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Параметр GlobalSettingsDomainController позволяет указать, где хранятся глобальные параметры. Если параметры хранятся в контейнере System (это обычная ситуация при обновлении развертываний, когда глобальные параметры не переносятся в контейнер Configuration), определите контроллер домена в корне леса Active Directory. Если глобальные параметры хранятся в контейнере Configuration (это обычная ситуация для новых развертываний или обновленных развертываний, в которых параметры перенесены в контейнер Configuration), определите любой контроллер домена в лесу. Если не указать этот параметр, командлет предполагает, что параметры хранятся в контейнере конфигурации и ссылаются на любой контроллер домена в доменных службах Active&nbsp;Directory.

    
    </div>
    
    Если параметр **domain** не указан, по умолчанию используется локальный домен.
    
    Этот командлет возвращает значение **\_домаинсеттингс\_\_** , которое было готово, если подготовка домена выполнена успешно.

</div>

<div>

## <a name="see-also"></a>См. также


[Использование командлетов для обратной подготовки домена для Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

