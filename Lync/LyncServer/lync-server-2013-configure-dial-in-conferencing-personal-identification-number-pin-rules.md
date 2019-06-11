---
title: Настройка правил для личного идентификационного номера конференц-связи с телефонным подключением (PIN)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda9269bb53a463bf439aef8fda87cbae5bdf17b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a>Настройка правил для личного идентификационного номера конференц-связи с телефонным подключением (PIN) в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-19_

Пользователи Lync Server 2013, у которых есть учетные данные доменных служб Active Directory (AD DS) в вашей организации, могут присоединяться к конференциям в сети для пользователей с проверкой подлинности, используя персональный идентификационный номер (ПИН-код). Политика ПИН-кодов определяет способ работы ПИН-кодов для конференц-связи с телефонным подключением.

Чтобы применить особую политику к узлу или группе пользователей, вы можете создать новую политику ПИН-кодов. Если вы хотите применить одну и ту же политику ПИН-кодов ко всей организации, вы можете использовать глобальную политику ПИН-кодов, изменив ее так, как нужно. Политики ПИН-кодов применяются к пользователям в очередности от самой узкой области действия до самой широкой. Если вы назначили пользователю политику ПИН-кодов на уровне пользователя, ее параметры имеют приоритет. Если вы не назначили политику пользователя, применяется политика ПИН-кодов на уровне узла, если она определена. Если политики пользователя и узла не назначены, действуют параметры по умолчанию глобальной политики ПИН-кодов.

<div>

## <a name="in-this-section"></a>Содержание

  - [Изменение параметров ПИН-кодов по умолчанию для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [оздание или изменение параметров ПИН-кода для конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [Удаление параметров контакта конференц-связи с телефонным подключением для сайта или группы пользователей в Lync Server 2013](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

