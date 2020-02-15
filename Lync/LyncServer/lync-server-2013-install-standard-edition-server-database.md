---
title: 'Lync Server 2013: Установка базы данных сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52853073fec62a3386936fe093b83e902d576069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Установка базы данных сервера Standard Edition для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Настройка сервера Standard Edition в качестве единственного сервера в вашей инфраструктуре, который пользователи домов отличаются от других серверных установок в том, что в **мастере развертывания** есть выбор, предназначенный для настройки начального сервера.

<div>

## <a name="to-install-a-standard-edition-server"></a>Установка сервера Standard Edition

1.  Выполните вход на сервер, на котором будет устанавливаться сервер Standard Edition, в качестве локального администратора или эквивалента домена.

2.  Если вы не подготовили доменные службы Active Directory, сначала выполните эти действия. Дополнительные сведения см. в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  В мастере развертывания Lync Server нажмите кнопку **подготовить первый сервер Standard Edition**.

4.  На странице **Подготовка отдельного сервера Standard Edition** нажмите кнопку **Далее**.

5.  На странице **выполнение команд** в качестве центрального хранилища управления устанавливается SQL Server 2012 Express. Создаются необходимые правила брандмауэра. После завершения установки базы данных и предварительно устанавливаемого ПО нажмите кнопку **Готово**.
    
    <div>
    

    > [!NOTE]  
    > При первоначальной установке может пройти некоторое время, прежде чем на экране вывода результатов команд появятся какие-либо изменения. Это обусловлено установкой SQL Server Express. Если необходимо отслеживать установку базы данных, используйте для этого диспетчер задач.

    
    </div>

6.  На странице мастера развертывания Lync Server щелкните **установить построитель топологий** , если вы еще не установили средства администрирования. Для получения дополнительных сведений ознакомьтесь со статьей [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Убедитесь, что рядом с пунктами "Подготовить Active Directory", "Подготовить первый сервер Standard Edition" и "Установить построитель топологий" стоят зеленые галочки.

</div>

</div>

<span> </span>

</div>

</div>

</div>

