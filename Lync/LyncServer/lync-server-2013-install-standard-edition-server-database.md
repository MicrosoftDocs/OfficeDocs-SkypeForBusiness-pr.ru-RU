---
title: 'Lync Server 2013: для установка базы данных сервера Standard Edition'
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
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>Установка базы данных сервера Standard Edition для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Настройка стандартного сервера выпусков в качестве единственного сервера в инфраструктуре, которой пользователи не отличаются от других установок сервера в том случае, если у вас есть выбор в **мастере развертывания** специально для настройки первоначального сервера.

<div>

## <a name="to-install-a-standard-edition-server"></a>Установка сервера Standard Edition

1.  Войдите на сервер, на котором вы собираетесь установить стандартный выпуск для локального администратора или эквивалент домена.

2.  Если вы не предготовили доменные службы Active Directory, сначала выполните эти действия. Дополнительные сведения можно найти в разделе [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

3.  В мастере развертывания Lync Server нажмите кнопку **подготовить первый сервер Standard Edition**.

4.  На странице **подготовить один стандартный выпуск на сервере** нажмите кнопку **Далее**.

5.  На странице **выполнение команд** сервер SQL Server 2012 Express установлен в качестве хранилища центрального управления. Создаются необходимые правила брандмауэра. После завершения установки базы данных и необходимого программного обеспечения нажмите кнопку **Готово**.
    
    <div>
    

    > [!NOTE]  
    > Начальная установка может занять некоторое время и не отменять заметные обновления экрана сводки вывода команды. Это происходит из-за установки SQL Server Express. Если вам нужно наблюдать за установкой базы данных, используйте диспетчер задач для наблюдения за настройкой.

    
    </div>

6.  На странице мастера развертывания Lync Server щелкните **установить построитель топологии** , если вы ранее не установили средства администрирования. Подробности можно найти в разделе [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

7.  Убедитесь, что рядом с пунктом "Подготовка Active Directory" установлены зеленые галочки, "подготовить первый сервер Standard Edition" и "установить построитель топологии".

</div>

</div>

<span> </span>

</div>

</div>

</div>

