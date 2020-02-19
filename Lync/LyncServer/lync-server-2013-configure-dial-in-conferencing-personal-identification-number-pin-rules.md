---
title: Настройка правил ПИН-кодов для конференц-связи с телефонным подключением
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a2298dffdcb868646f2d4d4513702a4c4554d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a>Настройка правил ПИН-кодов для конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-19_

Lync Server 2013 пользователи с учетными данными доменных служб Active Directory (AD DS) в организации могут присоединяться к конференциям в качестве пользователей, прошедших проверку подлинности, с помощью персонального идентификационного номера (ПИН-кода). Политика ПИН-кодов определяет способ работы ПИН-кодов для конференц-связи с телефонным подключением.

Чтобы применить особую политику к узлу или группе пользователей, вы можете создать новую политику ПИН-кодов. Если вы хотите применить одну и ту же политику ПИН-кодов ко всей организации, вы можете использовать глобальную политику ПИН-кодов, изменив ее так, как нужно. Политики ПИН-кодов применяются к пользователям в очередности от самой узкой области действия до самой широкой. Если вы назначили пользователю политику ПИН-кодов на уровне пользователя, ее параметры имеют приоритет. Если вы не назначили политику пользователя, применяется политика ПИН-кодов на уровне узла, если она определена. Если политики пользователя и узла не назначены, действуют параметры по умолчанию глобальной политики ПИН-кодов.

<div>

## <a name="in-this-section"></a>Содержание

  - [Изменение параметров ПИН-кода конференц-связи с телефонным подключением по умолчанию в Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [Создание или изменение параметров ПИН-кода конференц-связи с телефонным подключением в Lync Server 2013 для сайта или группы пользователей](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [Удаление параметров ПИН-кода конференц-связи с телефонным подключением для сайта или группы пользователей в Lync Server 2013](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

