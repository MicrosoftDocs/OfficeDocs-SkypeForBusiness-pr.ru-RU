---
title: Перемещение оставшихся пользователей на Lync Server 2013
description: Перемещение оставшихся пользователей на Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291b58d6644f9ac8f10c63f6585ba865602580df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571315"
---
# <a name="move-remaining-users-to-lync-server-2013"></a>Перемещение оставшихся пользователей на Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

Вы можете переместить пользователей в новое развертывание Lync Server 2013 с помощью панели управления Lync Server или командной консоли Lync Server. Для обеспечения плавного перехода на Lync Server 2013 необходимо соблюдение определенных требований. Дополнительные сведения о предварительных требованиях для выполнения процедур, описанных в этой статье, можно найти в разделе [Настройка клиентов для миграции](configure-clients-for-migration.md). Подробное описание действий по перемещению пользователей приведено в разделе [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Вы не можете использовать оснастку "Active Directory — пользователи и компьютеры" или средства администрирования Lync Server 2010 для перемещения пользователей из старой среды в Lync Server 2013.



</div>

При перемещении пользователя в пул Lync Server 2013 данные для пользователя перемещаются в фоновую базу данных, связанную с новым пулом.

<div>


> [!IMPORTANT]  
> Это относится к активным собраниям, созданным пользователем старой системы. Например, если устаревший пользователь настроил Конференц- <STRONG>зал для собраний</STRONG> , эта конференция по-прежнему будет доступна в новом пуле Lync Server 2013 после перемещения пользователя. Сведения для доступа к этому собранию — те же <STRONG>URL-адрес и код конференции</STRONG>. Единственное отличие состоит в том, что Конференция теперь размещается в пуле Lync Server 2013, а не в пуле Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Пользователям в Lync Server 2013 не требуется развертывать обновленные клиенты одновременно. Новые функциональные возможности станут доступными пользователям только после обновления до новой версии клиентского программного обеспечения.



</div>

<div>

## <a name="post-migration-task"></a>Задача после миграции

1.  После перемещения пользователей убедитесь, что для них назначена политика конференц-связи.

2.  Чтобы убедиться, что собрания, организованные пользователями, размещенными в Lync Server 2013, тесно взаимодействуют с федеративными пользователями, размещенными на Lync Server 2010, политика конференц-связи, назначенная для перенесенных пользователей, должна иметь анонимных участников.

3.  Политики конференц-связи, которые позволяют анонимным участникам разрешить **участникам приглашать анонимных пользователей** , выбранные в панели управления lync Server 2013 и иметь для **аллованонимауспартиЦипантсинмитингс** значение **true** в выходных данных командлета **Get-CsConferencingPolicy** в командной консоли Lync Server.

4.  Сведения о настройке политики конференц-связи с помощью консоли управления Lync Server можно найти в статье [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) в документации по консоли управления Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

