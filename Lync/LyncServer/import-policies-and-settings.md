---
title: Импорт политик и параметров
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1163a8abc54f60d55f1042d6d82552ca9f133a60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523396"
---
# <a name="import-policies-and-settings"></a>Импорт политик и параметров

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

После объединения информации о топологии Office Communications Server 2007 R2 с помощью пилотного пула Lync Server 2013 необходимо запустить командлет командной консоли Lync Server 2013, чтобы перенести политики и параметры конфигурации Office Communications Server 2007 R2 в пилотный пул Lync Server 2013.

Командлет **Import-CsLegacyConfiguration** импортирует политики, маршруты голосовых вызовов, абонентские группы, URL-адреса веб-клиента Communicator и номера доступа по телефонной линии в Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Перенос политик и параметров

1.  На сервере переднего плана Lync Server 2013 запустите командную консоль Lync Server.

2.  Введите в командной строке следующую команду:
    
        Import-CsLegacyConfiguration
    
    После импорта политик используйте приведенную ниже процедуру, чтобы просмотреть импортированные политики в панели управления Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Просмотр импортированных политик

1.  Откройте панель управления Lync Server 2013.

2.  Выберите пункт **Маршрутизация голосовой связи** и просмотрите импортированные политики.

3.  Выберите пункт **Конференц-связь** и просмотрите импортированные политики.

4.  Выберите пункт **Федерация и внешний доступ** и просмотрите импортированные политики.

5.  Выберите пункт **Мониторинг и архивация** и просмотрите импортированные политики.

</div>

</div>

<span> </span>

</div>

</div>

</div>

