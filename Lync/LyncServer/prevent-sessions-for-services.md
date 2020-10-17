---
title: Запрет сеансов для служб
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47202d91fdf0020a7692a9ff7b0c346ee3cb7aef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509276"
---
# <a name="prevent-sessions-for-services"></a>Запрет сеансов для служб

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

Вы можете использовать панель управления Microsoft Lync Server 2010, чтобы запретить новые сеансы для всех служб Lync Server 2010, работающих на определенном компьютере, или запретить новые сеансы для конкретной службы Lync Server 2010.

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>Запрет новых сеансов для всех служб Lync Server на компьютере

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте Панель управления Lync Server.

3.  В левой панели навигации щелкните **Топология**, а затем щелкните **Состояние**.

4.  На странице **Состояние** выполните сортировку или поиск по списку, чтобы найти компьютер, на котором выполняются службы, для которых нужно запретить новые сеансы, а затем щелкните ее.

5.  Щелкните **Действие**.

6.  Щелкните **Запретить новые сеансы для всех служб**.

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Запрет новых сеансов для определенной службы

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте Панель управления Lync Server.

3.  В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).

4.  На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.

5.  Нажмите кнопку **Свойства**.

6.  Отсортируйте список служб, если это необходимо, и щелкните службу, для которой вы хотите запретить новые сеансы.

7.  Щелкните **Действие**.

8.  Щелкните **Запретить новые сеансы для службы**.

9.  Нажмите кнопку **Закрыть**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

