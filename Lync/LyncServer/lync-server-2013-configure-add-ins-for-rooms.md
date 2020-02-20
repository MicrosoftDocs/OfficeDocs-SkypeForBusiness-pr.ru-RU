---
title: 'Lync Server 2013: Настройка надстроек для комнат'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27dd6ab5cdd6ca67d94071049a9615731735d8aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Настройка надстроек для комнат в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

В панели управления Lync Server 2013 вы можете использовать раздел **надстройка** страницы **сохраняемого чата** для сопоставления URL-адресов с комнатами сохраняемого чата. Эти URL-адреса отображаются в клиенте Lync 2013 в комнате чата в области расширения беседы. Администратор должен добавить надстройки в список зарегистрированных надстроек, а диспетчеры комнат чата или создатели должны связать комнаты с одной из зарегистрированных надстроек, прежде чем пользователи смогут увидеть это обновление в своем клиенте Lync 2013.

Надстройки используются для расширения функций комнаты чата. Типичная надстройка может содержать URL-адрес, указывающий на приложение Silverlight, которое перехватывает, когда Биржевая сводка публикуется в комнате чата, и показывает историю акций в области расширяемости. К другим примерам относится внедрение URL-адреса OneNote в комнату чата в качестве надстройки, чтобы включить некоторый общий контекст — «Важные размышления» или «Тема дня».

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Настройка надстроек для комнат чата

1.  Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Вы также можете использовать командлеты Windows PowerShell. Дополнительные сведения: <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> описанных в документации по развертыванию.

    
    </div>

3.  В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Надстройка**.
    
    Для нескольких развертываний пула серверов сохраняемого чата выберите соответствующий пул из раскрывающегося списка.

4.  На странице **Надстройка** нажмите кнопку **Создать**.

5.  В разделе **Выбор службы**выберите службу, соответствующую пулу серверов сохраняемого чата, где необходимо создать надстройку. Надстройки нельзя переместить из одного пула в другой и нельзя сделать их общими для разных пулов.

6.  В окне **Создание надстройки** выполните следующие действия.
    
      - В поле **Имя** введите имя новой надстройки.
    
      - В поле **URL-адрес** укажите URL-адрес, который необходимо связать с надстройкой. URL-адреса ограничены до протоколов HTTP и HTTPS.

7.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="see-also"></a>См. также


[Откройте Lync Server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md)  


[Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

