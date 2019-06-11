---
title: 'Lync Server 2013: создание пользовательской политики для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1d2cd767af4cbee7c416dc8f600ed9e9e192a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Создание пользовательской политики для сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

На панели управления Lync Server вы можете определить политики пользователей, которые могут назначаться пользователям. ****

Политика пользователя переопределяет глобальную политику и политики сайта, но только для пользователей, которым она назначена.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию. Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера для сохраняемого чата, ознакомьтесь с разстройкой <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Параметры сервера сохраняемого чата глобально или для постоянного пула серверов чатов в Lync server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>Создание политики пользователей для сохраняемого чата

1.  Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора. Дополнительные сведения о различных способах запуска панели управления Lync Server можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Вы также можете использовать командлеты Windows PowerShell. Дополнительные сведения о настройке сохраняемого сервера чата можно найти в документации по развертыванию <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">с помощью командлетов Windows PowerShell</A> .

    
    </div>

3.  В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.

4.  Нажмите кнопку **Создать** и выберите **Политика пользователя**.

5.  В окне **Создание политики сохраняемого чата** выполните следующие действия.
    
      - В поле **Имя** укажите имя новой политики пользователя.
    
      - В разделе **Описание**укажите сведения о политике пользователя (например, политика постоянного чата для определенного пользователя).
    
      - Чтобы настроить сохраняемый чат для всех пользователей, которые не управляются с помощью политики пользователя, установите или снимите флажок **включить сохраняемый чат** .

6.  Нажмите **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

