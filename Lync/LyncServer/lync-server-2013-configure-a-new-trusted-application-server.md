---
title: 'Lync Server 2013: Настройка нового доверенного сервера приложений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4d01e817e1a874af8c6beccdee332f85cc79ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Настройка нового доверенного сервера приложений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Доверенное приложение — это приложение, основанное на Microsoft Lync Server Managed Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Microsoft Lync Server 2013. Подробные сведения о приложениях UCMA можно найти в [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320)разделе "интегрированный API Managed Communications API 3,0".

Сведения о настройке Microsoft Outlook Web Access (OWA) и Lync Server 2013 приведены в статье "Настройка Outlook Web App и интеграции Lync Server 2010" в документации по Microsoft Exchange Server 2013.

Чтобы успешно опубликовать, включить или отключить топологию при добавлении или удалении роли сервера, необходимо войти в систему с учетной записью члена групп RTCUniversalServerAdmins или "Администраторы домена". Кроме того, вы можете делегировать соответствующие разрешения и права администратора для добавления ролей сервера. Для получения дополнительных сведений обратитесь к разделу [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) в документации по развертыванию. Для остальных изменений конфигурации требуется только членство в группе RTCUniversalServerAdmins.

<div>

## <a name="to-configure-a-trusted-application-server"></a>Настройка сервера доверенных приложений

1.  Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.

2.  Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.

3.  Выберите **Download topology from existing deployment** (Загрузить топологию из существующего развертывания) и затем нажмите кнопку **ОК**.

4.  В диалоговом окне **Сохранить топологию как** выберите нужный файл в построителе топологий, а затем нажмите кнопку **сохранить**.

5.  В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений** и выберите команду **Создать пул доверенных приложений**.

6.  В поле **Pool FQDN** (Полное доменное имя пула) введите полное доменное имя пула доверенных приложений, укажите параметры пула (пул из одного компьютера или нескольких компьютеров) и затем нажмите кнопку **Next** (Далее).

7.  На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Lync Server 2013.

8.  Нажмите кнопку **Finish** (Готово).

9.  Выберите верхний узел **Lync Server 2013** и затем в меню **Действия** выберите пункт **Опубликовать**.
    
    **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.

</div>

</div>

<span> </span>

</div>

</div>

</div>

