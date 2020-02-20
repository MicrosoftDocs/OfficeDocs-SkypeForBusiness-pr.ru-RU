---
title: 'Lync Server 2013: Настройка сертификатов для автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e2f39db761462f2f92ebde377fc9c9ecc5c27b6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Настройка сертификатов для автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-12_

Для поддержки безопасных подключений с клиентами Lync в сертификатах для пула директоров, интерфейсных пулов и обратном прокси-сервере требуются дополнительные записи альтернативного имени субъекта.

<div>


> [!NOTE]  
> Вы можете использовать командлет <STRONG>Get-CsCertificate</STRONG> для просмотра сведений о сертификатах, назначенных в данный момент. Однако в представлении по умолчанию не указываются свойства сертификата и отображаются не все значения в свойстве SubjectAlternativeNames. Вы можете использовать командлеты <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate и <STRONG>Set-CsCertificate</STRONG>, чтобы просматривать некоторые сведения, а также запрашивать и назначать сертификаты. Однако это не самый лучший способ в том случае, когда вы не уверены в свойствах альтернативных имен субъектов в текущем сертификате. Для просмотра сертификата и всех участников свойств рекомендуется использовать оснастку "сертификаты" <EM>консоли управления (MMC)</EM> или мастер развертывания Lync Server. В мастере развертывания Lync Server можно просмотреть свойства сертификата с помощью мастера сертификатов. Процедуры просмотра, запроса и назначения сертификата с помощью командной консоли Lync Server и <EM>консоли управления (MMC)</EM> описаны в следующих процедурах. Чтобы использовать мастер развертывания Lync Server, ознакомьтесь с подробными сведениями, если вы развернули пул необязательных директоров или директоров директоров: <A href="lync-server-2013-configure-certificates-for-the-director.md">Настройка сертификатов для директора в Lync Server 2013</A>. Сведения о сервере переднего плана или интерфейсном пуле можно найти здесь: <A href="lync-server-2013-configure-certificates-for-servers.md">Настройка сертификатов для серверов в Lync Server 2013</A>.<BR>Начальные шаги этой процедуры являются подготовительными действиями, призванными сориентировать вас относительно роли текущего сертификата. По умолчанию сертификаты не будут иметь lyncdiscover. &lt;sipdomain&gt; или lyncdiscoverinternal. &lt;внутренняя запись доменного имени&gt; , если вы еще не установили службы Mobility Service или заранее подготовили свои сертификаты. В данной процедуре используется пример имени домена SIP «contoso.com» и пример внутреннего имени домена «contoso.net».<BR>Конфигурация сертификата по умолчанию для Lync Server 2013 и Lync Server 2010 — использовать один сертификат (с именем "default") по умолчанию (для всех целей, кроме веб-служб), WebServicesExternal и WebServicesInternal. Дополнительная конфигурация заключается в использовании отдельных сертификатов для каждого назначения. Управление сертификатами осуществляется с помощью Командная консоль Lync Server и командлеты Windows PowerShell или с помощью мастера сертификатов в мастере развертывания Lync Server.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Обновление сертификатов с использованием новых альтернативных имен субъектов с помощью командной консоли Lync Server

1.  Войдите на компьютер, используя учетную запись с правами и разрешениями локального администратора.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Определите, какие сертификаты были назначены серверу и для какого типа использования. Эта информация потребуется вам на следующем шаге для назначения обновленного сертификата. Введите в командной строке следующее:
    
        Get-CsCertificate

4.  Просмотрите выходные данные из предыдущего шага, чтобы узнать, назначен ли нескольким использованиям один сертификат или для каждого из них назначен отдельный сертификат. Посмотрите на параметр Use, чтобы выяснить, как используется сертификат. Сравните параметр  Thumbprint для отображаемых сертификатов, чтобы узнать, имеет ли один сертификат несколько использований.

5.  Обновите сертификат. Введите в командной строке следующее:
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    Например, если командлет **Get-CsCertificate** отобразил сертификат, у которого для параметра Use установлено значение Default, другой сертификат со значением WebServicesInternal и еще один со значением WebServicesExternal, и все они имеют одинаковое значение Thumbprint, введите в командной строке следующее:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **Важно!**
    
    Если каждому использованию назначен отдельный сертификат (значение Thumbprint различно для каждого из сертификатов), важно не запускать командлет **Set-CsCertificate** с несколькими типами. В данном случае отдельно запустите командлет **Set-CsCertificate** для каждого использования. Например:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  Чтобы просмотреть сертификат, нажмите кнопку **Пуск**, щелкните **Выполнить…**. Введите MMC, чтобы открыть консоль управления (MMC).

