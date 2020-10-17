---
title: 'Lync Server 2013: применение политики архивации Lync Server к пользователю'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cad9784eb2c50662bfedc460cb0dbc8c892206c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504936"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Применение политики архивации Lync Server к пользователю в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-10_

После создания политики пользователя Lync Server ее необходимо применить к определенным пользователям или группам пользователей, размещенным на Lync Server 2013, прежде чем она вступит в силу. Дополнительные сведения о создании политик пользователей для определенных пользователей приведены в статье [Создание и Настройка политик пользователей для архивации в Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) в документации по развертыванию.

Сведения о том, как работают политики архивации, в том числе иерархия для глобальных политик, политик сайтов и пользователей, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .

<div>


> [!NOTE]  
> Чтобы настроить и использовать архивацию, сначала необходимо развернуть архивацию. Сведения о развертывании <A href="lync-server-2013-deploying-archiving.md">архивации в Lync Server 2013</A> содержатся в документации по развертыванию.<BR>Если для развертывания включена интеграция с Microsoft Exchange, политики хранения Exchange In-Place контролируют, включено ли архивирование для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание. Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации. Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Применение политики архивации Lync Server к пользователю

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server 2013. Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server 2013, можно найти в статье [Open the Lync server 2013 Tools администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.

5.  В разделе **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую нужно применить.
    
    <div>
    

    > [!NOTE]  
    > Параметры <STRONG> &lt; автоматического &gt; </STRONG> применения применяют параметры установки сервера по умолчанию. Данный параметр автоматически применяется сервером.

    
    </div>

6.  Нажмите кнопку **Сохранить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

