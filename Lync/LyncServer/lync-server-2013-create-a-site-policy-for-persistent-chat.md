---
title: 'Lync Server 2013: создание политики сайта для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be98028bf06c20c82dca98fc3bc20d25e97a94c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Создание политики сайта для сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Для каждого сайта, который вы развернули, вы можете создать политику постоянной беседы для определенного сайта.

Конфигурация в политике сайта переопределяет глобальную политику, но только для сайта, к которому применяется эта политика.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию. Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера для сохраняемого чата, ознакомьтесь с разстройкой <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Параметры сервера сохраняемого чата глобально или для постоянного пула серверов чатов в Lync server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Создание политики сохраняемого чата для сайта

1.  Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора. Дополнительные сведения о различных способах запуска панели управления Lync Server можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.
    
    <div>
    

    > [!IMPORTANT]  
    > Вы также можете использовать командлеты Windows PowerShell. Дополнительные сведения можно найти в разделе <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</A> в документации по развертыванию.

    
    </div>

4.  Нажмите кнопку **Создать** и выберите **Политика сайта**.

5.  В окне **Выбор сайта** нажмите сайт, к которому нужно применить эту политику.

6.  В окне **Создание политики сохраняемого чата** выполните следующие действия.
    
      - В поле **Имя** укажите имя новой политики сайта (например, Редмонд).
    
      - В поле **Описание** укажите сведения о цели политики сайта (например, политика комнаты чата для сайта Редмонд).
    
      - Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.

7.  Нажмите **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

