---
title: 'Lync Server 2013: создание пользовательской политики для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0326aa66a1b398153b64c0dc626b8aceb2d24e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Создание пользовательской политики для сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

В панели управления Lync Server определяются политики пользователей, которые можно назначить пользователям в разделе **Пользователи**.

Пользовательская политики переопределяет глобальную политику и политики сайта, но только для пользователей, которым назначена эта политика.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию. Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>Создание пользовательской политики для сохраняемого чата

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Вы также можете использовать командлеты Windows PowerShell. Обратитесь к разделу <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> приведенных в документации по развертыванию.

    
    </div>

3.  В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.

4.  Нажмите кнопку **Создать** и щелкните **Политика пользователя**.

5.  В окне **Создание политики сохраняемого чата** выполните следующие действия.
    
      - В поле **Имя** введите имя новой пользовательской политики.
    
      - В поле **Description (описание**) укажите сведения о политике пользователя (например, политика сохраняемого чата для определенного пользователя).
    
      - Чтобы управлять сохраняемым чат для всех пользователей, которые не контролируются политикой пользователя, установите или снимите флажок **включить сохраняемый чат** .

6.  Щелкните **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

