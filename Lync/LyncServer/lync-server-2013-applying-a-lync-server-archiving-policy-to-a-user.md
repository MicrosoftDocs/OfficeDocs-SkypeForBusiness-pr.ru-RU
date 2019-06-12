---
title: 'Lync Server 2013: применение политики архивации сервера Lync Server для пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295f1a0370372d937b07a38eab51cd43d0ef9f5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Применение политики архивации в Lync Server к пользователю в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-10_

После создания политики пользователя Lync Server вы должны применить ее к определенным пользователям или группам пользователей, которые размещены на Lync Server 2013, прежде чем он сможет вступить в силу. Дополнительные сведения о создании политик пользователей для конкретных пользователей можно найти в разделе [Создание и Настройка политик пользователей для архивации в Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) в документации по развертыванию.

Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по эксплуатации.

<div>


> [!NOTE]  
> Для конфигурации и использования архивации необходимо сначала развернуть ее. Подробности можно найти <A href="lync-server-2013-deploying-archiving.md">в разделе Развертывание архивации в Lync Server 2013</A> в документации по развертыванию.<BR>Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте. Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо указать все соответствующие параметры в разделе конфигурации архивации. Подробности можно найти <A href="lync-server-2013-configuring-archiving-options.md">в разделе Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Применение политики архивации сервера Lync Server для пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server 2013. Дополнительные сведения о различных способах запуска панели управления Lync Server 2013 можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить.

4.  В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.

5.  В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую вы хотите применить.
    
    <div>
    

    > [!NOTE]  
    > Для <STRONG> &lt;параметров&gt; автоматической</STRONG> настройки применяются параметры установки сервера по умолчанию. Данные параметры автоматически применяются сервером.

    
    </div>

6.  Нажмите **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

