---
title: 'Lync Server 2013: Создание политики сайта для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b682191b0170a3915f44d54daa426ca5ce4544
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Создание политики сайта для сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Для каждого развернутого сайта можно создать политику сохраняемого чата для определенных сайтов.

Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию. Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Создание политики сохраняемого чата для сайта

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.
    
    <div>
    

    > [!IMPORTANT]  
    > Вы также можете использовать командлеты Windows PowerShell. Дополнительные сведения: <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> описанных в документации по развертыванию.

    
    </div>

4.  Нажмите кнопку **Создать** и щелкните **Политика сайта**.

5.  В окне **Выбор сайта** щелкните сайт, к которому будет применена политика.

6.  В окне **Создание политики сохраняемого чата** выполните следующие действия.
    
      - В поле **Имя** введите имя новой политики сайта (например, Redmond).
    
      - В поле **Описание** введите сведения о политике сайта (например, политика комнаты чата для Redmond).
    
      - Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.

7.  Нажмите кнопку **Сохранить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

