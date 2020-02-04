---
title: 'Lync Server 2013: отключение обхода сетевых мультимедийных файлов'
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
ms.openlocfilehash: 0457281a743d317e17a5fd0728e1a747b4d88271
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a>Отключение обхода сетевых мультимедийных файлов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-15_

Параметры обхода мультимедиа применяются глобально в рамках развертывания Microsoft Lync Server 2013. Обойти функцию мультимедиа позволяет обходить сервер. Сведения о том, когда следует использовать обход мультимедиа, приведены в статье [Планирование обхода мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование. Вы можете отключить обход мультимедиа с помощью панели управления Lync Server. Дополнительные сведения о включении и настройке Медиал обхода можно найти [в разделе Включение обхода сетевого мультимедиа в Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)

<div>

## <a name="to-disable-media-bypass"></a>Отключение обхода мультимедиа

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Конфигурация сети** , а затем — **Глобальная**.

4.  На **глобальной** странице щелкните **глобальную** конфигурацию. Всегда существует только одна конфигурация, и она всегда имеет имя Global.

5.  В меню **Правка** выберите команду **Просмотреть сведения**.

6.  На странице **изменение глобальных параметров** снимите флажок **включить обход мультимедиа** .

7.  Нажмите **кнопку Сохранить,** чтобы сохранить изменения.

</div>

<div>

## <a name="see-also"></a>См. также


[Включение обхода сетевых мультимедийных файлов в Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

