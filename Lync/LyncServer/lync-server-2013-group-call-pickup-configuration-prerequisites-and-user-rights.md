---
title: Необходимые условия и права пользователя для настройки групповой отправки звонков
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b15be02b48c5e3f95a9b05475bea42284ec275
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498796"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Требования к настройке группового ответа на звонки и пользовательские права в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Групповое получение вызовов — это функция управления звонками, устанавливаемая по умолчанию при развертывании корпоративной голосовой связи. В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить раскладки группового ответа и права пользователя, необходимые для выполнения задач по настройке.

В этом разделе предполагается, что вы читали документацию по планированию, связанную с групповой Отделом ответа на звонки (см. [планирование группового ответа на звонки в Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Предварительные требования к настройке групповой отправки звонков

Для групповой отправки звонков требуются следующие компоненты:

  - служба приложения;

  - Приложение "Парковка вызовов"

Эти компоненты устанавливаются автоматически при развертывании корпоративной голосовой связи.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Права пользователя настройки групповой отправки звонков

Для настройки групповой отправки звонков используются следующие средства администрирования:

  - Командная консоль Lync Server

  - SEFAUtil Resource Kit Tool

Используйте командную консоль Lync Server для создания групп ответа на звонки в таблице орбит парковки вызовов и управления ими. Используйте средство SEFAUtil Resource Kit Tool, чтобы назначить группу ответа на звонки, а также включить групповую отправке звонков для пользователей или отключать групповую откадровую связь для пользователей.

Для настройки групповой отправки вызовов требуется любая из следующих административных ролей в зависимости от задачи:

  - **CsVoiceAdministrator:** Эта роль администратора позволяет создавать, настраивать и управлять всеми параметрами и политиками, связанными с голосовыми сообщениями.

  - **CsUserAdministrator:** Эта роль администратора позволяет пользователям предоставлять групповые звонки для пользователей. Она также имеет доступ только для чтения ко всем параметрам конфигурации голосовой связи.

  - **CsServerAdministrator:** Эта роль администратора позволяет управлять серверами и службами, а также отслеживать их и устранять неполадки.

  - **CsAdministrator:** Эта роль администратора позволяет выполнять все задачи CsVoiceAdministrator, CsServerAdministrator и CsUserAdministrator.

<div>


> [!NOTE]
> Подробные сведения об административных правах приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.



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

