---
title: 'Lync Server 2013: необходимые условия и роли для настройки оповещений'
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
ms.openlocfilehash: 09a7a8a17e3431c382ce4f49534336d266bbaa13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Необходимые условия и роли для настройки объявлений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-25_

Извещение — это функция управления вызовами корпоративной голосовой связи. В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить объявление и назначения ролей, необходимые для выполнения задач по настройке.

В этом разделе предполагается, что вы прочитали документацию по планированию, относящуюся к уведомлению (см. [Планирование функций управления вызовами в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Предварительные требования к настройке объявлений

Для приложения извещения необходимы следующие компоненты:

  - служба приложения;

  - приложение группы ответа;

  - хранилище файлов для звуковых файлов.

Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Роли настройки объявлений

Для настройки объявлений можно использовать следующие средства администрирования.

  - Панель управления Lync Server

  - Командная консоль Lync Server

Для настройки приложения извещения требуется одна из следующих административных ролей:

  - **CsVoiceAdministrator**   эта роль администратора позволяет создавать, настраивать и управлять всеми параметрами и политиками голосовой связи, включая параметры оповещений.

  - **CsServerAdministrator**   эта роль администратора позволяет управлять, отслеживать и устранять неполадки в серверах и службах, а также настраивать все параметры оповещений.

  - **CsAdministrator**   . Эта роль администратора позволяет выполнять все административные задачи и изменять все параметры.

  - **CsViewOnlyAdministrator**   эта роль администратора может просматривать развертывание для мониторинга работоспособности развертывания.

<div>


> [!NOTE]  
> Дополнительные сведения об административных правах пользователей приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.



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

