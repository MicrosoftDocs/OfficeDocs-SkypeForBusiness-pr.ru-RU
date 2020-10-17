---
title: Членство в группах и требования к правам пользователей для анализатора соответствия рекомендациям
description: Членство в группах и требования к правам пользователей для анализатора соответствия рекомендациям.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564195"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Членство в группах и требования к правам пользователей для анализатора соответствия рекомендациям в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-21_

Для успешного запуска анализатора соответствия рекомендациям используемая для входа учетная запись должна являться членом группы администраторов на локальном компьютере. Кроме того, для сканирования среды эта учетная запись пользователя должна быть членом следующих групп:

  - **Администраторы домена**     Для перечисления сведений о доменных службах Active Directory и вызова поставщиков инструментария управления Windows (WMI) на контроллерах домена и серверах глобального каталога.

  - **Администраторы**     Требуется на каждом внутреннем компьютере с Lync Server 2013 и на каждом пограничном сервере для вызова поставщиков инструментария управления Windows (WMI) и доступа к реестру.

  - **RTCUniversalReadOnlyAdmins**     Полный или делегированный доступ только для чтения Lync Server 2013 административные права.

  - Администратор только для **просмотра Exchange**     Полный или делегированный просмотр Exchange администратор в организации Microsoft Exchange.

Если ваша учетная запись пользователя не обладает достаточными правами, возможны два варианта:

  - Выполните команду **runas** в командной строке, чтобы запустить средство под учетной записью с достаточными правами. Используйте следующий синтаксис:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - На странице **Подключение к Active Directory** задайте учетные данные для учетных записей, которые планируете использовать для запуска анализатора соответствия рекомендациям. Щелкните элемент **Показать дополнительные варианты входа**. Вы можете ввести три учетные записи: один для подключения к доменным службам Active Directory, один для подключения к пограничным серверам Lync Server 2013 и один для подключения к серверам Exchange. Если вы не указываете какую-либо из этих учетных записей, используется та учетная запись, с помощью которой вы выполнили вход и запустили анализатор соответствия рекомендациям.

</div>

<span> </span>

</div>

</div>

</div>

