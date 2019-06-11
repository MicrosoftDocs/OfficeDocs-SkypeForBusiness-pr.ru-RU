---
title: Участники групп и требования к правам пользователей для анализатора соответствия рекомендациям
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Участие в группах и требования к правам пользователей для анализатора соответствия рекомендациям в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-21_

Для успешного выполнения анализатора соответствия рекомендациям учетной записи пользователя, которую вы используете для входа, необходимо быть членом группы "Администраторы" на локальном компьютере. Кроме того, для проверки среды учетной записи пользователя необходимо быть участником следующих групп:

  - **Администраторы домена**   для перечисления данных доменных служб Active Directory и вызова поставщиков WMI (инструментарий управления Windows) на контроллерах домена и серверах глобального каталога.

  - **Администраторы**   , необходимые для каждого внутреннего компьютера Lync Server 2013 и каждый пограничный сервер, должны вызывать поставщики инструментария управления Windows (WMI) и получать доступ к реестру.

  - **Рткуниверсалреадонлядминс**   полный или делегированный доступ только для чтения, права администратора Lync Server 2013.

  - **Exchange View только администратор**   с полным или делегированным Exchange View — только администратор в организации Microsoft Exchange.

Если учетная запись пользователя не имеет достаточных прав пользователя, у вас есть два варианта:

  - В командной строке используйте команду **runas** для запуска средства под учетной записью, имеющей достаточно прав пользователя. Синтаксис выглядит следующим образом:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - На странице **Подключение к Active Directory** задайте учетные данные для учетных записей, которые планируется использовать для проведения анализатора соответствия рекомендациям. Щелкните **Показать расширенные параметры входа**. Вы можете ввести три учетные записи: для подключения к доменным службам Active Directory, для подключения к серверам Lync Server 2013 EDGE и для подключения к серверам Exchange. Если вы не указали ни одну из этих учетных записей, используется учетная запись пользователя, который использовался для входа в систему и запуска анализатора соответствия рекомендациям.

</div>

<span> </span>

</div>

</div>

</div>

