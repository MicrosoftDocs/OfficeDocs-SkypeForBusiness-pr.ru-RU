---
title: 'Lync Server 2013: Проверка или Настройка проверки подлинности и сертификации для виртуальных каталогов IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4a9e4b2ad53b3fa3a339eae7b4b1ee1f4412548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Проверка и Настройка проверки подлинности и сертификации в виртуальных каталогах IIS в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-05-25_

Используйте следующую процедуру для настройки сертификата в виртуальных каталогах служб IIS или убедитесь, что сертификат настроен правильно. Выполните приведенную ниже процедуру на каждом сервере, на котором выполняются службы IIS, в внутреннем пуле Lync Server, а также в дополнительном директоре или серверах пула директоров.

<div>


> [!NOTE]  
> Приведенная ниже процедура определяет процедуру запроса комбинированного сертификата, используемого для всех целей Lync Server, внутреннего веб-сайта и внешнего веб-сайта в службах IIS. Lync Server 2010 представил набор командлетов&nbsp;Windows PowerShell для консоли управления Lync Server, чтобы выразить цель управления запросом сертификата, импортом и назначением. В данной процедуре предполагается, что существует внутренний развернутый центр сертификации (ЦС), который может обработать данный запрос. Если вы используете общедоступные сертификаты для целей Lync Server, или для вашего ЦС требуется автономный запрос, ознакомьтесь с подробным синтаксисом, приведенным в этом разделе, для получения сведений о параметре – OUTPUT. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request — CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Настройка проверки подлинности и сертификатов для виртуальных каталогов служб IIS

1.  Для успешного выполнения следующих действий необходимо войти на компьютер (сервер переднего плана или директор), где установлены веб-службы, и быть локальным администратором. Вам следует иметь разрешения **read** и **enroll** для центра сертификации, из которого вы будете запрашивать сертификаты, если этот центр сертификации принадлежит вашей организации. Разрешения для центра сертификации не требуются, если вы настроите и отправите автономный запрос на сертификат.

2.  Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Диспетчер служб IIS**.

3.  В окне **Диспетчер служб IIS** выберите **Имя сервера**. В окне **Просмотр возможностей** выберите элемент **Сертификаты сервера**, щелкните правой кнопкой мыши и выберите пункт **Открытие функции**.
    
    <div>
    

    > [!TIP]  
    > Если имеются сертификаты, назначенные данному серверу, они отображаются в этом представлении компонента сертификатов сервера. Если имеется сертификат, соответствующий требованиям для внешнего веб-сайта в службах IIS, вы можете использовать его повторно. Чтобы просмотреть сертификат, щелкните его правой кнопкой мыши и выберите пункт <STRONG>Просмотреть…</STRONG>

    
    </div>

4.  На сервере переднего плана или режиссере, для которого запрашивается сертификат, нажмите кнопку **Пуск**, выберите **все программы**, выберите **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.

5.  В командной консоли Lync Server введите следующую команду:
    
        Get-CsCertificate
    
    выходные данные представляют собой список сертификатов, которые в данный момент находятся в хранилище личных сертификатов на компьютере. Обратите внимание на то, что в комбинированном сертификате (где компоненты по умолчанию, компоненты внутренних веб-служб и компоненты внешних веб-служб используют один и тот же сертификат) видно, что свойство Use заполняется значениями Default, WebServicesInternal и WebServicesExternal. Кроме того, свойство Thumbprint будет одинаковым для каждого из типов Use. Пример выходных данных Get-CsCertificate показан в следующем примере:
    
    ![Get – CsCertificate сведения о текущем состоянии сцерт](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get – CsCertificate сведения о текущем состоянии сцерт")

6.  В командной консоли Lync Server введите следующую команду:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    При этом полная команда выглядит следующим образом:
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > По умолчанию Request-CsCertificate заполняет имя субъекта именем сервера или пула, а записи в альтернативном имени субъекта — полным доменным именем сервера, полным доменным именем пула, полными доменными именами простых URL-адресов, а также полными доменными именами внутренних и внешних веб-служб. Для этого командлет ссылается на документ топологии в вашем развертывании. Если вы указали параметр –Verbose, то в случае отсутствия какого-либо значения вы получаете уведомление о том, что расчетные и фактические значения для альтернативных имен различаются, однако этот параметр не сообщает вам, какие именно значения отсутствуют. Он предоставляет вам полное вычисленное значение, на которое ссылается командлет. Используйте строку вычисленных альтернативных имен в выходных данных, чтобы повторно запросить новый сертификат, включающий в себя все значения.

    
    </div>
    
    ![Выходные данные запроса сертификата с помощью команды Request — Ксцертифика](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Выходные данные запроса сертификата с помощью команды Request — Ксцертифика")

7.  В командной консоли Lync Server введите следующую команду:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    При этом полная команда выглядит следующим образом:
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Выходные данные командлета Set-CsCertificate покажут, что один сертификат (обозначенный отпечатком сертификата) назначается для использования Default, WebServicesExternal и WebServicesInternal.
    
    ![Выходные данные командлета Set — CsCertificate в службах IIS Вебекст](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Выходные данные командлета Set — CsCertificate в службах IIS Вебекст")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>Настройка проверки подлинности и сертификатов для виртуальных каталогов служб IIS и подтверждение правильности такой настройки

1.  Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Диспетчер служб IIS**.

2.  В **диспетчере служб IIS**разверните узел **ServerName**и разверните узел **сайты**.

3.  Щелкните правой кнопкой мыши элемент **Lync Server External Web Site** (Внешний веб-сайт Lync Server) и выберите пункт **Изменить привязки**

4.  Убедитесь, что HTTPS сопоставлен с портом 4443, а затем щелкните элемент **HTTPS**.

5.  Выберите запись HTTPS, нажмите кнопку **изменить**, а затем убедитесь, что сервер Lync Server вебсервицесекстерналцертификате связан с этим протоколом. Сравните отпечаток из командлета Set-CsCertificate, чтобы убедиться, что ожидаемый сертификат правильно сопоставлен с привязкой HTTPS.

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set — CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

