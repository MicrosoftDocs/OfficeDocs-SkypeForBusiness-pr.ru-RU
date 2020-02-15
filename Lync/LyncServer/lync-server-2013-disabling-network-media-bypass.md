---
title: 'Lync Server 2013: отключение обхода сетевых носителей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf551f94bc6b3ba919437730841f54dd01e291
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Отключение обхода сетевых носителей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-15_

Параметры обхода сервера мультимедиа применяются глобально в развертывании Microsoft Lync Server 2013. Обход сервера-посредника позволяет звонкам обходить сервер-посредник. Сведения о том, когда следует использовать обход сервера мультимедиа, приведены в разделе [Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование. Вы можете отключить обход сервера мультимедиа в панели управления Lync Server. Дополнительные сведения о включении и настройке Медиал обхода можно найти [в статье Включение обхода сетевых носителей в Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Отключение обхода медиаданных

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Глобальная**.

4.  На странице **Глобальная** выберите конфигурацию **Глобальная**. На этой странице всегда приводится только одна конфигурация, и она всегда имеет название "Глобальная".

5.  В меню **Изменить** щелкните **Просмотреть сведения**.

6.  На странице **Изменить глобальную настройку** снимите флажок **Разрешить обход мультимедиа**.

7.  Щелкните **Сохранить**, чтобы сохранить изменения.

</div>

<div>

## <a name="see-also"></a>См. также


[Включение обхода сетевых носителей в Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