7.  В меню консоли управления (MMC) выберите **Файл**, **Добавить или удалить оснастку…**, «Сертификаты». Нажмите кнопку **Добавить**. При отображении запроса выберите **учетной записи компьютера**, а затем нажмите кнопку **Далее**.

8.  Если сертификат находится на этом компьютере, выберите **локальный компьютер**. Если сертификат находится на другом компьютере, выберите **другой компьютер**, введите полное доменное имя компьютера или нажмите кнопку **Обзор** в поле **введите имя объекта для выбора**, введите имя компьютера. Щелкните элемент **Проверить имена**. После разрешения имени компьютера оно подчеркивается. Нажмите кнопку **ОК**, а затем кнопку **Готово**. Нажмите кнопку **ОК** для подтверждения выбора и закройте диалоговое окно **Добавление и удаление оснасток**.
    
    <div>
    

    > [!IMPORTANT]  
    > Если сертификат не отображается в консоли, убедитесь, что вы не выбрали пользователя или службу. Необходимо выбрать компьютер, или вы не сможете определить сертификат пробпер.

    
    </div>

9.  Чтобы просмотреть свойства сертификата, разверните узел **Сертификаты**, разверните узел **Личные** и выберите элемент **Сертификаты**. Выберите сертификат для просмотра, щелкните его правой кнопкой мыши и выберите пункт **Открыть**.

10. В представлении **Сертификат** выберите элемент **Сведения**. Здесь вы можете выбрать имя субъекта сертификата, выбрав элемент **Субъект**, после чего отображаются назначенное имя субъекта и связанные свойства.

11. Чтобы просмотреть назначенные альтернативные имена субъектов, выберите **Альтернативное имя субъекта**. Отображаются все назначенные альтернативные имена субъектов. Найденные в свойстве альтернативные имена субъектов по умолчанию имеют тип **DNS-имя**. Вам следует просмотреть следующие элементы (в соответствии с записями DNS-узла (A либо AAAA для IPv6) все они должны быть полными доменными именами:
    
      - Имя пула для этого пула или имя отдельного сервера, если это не пул
    
      - Имя сервера, которому назначен сертификат
    
      - Записи простых URL-адресов (обычно meet и dialin)
    
      - Внутренние имена веб-служб и внешние имена веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителе топологий и переопределенных на выборе веб-службах.
    
      - Если уже назначено, lyncdiscover. \<sipdomain\> и lyncdiscoverinternal. \<записи\> sipdomain.
    
    Последний элемент представляет для вас наибольший интерес — наличие записи альтернативного имени субъекта lyncdiscover и lyncdiscoverinternal.
    
    После получения этой информации вы можете закрыть представление сертификата и консоль управления (MMC).

12. Если служба автообнаружения, то есть lyncdiscover. \>доменное\> имя и lyncdiscoverinternal. \<доменное\> имя (в зависимости от того, является ли это внешнее или внутреннее имя субъекта) отсутствует альтернативное имя субъекта, и используется один сертификат по умолчанию для типов WebServicesInternal и вебсервицеекстернал по умолчанию, выполните следующие действия:
    
      - В командной строке командной строки командной консоли Lync Server введите:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Если у вас имеется много SIP-доменов, вы не можете использовать новый параметр AllSipDomain. Вместо этого вам следует использовать параметр DomainName. Когда вы используете параметр DomainName, вам следует определить полное доменное имя для записей lyncdisscoverinternal и lyncdiscover. Например:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - Чтобы назначить сертификат, введите следующее:
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Где «Thumbprint» — это отпечаток, отображаемый для недавно выданного сертификата.

13. В случае отсутствия внутренних альтернативных имен субъектов автообнаружения при использовании отдельных сертификатов для Default, WebServicesInternal и WebServicesExternal выполните следующие действия:
    
      - В командной строке командной строки командной консоли Lync Server введите:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        Если у вас имеется много SIP-доменов, вы не можете использовать новый параметр AllSipDomain. Вместо этого вам следует использовать параметр DomainName. Когда вы используете параметр DomainName, вам следует определить подходящий префикс для полного доменного имени. Например:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - В случае отсутствия внешнего альтернативного имени субъекта автообнаружения введите в командной строке следующее:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        Если у вас имеется много SIP-доменов, вы не можете использовать новый параметр AllSipDomain. Вместо этого вам следует использовать параметр DomainName. Когда вы используете параметр DomainName, вам следует определить подходящий префикс для полного доменного имени. Например:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - Чтобы назначить индивидуальные типы сертификатов, введите следующее:
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        Где «Thumbprint» — это отпечаток, отображаемый для недавно выданных индивидуальных сертификатов.

</div>

</div>

<span> </span>

</div>

</div>

</div>

