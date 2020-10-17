---
title: Восстановление зеркального сервера переднего план выпуска Enterprise Edition — зеркало
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e4bbb7d74c6bf660c69a15ff8250d95f04fed98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511586"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — зеркало

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-19_

При наличии внутреннего сервера Enterprise Edition в зеркальной конфигурации и сбоя зеркального отображения выполните процедуры, описанные в этом разделе. Если произойдет ошибка основной базы данных и зеркала, ознакомьтесь с разделом [Восстановление внутреннего сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Если возникает только основной сбой, ознакомьтесь [со статьей восстановление зеркального внутреннего сервера Enterprise Edition в Lync Server 2013 — основной](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md). Если база данных, в которой размещается центральное хранилище управления, не проходит, ознакомьтесь со статьей [восстановление сервера, на котором размещается центральное хранилище управления в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). В случае сбоя рядового сервера Enterprise Edition, который не является внутренним сервером, ознакомьтесь со статьей [Восстановление рядового сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Перед началом восстановления рекомендуется использовать копию системы в виде образа. Это изображение можно использовать в качестве точки отката, если в процессе восстановления что-то пойдет не так. Вы можете использовать копию образа после установки операционной системы и SQL Server, а также для восстановления или повторной регистрации сертификатов.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>Восстановление зеркального сервера базы данных переднего планов Enterprise Edition

1.  Войдите на сервер переднего плана из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Удаление зеркального отображения. Сначала введите следующий командлет:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Например:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    Выполните это действие для всех типов баз данных на этом сервере.

4.  Создайте чистый или новый сервер с таким же полным доменным именем (DB1.contoso.com) в качестве неисправного компьютера, установите операционную систему, а затем восстановите или повторно зарегистрируйте сертификаты. Этот сервер будет работать как новый зеркальный сервер.

5.  Войдите на новый сервер из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins.

6.  Установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.

7.  Войдите на сервер переднего плана из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins.

8.  Используйте построитель топологий для установки зеркальной базы данных. Выполните следующие действия:
    
      - Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.
    
      - Щелкните правой кнопкой мыши узел Lync Server 2013, выберите пункт **топология**, а затем — **установить базу данных**.
    
      - Следуйте инструкциям мастера **установки базы данных** . На странице " **Создание баз данных** " выберите базы данных, которые требуется повторно создать.
    
      - Следуйте указаниям мастера, пока не появится запрос на **Создание зеркальной базы данных** . Выберите базу данных, которую вы хотите установить, и выполните эту процедуру.
        
        <div>
        

        > [!TIP]
        > Вместо запуска построителя топологий можно использовать командлет <STRONG>Install – CsMirrorDatabase</STRONG> для настройки зеркального отображения. Дополнительные сведения см. в документации Lync Server Management Shell.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

