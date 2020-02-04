---
title: Импорт политик и параметров
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Импорт политик и параметров

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

После того как вы объедините сведения о топологии Office Communications Server 2007 R2 с помощью проекта Lync Server 2013 для пилотного пула, необходимо запустить командлет командной консоли Lync Server 2013 для миграции политик и параметров конфигурации Office Communications Server 2007 R2 в состав пула Lync Server 2013 Pilot.

Командлет **Import-кслегациконфигуратион** импортирует политики, маршруты голосовой связи, абонентские группы, URL-адреса Communicator Web Access и номера доступа для телефонного подключения в Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Миграция политик и параметров

1.  На сервере переднего плана Lync Server 2013 запустите командную консоль Lync Server Management Shell.

2.  В командной строке введите следующую команду:
    
        Import-CsLegacyConfiguration
    
    После импорта политик воспользуйтесь приведенными ниже инструкциями, чтобы просмотреть импортированные политики на панели управления Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Просмотр импортированных политик

1.  Откройте панель управления Lync Server 2013.

2.  Нажмите кнопку **Маршрутизация голоса** и просмотрите импортированные политики.

3.  Выберите **Конференц** -связь и просмотрите импортированные политики.

4.  Выберите пункт **Федерация и внешний доступ** и просмотрите импортированные политики.

5.  Нажмите кнопку **мониторинг и архивация** и просмотрите импортированные политики.

</div>

</div>

<span> </span>

</div>

</div>

</div>

