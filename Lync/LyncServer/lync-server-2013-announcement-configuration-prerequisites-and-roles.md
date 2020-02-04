---
title: 'Lync Server 2013: необходимые условия и роли для настройки объявлений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42cbc1429d4e27ee172dc1dacf6b86fa6ac243d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Необходимые условия и роли для настройки объявлений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-25_

Объявление — это функция управления голосовым звонком в корпоративной среде. В этой статье описаны действия, которые необходимо выполнить, прежде чем можно будет настроить объявление и назначения ролей, необходимые для выполнения задач настройки.

В этом разделе предполагается, что вы прочитали документацию по планированию, относящуюся к объявлению (см. раздел [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Предварительные требования для конфигурации объявлений

Для приложения извещения необходимы следующие компоненты:

  - приложения

  - "Группа ответа"

  - Хранилище файлов, для хранения звуковых файлов

Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Роли конфигурации объявлений

Для настройки объявлений можно использовать следующие средства администрирования:

  - Панель управления Lync Server

  - Командная консоль Lync Server

Для настройки приложения объявления требуется одна из следующих административных ролей:

  - **Ксвоицеадминистратор**   . Эта роль администратора может создавать, настраивать и управлять всеми параметрами и политиками голосовой связи, включая параметры объявлений.

  - **Кссерверадминистратор**   . Эта роль администратора может управлять, отслеживать и устранять неполадки серверов и служб, а также настраивать все параметры объявлений.

  - **Ксадминистратор**   . Эта роль администратора может выполнять все административные задачи и изменять все параметры.

  - **Ксвиевонлядминистратор**   . Эта роль администратора может просматривать развертывание, чтобы отслеживать состояние развертывания.

<div>


> [!NOTE]  
> Подробнее об административных правах пользователей можно узнать в разделе <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.



</div>

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

